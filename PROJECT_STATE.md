# Projektin tila — Ménière-tietopalvelu

Tämä dokumentti kuvaa projektin nykyisen tilan yksityiskohtaisesti ja listaa mahdollisia jatkokehityskohteita.

## Nykyinen tila (v19)

### Toiminnot — kaikki valmiit ja testattu

| Ominaisuus | Tila | Testattu |
|------------|------|----------|
| Etusivu (6 korttia, 6 statia) | ✓ | JSDOM |
| Mindmap (20 alatyyppi-laatikkoa, modaalit) | ✓ | JSDOM |
| Oirekysely (18 kysymystä, 10 alatyyppiä) | ✓ | JSDOM |
| Tulosrivin tx-cat-napit ja suodatustila | ✓ | JSDOM |
| Hoidot (34 stepiä id-attribuuttein, 7 osiota) | ✓ | JSDOM |
| Arki-välilehti (12 kysymys-vastaus -accordionia) | ✓ | JSDOM |
| Suomi-pikalinkit (12 korttia + hätänumerot) | ✓ | JSDOM |
| Lähdekirjasto (43 lähdettä 8 kategoriassa) | ✓ | JSDOM |
| Sanasto (105 termiä, sticky haku) | ✓ | JSDOM |
| Autolinkitys (lazy load välilehti kerrallaan) | ✓ | JSDOM |
| Akuutti kohtaus -pikaohje | ✓ | JSDOM |
| Tekstikoon säädin (A−/A/A+) | ✓ | JSDOM |
| Tulostettava profiili (lääkärikäyntiä varten) | ✓ | JSDOM |
| Sanaston haun parannus (sticky, status, clear) | ✓ | JSDOM |
| iOS Safari -yhteensopivuus | ✓ | Manuaalinen |
| Print-CSS (@media print) | ✓ | Manuaalinen |
| WCAG 2.2 AA -kontrastit | ✓ | Visuaalinen tarkistus |

### Tiedoston koko

- `index.html`: ~331 kt (yksi tiedosto)
- ~6 800 riviä yhteensä (HTML + CSS + JS + sisältö)
- ~120 kt JavaScript (sisältäen sanaston ja modaalisisällöt)

### Selaintuki

| Selain | Tila |
|--------|------|
| Chrome (uusin) | ✓ |
| Firefox (uusin) | ✓ |
| Safari macOS | ✓ |
| Safari iOS 16.4+ | ✓ |
| Safari iOS < 16.4 | ✓ (capture group -syntaksi, ei lookbehindiä) |
| Edge | ✓ |
| WhatsApp in-app WebView | ⚠ Rajoittaa JS:ää, suositellaan ulkoinen selain |

## Tunnetut puutteet ja kompromissit

### Tarkoituksellisia kompromisseja
- **Yksi tiedosto** — vaikeampi navigoida koodieditorissa, mutta helpompi julkaista ja jakaa
- **Ei build-vaihetta** — ei minifikaatiota, mutta ei myöskään riippuvuuksien hallintaa
- **Suomi yksin** — käyttäjäkohderyhmä on suomenkielinen, ei tarvetta i18n:lle
- **Ei analytiikkaa** — yksityisyysperiaate, ei seurata käyttäjiä
- **Ei evästeitä** — vain `localStorage` tekstikoolle (try/catch-suojattu)

### Mahdollisia ongelmia
- **Sanaston päivitys vaatii käsityötä** — kaikki 105 termiä ovat HTML-tiedoston sisällä `GLOSSARY`-vakiona. Jos termi pitää päivittää, etsi se ja muokkaa paikallaan.
- **Hoito-tiedot kahdessa paikassa** — itse hoito-stepit HTML:ssä (rikas teksti) ja `SUBTYPE_TREATMENTS`-mappaus JS:ssä (vain id:t). Pidettävä synkronoituna.
- **Modaalisisältö on JS-objektissa `MODAL_CONTENT`** — ei HTML:ssä. Modaalit rakennetaan dynaamisesti.
- **Ei automaattista regressio-testausta CI:ssä** — testit ajetaan käsin

## Mahdollisia jatkokehityskohteita

Listattu **prioriteettijärjestyksessä** sekä **työmäärä-arvio**.

### Korkea prioriteetti

#### 1. Testit Gittiin ja CI-pipeline
**Työmäärä:** 2–4 h
- Konsolidoi nykyiset `test_vN.js`-tiedostot yhdeksi `tests/test.js` tai useaksi temaattiseksi tiedostoksi
- Lisää `package.json` jossa `npm test` ajaa testit
- Lisää GitHub Actions -workflow joka ajaa testit jokaiselle PR:lle
- Vaikkei `npm install` -riippuvuuksia ole HTML-sivulla, testaukseen tarvitaan `jsdom`

```bash
npm init -y
npm install --save-dev jsdom
# tests/test.js käyttää jsdomia
```

#### 2. Manuaalinen QA-tarkistuslista
**Työmäärä:** 1 h
- Luo `QA_CHECKLIST.md` jossa lista asioista jotka pitää tarkistaa manuaalisesti ennen julkaisua:
  - iPhone 13+ Safari (uusi/vanha iOS)
  - Android Chrome
  - Tekstin koonsäätö järjestelmätasolla
  - Tulostuksen esikatselu (paperilla)
  - WhatsApp-jako (linkin avaaminen ulkoisessa selaimessa)
  - Tummateemamoodi (`prefers-color-scheme: dark`)

### Keskitason prioriteetti

#### 3. Akuuttinapin parempi sijoittelu mobiilissa
**Työmäärä:** 1 h
- Akuuttinappi on kelluva oikeassa alalaidassa. Mobiilissa se voi peittää sivun loppuosan kun käyttäjä rullaa alas.
- Mahdollinen ratkaisu: nappi liukuu pieneksi kuvakkeeksi kun rullaa, kasvaa takaisin kun pysähtyy

#### 4. Oirepäiväkirja (offline)
**Työmäärä:** 6–10 h
- Käyttäjä voi merkitä päivämääriä, kohtausten kestoja, vakavuus-arvioita ja mahdollisia laukaisijoita
- Tallennetaan localStorageen (try/catch-suojattu, ei lähetetä mihinkään)
- Tulostettava versio joka voi mennä lääkärikäyntiin
- HUOMAA: Tämä on iso ominaisuus joka voi venyttää tiedoston hyvin isoksi. Harkitse erillistä sivua tai modaalia.

#### 5. Sanaston laajentaminen
**Työmäärä:** 2–4 h
- Käy läpi 105 termiä — onko vielä puuttuvia?
- Erityisesti uudempi tutkimustieto (Chari et al. 2025, Yuan et al. 2025) voi olla termejä jotka eivät ole vielä sanastossa
- Lisää termit `GLOSSARY`-vakioon, autolinkitys päivittyy automaattisesti

#### 6. Lähdekirjaston suodatus
**Työmäärä:** 3–5 h
- Lähdekirjastossa on 43 lähdettä 8 kategoriassa
- Suodatus kategorian, vuoden tai avainsanan mukaan
- Ei ole vielä aakkosellinen järjestys / suosittelujärjestys -valinta

### Matala prioriteetti

#### 7. Kuvitukset ja ikonit
**Työmäärä:** vaihteleva (4–20 h)
- Anatomisia kaavioita sisäkorvasta (selkokielisiä, ei tieteellisiä piirroksia)
- Hoito-osioon ikonit (lääke, leikkaus, itsehoito)
- Mindmappiin värillisiä ikoneita per alatyyppi
- HUOMAA: Tämä venyttää tiedostoa jos kuvat ovat inline base64. Harkitse SVG-spriteä.

#### 8. PWA-tukien lisääminen
**Työmäärä:** 4–6 h
- Service worker → toimii offline kerran ladattuna
- `manifest.json` → asennettavissa kotinäytölle
- HUOMAA: Tämä vaatii että sivusto on omalla domainilla (ei pelkkä Netlify-aliasdomaini)

#### 9. Useamman kielen tuki
**Työmäärä:** suuri (20+ h)
- Tällä hetkellä vain suomeksi
- Englanninkielinen versio voisi olla hyödyllinen
- Vaatii i18n-järjestelmän tai erillisen `index_en.html`-tiedoston

#### 10. Käyttäjäkokemuksen lokitus (anonyymi)
**Työmäärä:** 4–6 h
- Mitä välilehtiä klikataan eniten?
- Pääsevätkö käyttäjät kyselyn loppuun?
- Onko jossakin vaiheessa drop-off?
- HUOMAA: Tämä on ristiriidassa "ei evästeitä, ei analytiikkaa" -periaatteen kanssa. Päätös tarvitaan.

## Mahdollisia regressio-riskejä

Asioita jotka voivat helposti hajota tulevien muutosten yhteydessä:

1. **Autolinkitys** — kun lisätään uusi interaktiivinen elementti, se pitää lisätä `SKIP_SELECTORS`-listaan
2. **Modaalien Esc-näppäinkäsittely** — useita modaaleja on, ja Esc-tapahtumien bubbling pitää käsitellä oikein
3. **Print-CSS** — kun lisätään uusia kelluvia elementtejä, ne pitää piilottaa `@media print` -säännöllä
4. **Tab-vaihto ja lazyLinkPanel** — uusien välilehtien autolinkitys pitää lisätä `lazyLinkPanel`-funktioon
5. **iOS-yhteensopivuus** — uusien interaktiivisten elementtien pitää toimia iOS Safarissa (touch-action, role-attribuutit)

## Versiointi tästä eteenpäin

Käytä Gitin versionhallintaa:
```bash
git log --oneline -20
git tag v20.0  # kun julkaistaan uusi versio
git push origin v20.0
```

Älä luo enää `meniere_alatyypit_vN.html`-tiedostoja — käytä `index.html` ja Git-historiaa.

## Yhteystiedot ja jakaminen

- Henkilökohtainen oppimisprojekti
- Sisältö perustuu julkisesti saatavilla oleviin tieteellisiin lähteisiin
- Voi jakaa vapaasti henkilökohtaisessa käytössä
- Ei kaupalliseen käyttöön ilman erillistä lupaa
