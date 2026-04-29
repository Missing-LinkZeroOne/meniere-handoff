# Ménière-tietopalvelu — Claude Code -konteksti

Tämä dokumentti on tarkoitettu Claude Code -istunnoille. Se kuvaa projektin tilan, käytännöt ja keskeiset päätökset jotka on tehty aiemmissa iteraatioissa.

## Projektin yleiskuvaus

Henkilökohtainen oppimisprojekti — interaktiivinen suomenkielinen tietopalvelu Ménièren taudista. Käyttäjäkohderyhmä on Ménière-potilaat ja heidän läheisensä, erityisesti **noin 70-vuotiaat käyttäjät** (vanhempi sukulainen tai puoliso).

Sivusto on **yksi itsenäinen `index.html`-tiedosto** ilman ulkoisia riippuvuuksia, kokoa noin 330 kt. Se julkaistaan staattisena GitHub Pagesissa tai Netlify Dropissa, ja URL jaetaan WhatsAppissa. iOS Safari -yhteensopivuus on välttämätön (WhatsAppin in-app-WebView rajoittaa JS:ää, joten sivuston pitää avautua oikeassa selaimessa).

## Tärkeimmät tekniset päätökset

### Yksittäinen tiedosto, ei build-vaihetta
Sivusto on yhdessä HTML-tiedostossa kaikki CSS, JS ja sisältö mukaan lukien. Ei `npm install`, ei build-komentoja, ei moduulijärjestelmää. Tämä on tarkoituksellinen valinta: helppo julkaista, helppo varmuuskopioida, helppo lukea koko tila yhdessä paikassa.

Jos joudut jakamaan tiedostoa jossain vaiheessa, tee se vasta kun perustelu on vahva. Iteraatiot tähän asti ovat olleet helposti hallittavissa yhdellä tiedostolla, ja yhden tiedoston etu Git-diffeissä on suuri (jokainen muutos näkyy yhdessä paikassa).

### iOS-yhteensopivuus on pakollinen
- **Ei lookbehind-regexejä** (esim. `(?<=...)`) — iOS Safari < 16.4 ei tue. Käytä capture group -syntaksia.
- **`touch-action: manipulation`** kaikkiin klikattaviin elementteihin — estää double-tap-zoomin
- **`role="button"`, `tabindex="0"`, `onclick="void(0)"`** klikattaville `<div>`-elementeille — iOS Safari ei muuten lähetä klikkaustapahtumia kaikille elementeille
- **Event delegation document-tasolla** + suora click + touchend + touchstart-tracker — robusti tap-mekanismi
- **`pointer-events: none`** klikattavien elementtien lapsielementeille
- **Globaali error handler** näyttää JS-virheet näkyvästi sivun ylälaitaan — tärkeää koska iOS-käyttäjillä ei ole helposti pääsyä konsoliin
- **localStorage on aina `try/catch`-suojattu** — incognito ja lockdown mode voivat estää sen

### Saavutettavuus 70-vuotiaalle
- **Vähintään 56×56 px tap-target** kelluvalle akuuttinapille, vähintään 48×48 px muille napeille
- **NHS Design System v10 -visuaalinen kieli** — sininen `#005EB8`, harmaa `#f0f4f5` tausta, Frutiger→Arial, focus-tila 4px keltainen outline
- **Iso teksti**: 16px leipä oletuksena, A−/A/A+ -säädin (14/16/18 px)
- **Selkeät visuaalit**: aina näkyvä punainen akuuttinappi, korostetut tilat hover/focus, statusrivit haulle
- **Sticky-elementit**: hakukenttä pysyy paneelin ylälaidassa kun rullaa
- **WCAG 2.2 AA -kontrastit** kaikissa väri­valinnoissa

### Print-CSS on toteutettu @media print -säännöllä
Tulostettava profiili -modaali näyttää tulosteessa **vain** modaalin sisällön A4:lle muotoiltuna, kaikki muu piilossa. `body > * { display: none !important }` + `.modal-overlay#print-modal-overlay.open { display: block !important }`.

### Autolinkitys
Sanaston 105 termiä linkitetään automaattisesti tekstien sisällä lazyloadingilla välilehti kerrallaan. `SKIP_SELECTORS`-listassa on kaikki elementit joita autolinkitys EI saa koskea (linkit, otsikot, syötekentät, modaalit, jne.). Jos lisäät uuden interaktiivisen elementin, **muista lisätä se SKIP_SELECTORS-listaan** jottei autolinkitys riko sitä.

## Sivuston rakenne

```
Yläbanner (sininen, "MD"-logo, otsikko, A−/A/A+ tekstikoon säädin)
├── Etusivu (6 korttia, 6 statia)
├── Mindmap (20 alatyyppi-laatikkoa, klikkaus → modaali)
├── Oirekysely (18 kysymystä, 10 alatyyppiä, 5 ranked tulosta + tx-cat-napit)
│   └── Tulosrivin alle "Tulosta profiili" -nappi → tulostusmodaali
├── Hoidot (34 stepiä id-attribuuttein, 7 osiota, suodatustila kyselyn kautta)
├── Arki (Suomi-pikalinkit 12 korttia + 12 kysymys-vastaus -accordionia)
├── Lähdekirjasto (43 lähdettä 8 kategoriassa)
└── Sanasto (105 termiä, sticky hakukenttä, aakkosnavigaatio)

Globaalit elementit:
- Akuutti kohtaus -kelluva nappi (oikea alalaita) → akuuttimodaali
- Tulostusmodaali (tulosten kautta)
- Termimodaali (autolinkitettyjen termien klikkauksesta)
```

## Versiohistoria (yhteenveto)

| Versio | Sisältö |
|--------|---------|
| v1–v7  | Mindmap, oirekysely, lähdekirjasto, sanasto, hoidot, etusivu rakennettu |
| v8     | NHS Design System -teema |
| v9–v12 | iOS Safari -yhteensopivuus, robusti tap-mekanismi |
| v13    | Hoitojen integraatio kyselyyn (tx-cat-napit, suodatustila) |
| v14    | Akuutti kohtaus -pikaohje |
| v15    | Arki-välilehti (12 kysymys-vastaus) |
| v16    | Suomi-pikalinkit (12 korttia, hätänumerot, vanhentuneen nimen korjaus) |
| v17    | Tekstikoon säädin (A−/A/A+, localStorage) |
| v18    | Tulostettava profiili (lääkärikäyntiä varten) |
| **v19**| **Sanaston haun parannus (current)** |

Versiot v1–v19 ovat olleet yksittäisinä tiedostoina (`meniere_alatyypit_vN.html`). Tästä eteenpäin Git-historia hoitaa versionhallinnan, ja työtiedosto on `index.html`.

## Testausmetodologia

Jokaiselle versiolle on tehty kattava JSDOM-pohjainen interaktiivinen testi:
- Testi luodaan tiedostoon `tests/test_vN.js`
- Ajo: `cd tests && node test_vN.js`
- Testit kattavat rakenteen, klikkaukset, tab-vaihdot, modaalit, näppäimistön, autolinkityksen ja edge-caset
- JSDOM-mock: `scrollIntoView`, `scrollTo`, `focus` — jotta jsdom ei kaadu

**Testien tila tällä hetkellä:** Yksittäisiä `test_vN.js`-tiedostoja ei ole siirretty Gittiin. Voit halutessasi:
1. Säilyttää nykyisen mallin (yksi testi per versio)
2. Konsolidoida yhdeksi `test.js`-tiedostoksi joka testaa nykyversiota
3. Jakaa testit useaan tiedostoon (rakenne, vuorovaikutus, akuutti, arki, jne.)

Suosittelen vaihtoehtoa 2 tai 3 — Git pitää historian, ei tarvitse `test_v20.js`, `test_v21.js`...

## Käytännön ohjeita Claude Codelle

### Kun lähdet tekemään muutosta
1. Lue tämä CLAUDE.md ja `PROJECT_STATE.md` kokonaan
2. Tarkista nykyinen tila: `git log --oneline -20`
3. Tee oma branch: `git checkout -b feature/<nimi>`
4. Tee muutokset `index.html`-tiedostoon
5. Aja `node tests/test.js` jos testitiedosto on olemassa
6. Commit: `git add index.html && git commit -m "<selkeä viesti>"`

### Tärkeää
- **Älä lisää ulkoisia riippuvuuksia** ilman painavaa syytä — sivusto on tarkoituksella self-contained
- **Älä riko iOS-yhteensopivuutta** — tarkista jokainen muutos
- **Älä unohda SKIP_SELECTORS-listaa** kun lisäät uusia interaktiivisia elementtejä
- **Print-CSS on @media print** — testaa selaimen tulostuksen esikatselulla, ei vain ruudulla
- **Sanaston päivitys vaatii myös autolinkityksen päivityksen** — TERM_INDEX rakennetaan GLOSSARY-listasta käynnistyksessä
- **NHS Design System -värit ovat CSS-muuttujia** (`--nhs-blue`, `--blue-50`, jne.) — käytä niitä, älä kovakoodaa hex-arvoja

### Mahdollisia jatkokehityskohteita
Katso `PROJECT_STATE.md`. Sivusto on tällä hetkellä toimiva ja täysin julkaisukelpoinen, joten kehitys on tästä eteenpäin "nice to have" -tasolla.

## Käyttäjän näkökulma

Tärkein käyttäjä on **läheinen henkilö** (~70 v), jolle haluat antaa selkeän, suomenkielisen, luotettavan tiedon Ménièren taudista. Suunnitteluvalinnat on tehty hänen ehdoillaan: iso teksti, selkeät napit, akuutti­kohtaus­pikaohje aina käden ulottuvilla, käytännön kysymykset arjessa (autoa, lentokone, ruoka, työ, läheiset, talous), suomalaiset palvelut yhdellä klikkauksella.

Tieto on tieteellisesti tarkkaa: Frejo et al. 2016/2017, Bächinger & Eckhard 2019/2024, Chari et al. 2025, Yuan et al. 2025, AAO-HNS 2020, Käypä hoito. Mutta esitysmuoto on selkokielinen, ei akateeminen.

## Lähteet ja luotettavuus

Sivuston tärkeimmät lähteet ovat **vertaisarvioituja** ja **ajantasaisia**. Älä lisää lähteitä jotka ovat:
- Yli 10 vuotta vanhoja (paitsi historiallisia perusartikkeleita)
- Predatory journals (Beall's list, MDPI:n osa lehtiä, jne.)
- Yksittäisten lääketeollisuuden sponsoroimien tutkimusten ainoa peruste
- Sosiaalisen median sisältöä, blogeja, mielipidekirjoituksia

Suomalainen Käypä hoito on ensisijainen luotettava lähde suomeksi.
