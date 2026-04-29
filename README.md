# Ménière-tietopalvelu

Suomenkielinen interaktiivinen tietosivusto Ménièren taudista. Tarkoitettu potilaille ja heidän läheisilleen.

## Sisältö

- **Etusivu** — johdanto ja navigointi
- **Mindmap** — tunnistetut alatyypit visuaalisena karttana
- **Oirekysely** — 18-kysymyksinen alatyyppi-arvio + räätälöidyt hoitosuositukset
- **Hoidot** — 34 hoitomuotoa kategorioittain (lääkkeet, leikkaukset, itsehoito, tulevaisuuden hoidot)
- **Arki** — käytännön kysymyksiä (ajaminen, matkustaminen, ruoka, työ, vertaistuki) + Suomi-pikalinkit
- **Lähdekirjasto** — 43 vertaisarvioitua tieteellistä lähdettä
- **Sanasto** — 105 termin selkokielinen sanasto, autolinkitys teksteissä

Sivustolla on lisäksi:
- **Akuutti kohtaus -pikaohje** (kelluva nappi sivun oikeassa alalaidassa)
- **Tekstikoon säädin** (A−/A/A+ yläbannerissa)
- **Tulostettava profiili** lääkärikäyntiä varten (kyselyn tulosten kautta)

## Tekninen toteutus

Yksittäinen `index.html`-tiedosto ilman ulkoisia riippuvuuksia.

- HTML, CSS ja JavaScript samassa tiedostossa
- Ei build-vaihetta, ei `node_modules`
- iOS Safari -yhteensopiva
- WCAG 2.2 AA -saavutettavuus
- NHS Design System v10 -visuaalinen kieli
- Toimii myös offline kun sivu on kerran ladattu

## Julkaisu

### Vaihtoehto 1: Netlify Drop (helpoin)

1. Mene osoitteeseen https://app.netlify.com/drop
2. Vedä `index.html` selaimen ikkunaan
3. Sivusto julkaistaan välittömästi ja saat URL:n
4. Voit muuttaa aliaksen ilmaisellä Netlify-tilillä

### Vaihtoehto 2: GitHub Pages

1. Push tämä repo GitHubiin
2. Settings → Pages → Source: `main` branch, root
3. URL: `https://<käyttäjä>.github.io/<repo-nimi>/`

### Jakaminen WhatsAppissa

WhatsAppin in-app WebView iOS:llä rajoittaa JavaScriptiä. Sivusto pitää julkaista verkkoon (URL), jonka käyttäjä avaa **oikeassa selaimessa** (Safari, Chrome). Linkin klikkaaminen WhatsAppissa avaa yleensä in-app-katselijan jossa sivusto ei välttämättä toimi — pyydä vastaanottajaa avaamaan linkki ulkoisessa selaimessa (... → "Avaa Safarissa").

## Lähteet ja vastuuvapauslauseke

Tieto perustuu vertaisarvioituihin tieteellisiin julkaisuihin (Frejo et al. 2016/2017, Bächinger & Eckhard 2019/2024, Chari et al. 2025, Yuan et al. 2025, AAO-HNS 2020) ja Käypä hoito -suositukseen.

**Tämä on opetuksellinen materiaali, ei lääketieteellistä neuvontaa.** Hoitopäätökset tehdään aina KNK-erikoislääkärin arvion perusteella.

## Kehittäminen

Katso `CLAUDE.md` Claude Code -istuntojen brieffaukseksi ja `PROJECT_STATE.md` projektin yksityiskohtaiseksi tilaksi ja jatkokehitysideoiksi.

```bash
# Avaa sivusto paikallisesti
open index.html
# tai
python3 -m http.server 8000  # http://localhost:8000

# Aja testit (kun ne on lisätty)
node tests/test.js
```

## Lisenssi

Henkilökohtainen oppimisprojekti. Sisältö perustuu julkisesti saatavilla oleviin tieteellisiin lähteisiin. Ei kaupalliseen käyttöön.
