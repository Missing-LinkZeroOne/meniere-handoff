# Ménière-tietopalvelu — DALL-E 3 -kuvitusprompit

> **Käyttöohje:** Tämä tiedosto on suunniteltu annettavaksi **kokonaisuudessaan** DALL-E 3:lle (esim. ChatGPT Plus / Image Generator -istunnossa). Liitä koko tiedoston sisältö ensimmäiseen viestiin, ja DALL-E käsittelee jokaisen kuvan järjestyksessä.
>
> Tiedostot on tarkoitus tallentaa nimillä `01-etusivu-hero.webp`, `07-oirekysely-hero.webp` jne. Sivuston `images/`-kansioon. Ne korvaavat nykyiset placeholder-SVG:t, joiden HTML-kommentteihin (`AI-IMAGE-PROMPT START` / `END`) on jo upotettu sama prompti.
>
> Sivusto: https://missing-linkzeroone.github.io/meniere-handoff/
> Repo: https://github.com/Missing-LinkZeroOne/meniere-handoff

---

## OSA 1 — YLEISOHJE (System Prompt / Brand Guide)

**Liitä tämä osio ensimmäiseen viestiin DALL-E:lle, ennen yksittäisiä prompteja.**

```
You are generating a series of editorial watercolor illustrations for a Finnish health information website about Ménière's disease.

═══ AUDIENCE & TONE ═══
Target reader: Finnish-speaking adult, ~70 years old, or their family members.
Tone: warm, calm, dignified, hopeful, capable. NEVER fearful, clinical, or victimizing.
The site emphasizes that Ménière's disease is manageable and that patients live full lives.

═══ VISUAL STYLE (apply to ALL images) ═══
• Style: editorial watercolor illustration with subtle ink line work
• Aesthetic: Scandinavian / Nordic minimalism, NHS Design System v10 inspired
• Quality: clean, modern, magazine-cover quality
• Texture: soft watercolor washes, visible brush texture, not photorealistic
• Lines: gentle ink contours where needed, never harsh
• Light: soft natural light, often golden hour or diffuse daylight
• Composition: spacious, uncluttered, clear focal point

═══ COLOR PALETTE (use consistently) ═══
Primary:    NHS Blue       #005EB8   (anchor color, used sparingly)
Light:      NHS Light Blue #41B6E6   (water, sky, calm accents)
Nature:     NHS Green      #007F3B   (foliage, foreground)
Warm:       Warm Yellow    #FFF7BF   (sunlight, paper, warmth)
            Amber          #FFE3E0   (skin tones, warm accents)
Neutral:    Pale Grey      #F0F4F5   (paper, background)
            Medium Grey    #5b6770   (silhouettes, ground)
Avoid:      pure black, harsh red except for highlight (#DA291C used very sparingly)

═══ FINNISH SETTING ═══
When showing landscape or interiors, use specifically Finnish elements:
• Birch trees (koivu) with white-grey trunks and small green leaves
• Pine forests (mänty)
• Calm lakes (järvi) with subtle ripples
• Light wood floors and large windows in interiors
• Summer cottage (mökki) silhouettes in distance for outdoor scenes
• Moderate, not dramatic, scenery — peaceful, not majestic

═══ PEOPLE (when shown) ═══
• Age: predominantly 50–70, gender-neutral or mixed
• Body language: calm, present, not anxious
• Faces: serene, gentle, never expressing pain or fear
• Clothing: comfortable, casual, not medical-looking
• Diversity: subtle, natural — no overt diversity tokenism

═══ MEDICAL CONTEXT (subtle) ═══
• NO visible medical equipment except where explicitly required
• NO surgical/clinical scenes
• Inner ear motifs (cochlea spirals, semicircular canals) may appear VERY subtly as decorative elements (e.g., reflected in water ripples) — never the main subject
• If a doctor is shown, white coat is OPTIONAL; emphasize dialogue and equality, not authority

═══ TEXT IN IMAGES ═══
NO TEXT in images. Letters, words, numbers, signs, books with readable text — all forbidden.
(If the brief specifies showing a notebook page or dictionary, leave the text visually abstract — squiggles or fade-out marks suggesting text, never readable.)

═══ TECHNICAL ═══
• Output: highest quality DALL-E 3 setting, "natural" style preferred over "vivid"
• Aspect ratio: follow each individual brief precisely
• Background: usually soft, gradient or subtle texture, never busy
• Negative space: respected, breathing room around subject

When you are ready, I will provide 11 individual image briefs. Generate each one in turn following these guidelines.
```

---

## OSA 2 — YKSITTÄISET PROMPTIT (11 kuvaa)

> Pyydä DALL-E:tä generoimaan kuvat yksi kerrallaan. Annan jokaisen promptin valmiiksi muotoiltuna — sisältää tiedostonimen ja mittasuhteen.

---

### 🖼 Kuva 1 / 11 — IMG-01: Etusivun hero

**Tiedostonimi:** `01-etusivu-hero.webp`
**Mitat:** 1200 × 320 px (3.75:1 panoramic)
**Sijainti sivulla:** Etusivu-välilehti, otsikon yläpuolella

```
A serene panoramic illustration in soft watercolor style showing a calm Finnish lake at dawn, with gentle ripples on the water surface. The composition is wide (3.75:1 ratio). In the foreground, faint subtle outlines of a stylized inner ear (cochlea spiral and three semicircular canals) are integrated into the water ripples, almost like reflections, very subtly visible. Color palette: soft pastel blues (#41B6E6, #005EB8), warm yellow morning light, pale grey backgrounds. No text, no people, no medical symbols visible explicitly. Mood: hopeful, peaceful, contemplative. Suitable as hero image for a Finnish medical information website. Style: editorial illustration, watercolor with ink lines, minimalist.
```

**Suomenkielinen alt-teksti:**
> Rauhallinen suomalainen järvinäkymä aamuhämärässä, jonka aaltokuvioissa näkyy hienovaraisia sisäkorvan ääriviivoja kuvituksenomaisena yhdistelmänä.

---

### 🖼 Kuva 2 / 11 — IMG-07: Oirekysely-hero

**Tiedostonimi:** `07-oirekysely-hero.webp`
**Mitat:** 1000 × 250 px (4:1 panoramic)
**Sijainti sivulla:** Oirekysely-välilehti, otsikon yläpuolella

```
A panoramic warm illustration showing the act of self-reflection and symptom tracking. Foreground: a hand holding a pen, writing in a small notebook on a wooden desk. Background: soft watercolor of a thoughtful person (50+ years old, gender-neutral) looking out a window in a Finnish home, calm light. Aspect ratio 4:1. Color palette: soft pastels, warm whites, gentle blue (#41B6E6) accents. No medical equipment visible. Mood: contemplative, gentle, encouraging. Style: editorial watercolor illustration with subtle ink lines, minimalist.
```

**Suomenkielinen alt-teksti:**
> Lämmin kuvituskuva pöydällä makaavasta muistivihkosta ja kynästä, taustalla mietteliäs henkilö ikkunan ääressä — kuvataan kohtaa, jossa pysähdytään pohtimaan omia oireita.

---

### 🖼 Kuva 3 / 11 — IMG-09: Hoidot-hero

**Tiedostonimi:** `09-hoidot-hero.webp`
**Mitat:** 1000 × 240 px (25:6 panoramic)
**Sijainti sivulla:** Hoidot-välilehti, otsikon yläpuolella

```
A panoramic warm illustration showing a doctor and patient in conversation, viewed from a soft side angle. They are seated in a modern Finnish clinic — bright, light-filled space with large windows showing soft greenery outside. The scene emphasizes equality and dialogue: both are leaning toward each other, the doctor (50s, gender-neutral, white coat optional) is listening, the patient (60s, calm) is speaking. No medical equipment visible. Aspect ratio 25:6. Color palette: soft pastels, NHS-blue (#005EB8) accents, warm whites, gentle greens. Mood: collaborative, hopeful, professional yet warm. Style: editorial illustration, watercolor with subtle ink lines, minimalist.
```

**Suomenkielinen alt-teksti:**
> Lääkäri ja potilas keskustelevat valoisalla suomalaisella vastaanotolla. Tunnelma on yhteistyöhenkinen — molemmat kuuntelevat toisiaan, ei kliinistä etäisyyttä.

---

### 🖼 Kuva 4 / 11 — IMG-13: Arki-hero

**Tiedostonimi:** `13-arki-hero.webp`
**Mitat:** 1000 × 280 px (25:7 panoramic)
**Sijainti sivulla:** Arki-välilehti, otsikon yläpuolella (yläosa, ennen subtab-navigaatiota)

```
A panoramic warm watercolor illustration depicting Finnish daily life with quiet resilience. A pair of people walking together along a serene Finnish lake-side path in summer, viewed from behind. They are dressed in comfortable clothing, one with a cane optional but not emphasized. Around them: birch trees, calm water, soft sunlight, distant view of a Finnish summer cottage. Both walking at peaceful pace. Aspect ratio 25:7. Color palette: soft greens, blues (#41B6E6), warm yellows, pale earthtones. No medical references. Mood: enduring, peaceful, life continues. Style: editorial watercolor illustration with subtle ink lines.
```

**Suomenkielinen alt-teksti:**
> Lämmin kuvituskuva pareista, jotka kävelevät yhdessä rauhallisesti suomalaisen järven rantapolulla kesällä. Tunnelma: arki jatkuu, elämä on hallittavissa.

---

### 🖼 Kuva 5 / 11 — IMG-14: Q&A "Voinko ajaa autoa?"

**Tiedostonimi:** `14-arki-ajaminen.webp`
**Mitat:** 400 × 250 px (8:5)
**Sijainti sivulla:** Arki / "Voinko ajaa autoa Suomessa?" -accordionin sisällä, vasemmalla, teksti kiertää

```
A warm illustration showing the dashboard view of a car driving on a calm Finnish countryside road. Driver's hand visible on the steering wheel (middle-aged hand, calm grip). View through windshield: open road with birch trees, soft Finnish landscape, golden hour light. Color palette: warm pastels, NHS-blue (#005EB8) accents subtle. No tension, calm and capable. Aspect ratio 8:5. Style: editorial watercolor.
```

**Suomenkielinen alt-teksti:**
> Auton ratin ja tien näkymä — kuljettajan käsi rauhallisesti ratissa, edessä avoin suomalainen maaseutumaisema.

---

### 🖼 Kuva 6 / 11 — IMG-15: Q&A "Voinko lentää?"

**Tiedostonimi:** `15-arki-lentaminen.webp`
**Mitat:** 400 × 250 px (8:5)
**Sijainti sivulla:** Arki / "Voinko lentää lentokoneella?" -accordionin sisällä

```
A warm watercolor illustration showing the view from an airplane window. Foreground: a small water bottle resting on a fold-out tray. Through the window: soft white clouds, blue sky, peaceful flight. The composition emphasizes calm preparation. Color palette: soft blues (#41B6E6), warm whites, gentle pastels. Aspect ratio 8:5. Style: editorial illustration, no people visible directly.
```

**Suomenkielinen alt-teksti:**
> Lentokoneen ikkunan näkymä, edessä pieni vesipullo lentokoneen pöydällä — kuvataan rauhallista lentomatkaa hyvin valmistautuneena.

---

### 🖼 Kuva 7 / 11 — IMG-16: Q&A "Mitä saan syödä?"

**Tiedostonimi:** `16-arki-ruoka.webp`
**Mitat:** 400 × 280 px (10:7)
**Sijainti sivulla:** Arki / "Mitä saan syödä? Mitä kannattaa välttää?" -accordionin sisällä

```
A warm overhead illustration of a balanced Finnish lunch table. On a wooden table: a plate with grilled salmon, steamed vegetables, baked potatoes, fresh greens. Beside the plate: a glass of water, a slice of whole-grain rye bread. Soft natural light. Color palette: warm earthtones, fresh greens, soft whites. Style: editorial watercolor illustration, no people. Mood: healthy, capable, Finnish home cooking. Aspect ratio 10:7.
```

**Suomenkielinen alt-teksti:**
> Suomalainen tasapainoinen lounaspöytä: lohifile, höyrytetyt kasvikset, perunat, salaatti, vesilasi ja pala ruisleipää.

---

### 🖼 Kuva 8 / 11 — IMG-17: Q&A "Voinko liikkua?"

**Tiedostonimi:** `17-arki-liikunta.webp`
**Mitat:** 400 × 280 px (10:7)
**Sijainti sivulla:** Arki / "Voinko liikkua ja harrastaa?" -accordionin sisällä

```
A warm watercolor illustration showing two people aged 50-65 doing gentle Nordic walking on a Finnish forest path. They have walking poles and appropriate outdoor clothing. Background: pine trees, soft forest light, peaceful path. Both walking at measured pace, smiling slightly. Color palette: soft greens, warm yellows, pale earthtones. Style: editorial watercolor with ink lines. Aspect ratio 10:7.
```

**Suomenkielinen alt-teksti:**
> Kaksi 50–65 -vuotiasta sauvakävelijää suomalaisella metsäpolulla, rauhallinen tahti, hymyilevät hieman.

---

### 🖼 Kuva 9 / 11 — IMG-18: Lähdekirjasto-hero

**Tiedostonimi:** `18-lahdekirjasto-hero.webp`
**Mitat:** 1000 × 220 px (50:11 panoramic)
**Sijainti sivulla:** Lähdekirjasto-välilehti, otsikon yläpuolella

```
A panoramic warm illustration of an academic study desk. Foreground: open scientific journals and books, with subtle glimpses of charts and data on the visible pages (NO readable text — only abstract shapes resembling charts). A glass of water, reading glasses, a fountain pen, a small notebook. Soft natural light from the side. Color palette: warm browns, cream whites, subtle NHS-blue (#005EB8) on book covers. Aspect ratio 50:11. No people. Style: editorial watercolor illustration. Mood: studious, careful, illuminated.
```

**Suomenkielinen alt-teksti:**
> Tieteellisten lehtien ja kirjojen lähikuva työpöydällä, taustalla lukulasit ja kynä. Tunnelma: huolellinen tutkimustyö.

---

### 🖼 Kuva 10 / 11 — IMG-19: Blogi-hero

**Tiedostonimi:** `19-blogi-hero.webp`
**Mitat:** 1000 × 220 px (50:11 panoramic)
**Sijainti sivulla:** Blogi-välilehti, otsikon yläpuolella

```
A panoramic warm illustration showing a cozy reading scene. A person (50+ years, gender-neutral) sitting in a comfortable chair, reading on a tablet, with a coffee cup nearby. Soft afternoon light, Finnish home setting (light wood floor, large window, simple Scandinavian interior). Color palette: warm earthtones, soft blues (#41B6E6), gentle whites. Aspect ratio 50:11. Style: editorial watercolor illustration, peaceful mood.
```

**Suomenkielinen alt-teksti:**
> Henkilö istuu mukavassa nojatuolissa lukemassa tablettia, kahvikuppi vieressä, suomalainen kotimiljöö, rauhallinen iltapäiväkohtaus.

---

### 🖼 Kuva 11 / 11 — IMG-23: Sanasto-hero

**Tiedostonimi:** `23-sanasto-hero.webp`
**Mitat:** 1000 × 180 px (50:9 panoramic, matalampi)
**Sijainti sivulla:** Sanasto-välilehti, otsikon yläpuolella

```
A panoramic warm illustration showing an open dictionary or encyclopedia, with colorful sticky notes marking pages (yellow, blue, pink). A magnifying glass placed on top of one page. Soft afternoon light, warm tones. The text on the dictionary pages is suggested with abstract squiggle marks (NO readable text). Color palette: cream whites, soft blues (#41B6E6), warm yellows for sticky notes. No people. Style: editorial watercolor illustration. Aspect ratio 50:9. Mood: curious, exploring, careful study.
```

**Suomenkielinen alt-teksti:**
> Avoin sanakirja, jossa värilliset paperilaput merkitsevät sivuja, ja suurennuslasi yhden sivun päällä. Tunnelma: utelias selailu.

---

## OSA 3 — TOIMITUS

Kun DALL-E on generoinut kuvat:

1. **Tallenna jokainen kuva** sen ehdotetulla tiedostonimellä (esim. `01-etusivu-hero.webp`).
   - DALL-E tuottaa yleensä PNG/JPG. Voit muuntaa ne WebP-formaattiin esim. https://squoosh.app -työkalulla (laatu 80, lossy).
   - Vaihtoehtoisesti voit jättää PNG/JPG ja muuttaa filename-päätteen tarvittaessa.

2. **Lataa tiedostot Git-repon `images/`-kansioon:**
   ```
   meniere-handoff/
   └── images/
       ├── 01-etusivu-hero.webp
       ├── 07-oirekysely-hero.webp
       ├── 09-hoidot-hero.webp
       ├── 13-arki-hero.webp
       ├── 14-arki-ajaminen.webp
       ├── 15-arki-lentaminen.webp
       ├── 16-arki-ruoka.webp
       ├── 17-arki-liikunta.webp
       ├── 18-lahdekirjasto-hero.webp
       ├── 19-blogi-hero.webp
       └── 23-sanasto-hero.webp
   ```

3. **Anna Claude Codelle viesti**: *"Kuvat ovat valmiina images/-kansiossa. Korvaa placeholder-SVG:t img-elementeillä jokaisen AI-IMAGE-PROMPT-kommentin REPLACE-WITH-WHEN-READY -snippetillä."*

   Claude Code etsii HTML:stä jokaisen `AI-IMAGE-PROMPT START` -kommentin, hakee `REPLACE-WITH-WHEN-READY:` -kohdan ja korvaa sen alla olevan placeholder-SVG:n vastaavalla `<img>`-tagilla.

4. **Lopullinen verifiointi:** Sivuston pitäisi näyttää lämpimämmältä ja vähemmän geneeriseltä kuin nyt. Placeholder-SVG:t katoavat, ja AI-akvarellit tuovat tunnelman.

---

## OSA 4 — KEHITYSKEHTONOT (myöhempää varten)

Jos jokin kuva ei toimi DALL-E:n kanssa hyvin, voit kokeilla:

- **Vaihtaa formaattia:** *"editorial watercolor"* → *"flat illustration"* tai *"minimal vector art"*
- **Lisätä spesifisyyttä:** mainita esim. tunnetut taiteilijat (*"in the style of editorial illustration similar to The New Yorker covers"*)
- **Tarkentaa kuvasuhdetta:** DALL-E 3 tukee 1024×1024, 1024×1792, 1792×1024 → joudut ehkä rajaamaan / venyttämään lopputulosta sopivaksi
- **Korjata yksityiskohtia:** *"Make the lake more prominent"*, *"Remove the figure in the background"*

Anatomisia diagrammeja (IMG-04, 05, 06, 10, 20, 21, 22) **ei kannata generoida AI:lla** — niiden inline SVG -versiot toimivat luotettavammin sivustolla. Logo (IMG-25) ja Venn-diagrammi (IMG-03) ovat samoin valmiita SVG-muodossa.

---

**Versio:** 1.0 — luotu 2026-04-29
**Sivuston versio:** v20-tasolla (commit `e529010` jälkeen)
**Yhteensä kuvia:** 11 generoitavaa + 13 valmista inline SVG -kuvaa
