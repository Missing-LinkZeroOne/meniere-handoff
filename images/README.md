# Kuvat — Ménière-tietopalvelu

Tässä kansiossa olevat kuvat on tuotettu **OpenAI DALL·E 3** -mallilla 29.4.2026 osana sivuston kuvitusprojektia. Kuvat noudattavat sivuston brändiopasta (NHS Design System v10 -värit, lämmin akvarelli/editorial-tyyli, suomalainen luonto, ei kasvoja tai brändejä).

## Kuvalista

| Tiedosto | Käyttöpaikka | Mitat |
|----------|--------------|-------|
| `01-etusivu-hero.webp` | Etusivu — hero | 1200 × 320 |
| `07-oirekysely-hero.webp` | Oirekysely — hero | 1000 × 250 |
| `09-hoidot-hero.webp` | Hoidot — hero | 1000 × 240 |
| `13-arki-hero.webp` | Arki — hero | 1000 × 280 |
| `14-arki-ajaminen.webp` | Arki Q&A — Voinko ajaa autoa? | 400 × 250 |
| `15-arki-lentaminen.webp` | Arki Q&A — Voinko lentää? | 400 × 250 |
| `16-arki-ruoka.webp` | Arki Q&A — Mitä saan syödä? | 400 × 280 |
| `17-arki-liikunta.webp` | Arki Q&A — Voinko liikkua? | 400 × 280 |
| `18-lahdekirjasto-hero.webp` | Lähdekirjasto — hero | 1000 × 220 |
| `19-blogi-hero.webp` | Blogi — hero | 1000 × 220 |
| `23-sanasto-hero.webp` | Sanasto — hero | 1000 × 180 |

## Lisensointi

OpenAI:n käyttöehtojen ([Terms of Use, Section 3 — Content](https://openai.com/policies/terms-of-use)) mukaan käyttäjä omistaa generoimiensa kuvien oikeudet ja saa käyttää niitä myös kaupallisesti. Tämän projektin kuvat on lisensoitu sivuston omistajalle (Missing-LinkZeroOne) ja niitä saa käyttää tämän palvelun yhteydessä vapaasti.

## Tekninen tieto

- **Formaatti:** WebP (laajalti tuettu, hyvä pakkaus)
- **Koko yhteensä:** ~6,3 MB
- **Lazy-load:** kaikilla `<img>`-tageilla on `loading="lazy"`
- **Saavutettavuus:** jokaisella kuvalla on suomenkielinen `alt`-teksti

## Promptit

Kuvien generointiin käytetyt promptit ovat tallessa repon juuressa tiedostossa `DALL_E_PROMPTS.md`. Sieltä löytyy myös brändiopas (Brand Guide), jota käytettiin DALL·E:n system-promptina ennen yksittäisiä kuvapyyntöjä.

## Päivitys

Jos kuvia uusitaan tai lisätään:

1. Päivitä myös `index.html`:n `<img>`-tagit (etsi `AI-IMAGE-PROMPT`-kommentteja)
2. Päivitä tämä `README.md`
3. Lisää uusi prompti `DALL_E_PROMPTS.md`-tiedostoon
4. Tarkista alt-tekstien suomenkielisyys ja kuvaavuus

---

Versio: v20.0 — kuvitus käytössä, 29.4.2026
