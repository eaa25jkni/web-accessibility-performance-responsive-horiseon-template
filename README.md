# Horiseon

# Web Accessibility, Web Performance og Responsive Webdesign

**Semester:** 3. semester

> Opgaven kan løses med Visual Studio Code, Google Chrome, Chrome DevTools, Lighthouse, tastatur og eventuelt HeadingsMap.

---

## Opgavebeskrivelse

I denne øvelse skal du arbejde med et eksisterende website for det digitale bureau **Horiseon**.

Horiseon arbejder blandt andet med:

- Search Engine Optimization
- Online Reputation Management
- Social Media Marketing
- Lead Generation
- Brand Awareness
- Cost Management

Du skal **ikke bygge websitet om fra bunden**.

Formålet er, at du lærer at analysere og forbedre eksisterende HTML og CSS trin for trin.

Opgaven består af tre dele:

```text
DEL 1
Web Accessibility
        ↓
DEL 2
Web Performance
        ↓
DEL 3
Responsive Webdesign med CSS Flexbox
```

Du skal bruge **Chrome DevTools** og **Lighthouse** til at dokumentere effekten af dine ændringer.

> **Vigtigt:** Foretag ikke alle ændringer på én gang. Test løbende, så du kan se, hvilken betydning de enkelte ændringer har.

---

## Projektmappe

Starterprojektet består af:

```text
project/
│
├── README.md
├── index.html
│
├── css/
│   └── style.css
│
├── images/
│   ├── brand-awareness.png
│   ├── cost-management.png
│   ├── digital-marketing-meeting.jpg
│   ├── lead-generation.png
│   ├── online-reputation-management.jpg
│   ├── search-engine-optimization.jpg
│   └── social-media-marketing.jpg
│
└── README-assets/
    └── horiseon-responsive-reference.png
```

> **Vigtigt:** I `index.html` skal stylesheetet refereres som `./css/style.css`, og HTML-billederne skal refereres fra `./images/`. Fra `css/style.css` refereres hero-billedet som `../images/digital-marketing-meeting.jpg`.

---

## GitHub og løbende commits

Du skal arbejde med projektet i dit eget GitHub-repository.

Under hele opgaven skal du lave **løbende og beskrivende commits**, så din arbejdsproces og udviklingen af projektet kan følges.

Du skal som minimum:

- lave **ét commit for hver opgave**
- committe løbende, efterhånden som du løser og tester opgaverne
- skrive en beskrivende commit-besked, der fortæller, hvad du har ændret

Da opgavesættet består af 29 opgaver, skal dit repository derfor indeholde **mindst 29 relevante commits**.

---

# DEL 1 – WEB ACCESSIBILITY

I første del skal du forbedre websitets HTML og CSS med fokus på webtilgængelighed.

Målet er:

```text
Lighthouse Accessibility: 100
```

En Lighthouse-score på 100 betyder dog ikke, at websitet automatisk er fuldt tilgængeligt.

Du skal derfor kombinere Lighthouse med:

- manuel tastaturtest
- kontrol af headingstruktur
- vurdering af `alt`-tekster
- kontrol af farvekontrast
- zoom og reflow
- HTML-validering

---

# Opgave 1 – Lav en Lighthouse Accessibility-baseline

Inden du ændrer noget i koden, skal du måle sidens nuværende Accessibility-score.

## Sådan gør du

1. Åbn `index.html` i Google Chrome.
2. Åbn **Chrome DevTools**.
3. Vælg **Lighthouse**.
4. Vælg kategorien **Accessibility**.
5. Kør analysen.
6. Notér den nuværende score.
7. Gem gerne et screenshot.

```text
Accessibility før forbedringer: __67___
```
!["Screenshot af lighthouse analyse af Accessibility med en score på 67](/readimg/opg1a.png "Screenshot af lighthouse analyse af Accessibility med en score på 67")



> Din præcise Lighthouse-score kan variere lidt afhængigt af Chrome/Lighthouse-version og testmiljø. Det vigtige er, at du registrerer **din egen baseline**, før du ændrer koden, og bruger samme testopsætning ved eftermålingen.

## Forkert princip

```text
Ret først problemerne og kør derefter Lighthouse.
```

### Hvorfor er det et problem?

Hvis du ændrer siden først, har du ingen baseline at sammenligne med.

## Korrekt princip

```text
1. Mål
2. Notér
3. Forbedr
4. Mål igen
5. Sammenlign
```

## Ændringer

### Alt antributter

#### Før
eksempel:
```html
<img src="./readimg/search-engine-optimization.jpg"  class="float-left" />
```

#### Efter

Tilføjet manglende alt tekster til hver img

eksempel:
```html
<img src="./readimg/search-engine-optimization.jpg" alt="På et skrivebord ligger en notesbord, hvor der på siden er tegnet en figur. Seo står i midten og rundt om der der tegnet kendetegn ved seo" class="float-left" />
```



### Farvekontrast

#### Før
![Screenshot af farvekontrast analyse lavet med strak værktøj før ændringer, som viser en dårlig score](/readimg/opg1farve-før.png "Screenshot af farvekontrast analyse lavet med strak værktøj før ændringer, som viser en dårlig score")

Dårlig farvekontrast før ændringer. Den blå baggrundsfarve og den hvide tekst 

![Screenshot af strak værktøj forslag til farve med en bedre kontrast](/readimg/opg1farve-efter.png "Screenshot af strak værktøj forslag til farve med en bedre kontrast")

starks forslag til en farve, som har en god kontrast med teksten

#### Efter
Jeg har ændret farven til #154b67 i benefits søjlen


### Optimale løsninger

#### Før

##### a
Manglende primært landmark


##### b
I headeren står li elementerne i ul for tæt, så det svært for folk at trykke på.

#### Efter

##### a
Jeg har tilføjet et main-element i min html, som manglede. Så nu ved den, hvor og hvad det vigtigste indhold er. 

##### b
Jeg har gjort teksten er blevet større og tilføjet en display flex og et gap.


### Score efter ændringer
![Screenshot af lighthouse analyse efter ændringer. Scoren er på 100 nu](/readimg/opg1score-efter.png "Screenshot af lighthouse analyse efter ændringer. Scoren er på 100 nu")


---

# Opgave 2 – Giv siden en beskrivende `<title>`

Undersøg dokumentets nuværende `<title>`.

Starterprojektet indeholder:

```html
<title>website</title>
```

### Hvorfor kan det forbedres?

Titlen hjælper brugeren med at identificere siden i blandt andet:

- browserfaner
- bogmærker
- browserhistorik

## Korrekt princip

En titel bør kort beskrive både websitet og sidens vigtigste indhold.

```html
<title>Virksomhedsnavn | Sidens vigtigste indhold</title>
```

Formulér selv en passende titel til Horiseon.

## Efter ændringer
```html
<title>Horiseon | Seo, online reputation management og social media marketing</title>
```



---

# Opgave 3 – Kontrollér dokumentets `<head>`

Kontrollér dokumentets metadata.

Starterprojektet indeholder allerede:

```html
<meta charset="UTF-8" />
```

Undersøg, hvad der mangler for at gøre siden bedre forberedt til forskellige viewport-størrelser.

## Korrekt princip

Et responsive website bør blandt andet indeholde en viewport-deklaration:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### Hvorfor er dette vigtigt?

Viewport-indstillingen har betydning for:

- mobile enheder
- responsive layouts
- zoom
- reflow


## Efter ændringer
Først tilføjede jeg:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Derefter ændrede jeg rækkefølgen på title og link, så link står til sidst i head.


Så head endte med at se således ud:
```html
<meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    
    <title>Horiseon | Seo, online reputation management og social media marketing</title>
    
    <link rel="stylesheet" href="./css/style.css">
```


---

# Opgave 4 – Forbedr den semantiske HTML

Starterprojektet anvender flere generiske `<div>`-elementer.

Eksempel:

```html
<div class="header"></div>
```

Undersøg, om nogle områder i stedet bør anvende semantiske HTML-elementer.

Overvej blandt andet:

```html
<header>
  <nav>
    <main>
      <section>
        <aside>
          <footer></footer>
        </aside>
      </section>
    </main>
  </nav>
</header>
```

## Forkert princip

```html
<div class="footer">...</div>
```

hvis området reelt fungerer som sidens footer.

## Korrekt princip

Brug det HTML-element, der bedst beskriver indholdets funktion.

### En `<div>` kan også være det korrekte valg

Semantisk HTML betyder ikke, at alle `<div>`-elementer skal erstattes med `<section>`.

Hvis et element kun bruges til at gruppere indhold af hensyn til layout og ikke repræsenterer et selvstændigt indholdsafsnit, kan `<div>` være det korrekte valg.

Eksempel:

```html
<div class="layout-wrapper">...</div>
```

Her bruges `<div>` kun som en neutral wrapper til layout.

## Undersøg navigationen særligt

Starterprojektet har et synligt problem i headeren: navigationen står lodret og vises med bullets.

Undersøg både HTML'en og de eksisterende CSS-selectors. Starter-CSS'en indeholder blandt andet:

```css
.header nav {
    ...
}

.header nav ul {
    list-style-type: none;
}

.header nav ul li {
    display: inline-block;
    ...
}
```

Sammenlign disse selectors med den HTML, der faktisk omgiver menuens `<ul>`.

### Rettelse
Flere div elementer er blevet rettet. Så nu er de semantisk rigtige. F.eks. har jeg ændret en div til en header, og en div til en nav. På den måde er vores header sektion korrekt semantisk nu. 

Andre ændringer er f.eks div med class="content", har jeg ændret til en section element. 



### Krav til navigationen på større skærme

Efter din semantiske rettelse skal navigationen:

- være markeret med et passende semantisk HTML-element
- vises uden bullets
- have menupunkterne placeret horisontalt
- bevare de tre eksisterende links

> Pointen er både at vælge korrekt HTML-semantik og at forstå, hvorfor en CSS-selector kun virker, når den matcher den faktiske HTML-struktur.

## efter rettelser
Før kaldte css'en på et nav element som ikke fandtes. Derfor startede det med at stå i en kolonne og ikke i en række. Ved at ændre det fra en div til en nav element, bliver css nu kaldt og den styles rigtigt. 

---

# Opgave 5 – Skab en logisk dokumentstruktur

HTML-strukturen skal give mening, også hvis CSS ikke indlæses.

Prøv midlertidigt at deaktivere:

```html
<link rel="stylesheet" href="./css/style.css" />
```

Undersøg:

- Kommer navigationen før hovedindholdet?
- Er hovedindholdet samlet?
- Er supplerende indhold placeret logisk?
- Kommer footeren sidst?
- Kan siden forstås uden floats og visuel positionering?

> HTML-koden skal give mening uafhængigt af den visuelle styling.

## undersøgelse
- Kommer navigationen før hovedindholdet?
Ja den kommer først.

- Er hovedindholdet samlet?
Ja det er det, det ligger i en main.

- Er supplerende indhold placeret logisk?
Ja først kommer hero, så content sektionen, så benefits sektionen og til sidst footer.

- Kommer footeren sidst?
Ja den ligger i bunden, som man ville forvente.

- Kan siden forstås uden floats og visuel positionering?
Ja rækkefølge giver mening. Det eneste der er i sektionen content i hver af de tre article kommer img før h2 titlen. Så med en screen reader ville læse billede før titlen overhoevdet kommer. Det kan virker forvirrende.

Ellers er den meget let og forståligt.

---

# Opgave 6 – Undersøg headingstrukturen

Starterprojektet anvender website-navnet som `<h1>`.

Du skal overveje:

- Hvad er branding?
- Hvad er sidens egentlige hovedemne?
- Hvilke overskrifter er underemner?
- Mangler nogle sektioner en overordnet heading?
- Er headingniveauerne logiske?

Et muligt hierarki kan være:

```text
h1 Sidens hovedemne

├── h2 Search Engine Optimization
├── h2 Online Reputation Management
├── h2 Social Media Marketing
└── h2 Benefits
    ├── h3 Lead Generation
    ├── h3 Brand Awareness
    └── h3 Cost Management
```

### Vigtigt

Vælg ikke headingniveau ud fra tekstens størrelse.

Vælg headingniveau ud fra indholdets hierarki.

---

## Tilpas CSS efter ændringer i HTML-strukturen

Når du ændrer HTML-elementer, skal du kontrollere, om de eksisterende CSS-selectors stadig matcher.

Starter-CSS'en er flere steder knyttet direkte til bestemte HTML-elementer, blandt andet:

```css
.header h1 {
    ...
}

.header h1 .seo {
    ...
}

.header nav {
    ...
}

.footer h2 {
    ...
}
```

Hvis du ændrer et af disse HTML-elementer, kan stylingen derfor holde op med at virke.

### Korrekt princip

Du skal enten:

1. tilpasse CSS-selectoren til den nye semantiske HTML, eller
2. tilføje en relevant class, hvis stylingen med fordel skal være uafhængig af elementtypen.

Eksempel på princippet:

```html
<p class="logo">...</p>
```

```css
.logo {
    ...
}
```

Det samme princip kan anvendes andre steder, hvis du ændrer et heading-element, men stadig ønsker at bevare den eksisterende visuelle styling.

### Vigtig pointe

```text
HTML-element
→ beskriver betydning og struktur

CSS-selector / class
→ styrer styling og layout
```

## Ændringer

### logo h1 -> p

#### Før
Før var logo'et beskrevet med et h1-tag. Men logoet et egenligt bare en branding for virksomheden og ikke det relelle emne for hjemmside. Derfor bør den ikke have første priotet for en screenreader, som den ville få med en h1. Derfor laves den om til en p-tag.

```html
<h1>Hori<span class="seo">seo</span>n</h1>
```

```css
.header h1 {
    display: inline-block;
    font-size: 48px;
}

.header h1 .seo {
    color: #d9dcd6;
}
```

#### Efter
Efter er logoet skrevet med et p-tag, og har derfor en mindre priotet i hjemmesiden hieraki.

```html
<p>Hori<span class="seo">seo</span>n</p>
```

Css'en skulle også ændres da den før jo kaldte på en h1-tag. Nu kalder den på en p tag i header.
```css
.header p {
    display: inline-block;
    font-size: 48px;
}

.header p .seo {
    color: #d9dcd6;
}
```

### Tilføj h1 til webpage
Hjemmesiden mangler en passende og beskrivende h1. Den tilføjer jeg i content-sektionen. Med den nye h1 ved den besøgende med det samme hvad hjemmesiden faktisk handler om.

#### Efter
```html
<section class="content">
        <h1>Digital marketing solutions for your company</h1>
        
        <article class="search-engine-optimization">
            
    ...
```

### Tilføj h2 til benefits
Der manglede en passende overskrift til benefits søjlen. Den har jeg tilføjet. Nu kan læsere nemmere og hurtigere forstå.

```html
<aside class="benefits">
        <h2>Benefits</h2>
  ...
```

### Footer h2 -> p
h2 er ikke et af hovedeemnerne, derfor burde den ikke være en h2. Den ændres derfor til en p. 

### Resultater
Efter at ændret h1 i logoet til en p-tag. Tilføjet en passende h1 og h2 til sektionerne, så vil hjemmesiden hieraki se således ud:

```text
h1 Digital marketing solutions for your company

├── h2 Search Engine Optimization
├── h2 Online Reputation Management
├── h2 Social Media Marketing
└── h2 Benefits
    ├── h3 Lead Generation
    ├── h3 Brand Awareness
    └── h3 Cost Management

```

---

# Opgave 7 – Gennemgå billedernes `alt`-attributter

Starterprojektet indeholder flere billeder uden `alt`.

Du skal vurdere hvert billede.

## Informativt billede

Hvis billedet tilfører relevant information:

```html
<img src="images/example.jpg" alt="Meningsfuld beskrivelse" />
```

## Dekorativt billede

Hvis billedet kun er dekorativt:

```html
<img src="images/example.png" alt="" />
```

### Vigtig pointe

```text
Informativt billede
→ alt="Meningsfuld beskrivelse"

Dekorativt billede
→ alt=""
```

Brug ikke `aria-label` eller `aria-labelledby` for at fortælle, at et billede er dekorativt.

`aria-label` og `aria-labelledby` bruges, når et element har behov for et tilgængeligt navn.

Til et dekorativt `<img>` er:

```html
alt=""
```

normalt den enkleste og korrekte løsning.

---

# Opgave 8 – Reparér de interne anchor-links

Navigationen anvender interne links som:

```html
<a href="#search-engine-optimization"> Search Engine Optimization </a>
```

Destinationen skal have et tilsvarende `id`.

Eksempel:

```html
<section id="search-engine-optimization"></section>
```

### Din opgave

Test alle tre navigationslinks.

Kontrollér, at de fører til den korrekte sektion.

## Gør også logoet til et link til forsiden

På mange websites fungerer logoet som et link tilbage til forsiden.

Gør derfor hele Horiseon-logoet klikbart og lad det føre til `index.html`.

Eksempel:

```html
<p class="logo">
  <a href="index.html"> Hori<span class="seo">seo</span>n </a>
</p>
```

### Accessibility-pointe

Der er ikke behov for at tilføje `aria-label` til dette link, når den synlige linktekst allerede giver linket et meningsfuldt navn.


## Ændringer
I opg 1 tilføjede jeg beskrivende alt tekst til alle img tags i html. Men de kan forbedres.

### alt tekster i content sektion
I opgave 1 lavede jeg nogle lange og meget beskrivende alt-tekster på dansk, dem har jeg gjort kortere og mere præcise. Og så har jeg også oversat dem til engelsk så de passer til alt andet indhold.


### alt tekster i benfits søjle
Jeg havde en beskrivende alt tekst til alle billederne med ikonerne. Men ikoner er mere dekorative og tilføjer egenligt ikke noget ekstra for teksten. Derfor har keg valgt at deres alt tekst bare skal være dekorativ. alt=""


## Ændringer

### Logo lavet til link
For at lave logoet til et link har jeg tilføjet et ankerlink til index.html

#### Efter
```html
<p class="logo">
            <a href="index.html"> Hori<span class="seo">seo</span>n </a>
        </p>
```

### Manglende id til search-engine-optimization article

Før virkede ankerlinket ikke til search-engine-optimization fordi der manflede et id. Det tilføjede jeg.

```html
<article id="search-engine-optimization" class="search-engine-optimization">
            
```

---

# Opgave 9 – Undersøg om links kan identificeres visuelt

Starter-CSS'en indeholder:

```css
a {
  color: #ffffff;
  text-decoration: none;
}
```

Undersøg navigationen og vurder:

- Er det tydeligt, at teksterne er links?
- Er links tydelige ved hover?
- Er links tydelige ved keyboard-fokus?
- Er designet afhængigt af farve alene?

> Det er ikke automatisk en accessibility-fejl at fjerne understregningen fra links i en tydelig navigation. Du skal vurdere linkets kontekst.

## Undersøgelse
- Er det tydeligt, at teksterne er links?
Visuelt nej, hvis man tænker på et typisk link, da der ikke er en streg under. Men jakobs low træder ind, så vi ved godt at i en nav bar består af klikbare links. så der behøver faktisk ikke være en streg under.

- Er links tydelige ved hover?
Ja de er tydelige. der er cursor effekt på, så man ved de er klikbare.

- Er links tydelige ved keyboard-fokus?
Ja det er de. Der kommer en stor lysende boks/kant rundt om linket når man bruger tab.



- Er designet afhængigt af farve alene?
I dette tilfælde så nej. Samme princip som at der ikke behøver en underline. Når det er nav, så ved brugeren automatisk at det er links, så farven er ikke afgørende. Hvorimod hvis det var brød tekst, er det forventet at der enten er en underline eller linket er blåt.




---

# Opgave 10 – Test og forbedr farvekontrast

Brug Lighthouse eller browserens accessibility-værktøjer til at undersøge kontrast.

Vær især opmærksom på:

```css
color: #ffffff;
```

kombineret med blå baggrunde.

## Din opgave

Hvis kontrasten er utilstrækkelig, skal du ændre eksempelvis:

```css
color
background-color
```

Forsøg at bevare Horiseons visuelle identitet.

## Ændringer
I opg 1 var en af problemere i min lighthouse analyse jeg fandt farvekonstrasten. Her ændrede jeg farven på baggrunden.

### Nav
![Farvekonstarst før og efter på nav.](/readimg/opg10nav.png "Farvekonstarst før og efter på nav.")

### Content sektion
![Farvekonstarst før og efter på content sektion.](/readimg/opg10content.png "Farvekonstarst før og efter på content sektion.")

### Benefits søjle
![Farvekonstarst før og efter på benefits søjle.](/readimg/opg10benefits.png "Farvekonstarst før og efter på benefits søjle.")

Her ændre jeg farven på fonten til sort så det passer til ikonerne. Deridover har jeg gjort baggrunden til en lysere blå.

---

# Opgave 11 – Test siden med tastatur

Læg musen væk.

Brug:

```text
Tab
Shift + Tab
Enter
```

Kontrollér:

- Kan du nå alle links?
- Kan navigationen bruges?
- Følger fokus en logisk rækkefølge?
- Kan du se, hvilket element der har fokus?

## Korrekt princip

Hvis den eksisterende fokusmarkering ikke er tydelig nok, kan du implementere en tydelig `:focus-visible`-stil.

Eksempel:

```css
a:focus-visible {
  outline: 3px solid currentColor;
  outline-offset: 4px;
}
```

Tilpas løsningen til designet.

## Ændringer

### Før
Navigationen virker fint med brug af tab. Man bliver også ført de rigtige steder hen. En forbedring der kunne laves er et det bliver endnu tydligere hvad link tab er på. Lige nu er det en meget tynd streg der er rundt om. Den er egenligt ok, men det kan godt blive tydeligere

### Efter

```css
a:focus-visible {
  outline: 4px solid currentColor;
  outline-offset: 6px;
}
```

Med dette stykke kode, har jeg lavet en tykkere og større streg rundt om markede.


---

# Opgave 12 – Test zoom, reflow og faste højder

Starterprojektet anvender blandt andet:

```css
height: 300px;
```

på serviceområderne.

Zoom browseren til:

```text
200 %
```

Undersøg:

- Er al tekst stadig synlig?
- Løber tekst uden for bokse?
- Overlapper elementer?
- Kan bokse vokse med indholdet?
- Opstår der unødvendig vandret scrolling?

## Korrekt princip

Brug ikke en fast højde, hvis indholdet har behov for at kunne vokse.

Overvej:

```css
min-height
```

eller at lade indholdet bestemme højden.


## Undersøgelse
- Er al tekst stadig synlig?
Alt teksten er stadig inden for skærmen. Dog er meget af teksten ikke læsbar mere, da den flyder ud af dens boks og henover andre elementer.


- Løber tekst uden for bokse?
Ja, teksten i content boksene løber ud over grænserne.

I benefit søjlen holder teksten sig dog indenfor rammerne.


- Overlapper elementer?
Ja tekst, billeder osv overlapper hinanden i content sektionen nu.


- Kan bokse vokse med indholdet?
Som det er lige nu vokser boksene ikke med indholdet. Det kan dog fikses.


- Opstår der unødvendig vandret scrolling?
Ved 200% så nej. 
Men hvis vi zoomer ydeligere ind til 250% opstår der faktisk en smule unødvenligt vandret scroll. 


## Ændringer

### Før
Før var der brugt en fast højde på boksene, hvilket gjorde at de ikke vokser med indholdet. 

```css
height
```


### Efter
Er der blevet brugt min-height på alle boksene.
```css
min-height
```

Så nu vokser boksen med indholdet.

---

# Opgave 13 – Ryd op i CSS

Starter-CSS'en indeholder med vilje gentagelser.

Undersøg:

- Findes den samme styling flere steder?
- Kan selectors samles?
- Findes gamle eller overflødige properties?
- Findes layoutregler, der ikke længere er nødvendige?
- Findes CSS, der ikke længere matcher HTML'en?

### Afgrænsning i denne del

Du må gerne reducere gentagelser ved at gruppere eksisterende selectors. Du behøver ikke allerede her at indføre den `.marketing`-wrapper eller fælles `.services`-class, som introduceres i DEL 3.

## Eksempel

```css
.element-a {
  margin-bottom: 32px;
  color: #ffffff;
}

.element-b {
  margin-bottom: 32px;
  color: #ffffff;
}
```

kan eventuelt samles:

```css
.element-a,
.element-b {
  margin-bottom: 32px;
  color: #ffffff;
}
```

### Vigtigt

Fjern ikke CSS alene, fordi du ikke forstår reglen.

Undersøg først, hvilken funktion den har.


## Ændringer


### Content sektion
#### Før
De tre bokse har helt samme styling og kan dermed samles i css.

#### Efter
```css
.search-engine-optimization, .online-reputation-management, .social-media-marketing {
    margin-bottom: 20px;
    padding: 50px;
    min-height: 300px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: #025b92;
    color: #ffffff;
}
```



Det samme princip gælder også deres h2.

```css
.search-engine-optimization h2, .online-reputation-management h2, .social-media-marketing h2 {
    margin-bottom: 20px;
    font-size: 36px;
}
```


Og deres styling af img, kan også samles.

```css
.search-engine-optimization img, .online-reputation-management img, .social-media-marketing img {
    max-height: 200px;
}
```




### Benefits søjle
#### Før
```css
.benefit-lead {
    margin-bottom: 32px;
    color: #000000;
}

.benefit-brand {
    margin-bottom: 32px;
    color: #000000;
}

.benefit-cost {
    margin-bottom: 32px;
    color: #000000;
}
```


De tre forskellige elementer har faktisk præcis samme styling. Samme margin-bottom og color. Derfor kan de godt samles.

#### Efter
```css
.benefit-lead, .benefit-brand, .benefit-cost {
    margin-bottom: 32px;
    color: #000000;
}
```

Dette princip er mange steder i css'en. Blandt andet også ved de tre benefit articles h3. De har alle samme styling og kan derfor samles til:



```css
.benefit-lead h3, .benefit-brand h3, .benefit-cost h3 {
    margin-bottom: 10px;
    text-align: center;
}
```


Og det samme med deres img. Det kan også samles, fordi det har samme styling.

```css
.benefit-lead img, .benefit-brand img, .benefit-cost img {
    display: block;
    margin: 10px auto;
    max-width: 150px;
}
```



```css
```

---

# DEL 2 – WEB PERFORMANCE

I anden del skal du optimere websitets ressourcer med fokus på indlæsningstid og billedoptimering.

Målet er:

```text
Lighthouse Performance: 90 eller højere
```

Du skal især arbejde med:

- billeddimensioner
- filstørrelser
- WebP
- hero-billedet i CSS
- billedkvalitet
- Lighthouse og Chrome DevTools

> Bevar de accessibility-forbedringer, du gennemførte i DEL 1, mens du arbejder med performance.

---

# Opgave 14 – Lav en Performance-baseline

Åbn Lighthouse igen.

Vælg:

```text
Performance
```

Brug samme indstillinger ved før- og eftermålingen.

Notér:

```text
Performance før optimering: ___73___
```

> Performance-scoren kan variere lidt mellem målinger. Brug derfor samme browser, samme Lighthouse-indstillinger og så vidt muligt samme testforhold ved før- og eftermålingen.

Gem gerne et screenshot.

![Performance score på 73](/readimg/performancescore-foer.png "Performance score på 73.")

![Performance problemer](/readimg/performancescoreproblemer-foer-.png "Performance problemer")

---

# Opgave 15 – Undersøg billedernes dimensioner og filstørrelser

Gennemgå billederne i:

```text
images/
```

Undersøg for hvert billede:

- filformat
- bredde og højde i pixels
- filstørrelse
- hvor stort billedet faktisk vises på websitet

### Refleksion

Et billede på eksempelvis:

```text
3000 × 2000 px
```

er ikke nødvendigvis hensigtsmæssigt, hvis det kun vises omkring:

```text
500 × 300 px
```

## Hjælp

Du kan bruge:

- filinformation i operativsystemet
- Chrome DevTools
- Network-panelet
- et billedredigeringsprogram

Notér gerne resultaterne i en lille tabel.

| Billede                            | Format | Dimensioner | Filstørrelse | Relevant at optimere? |
| ---------------------------------- | ------ | ----------: | -----------: | --------------------- |
| `search-engine-optimization.jpg`   |        |             |              |                       |
| `online-reputation-management.jpg` |        |             |              |                       |
| `social-media-marketing.jpg`       |        |             |              |                       |


## Notater

| Billede                            | Format | Dimensioner | Filstørrelse | Relevant at optimere? |
| ---------------------------------- | ------ | ----------: | -----------: | --------------------- |
| `digital-marketing-meeting.jpg`       |    JPEG    |      8688 × 5792       |      14,2 mb        |          Ja, meget store dimensioner og filstørrelse             |
| `search-engine-optimization.jpg`   |    JPEG    |     7360 × 4912        |      14,9 mb        |           Ja, billedet et ekstremt stort i forhold til den størrelse den bliver vist på hjemmesiden            |
| `online-reputation-management.jpg` |   JPEG     |      4404 × 2877       |      6,7 mb        |         Ja             |
| `social-media-marketing.jpg`       |    JPEG    |      5000 × 3451       |       14,2 mb       |          Ja, filen fylder ekstremt meget, og har meget store dimensioner             |
| `brand-awareness.png`   |    png    |      1000 × 1000       |       63 kB        |            Ikke nødvendigt, men dimensioner kan godt formindskes           |
| `cost-management.png` |    png    |     1000 × 1000        |       41 kB       |          Ikke nødvendigt, men dimensioner kan godt formindskes             |
| `lead-generation.png`       |    png    |     1000 × 1000        |      40 kB        |           Ikke nødvendigt, men dimensioner kan godt formindskes            |

---

# Opgave 16 – Konvertér relevante billeder til WebP

Konvertér relevante JPG- og PNG-billeder til **WebP**.

## Forkert

Det er ikke nok blot at ændre:

```html
<img src="images/photo.jpg" alt="..." />
```

til:

```html
<img src="images/photo.webp" alt="..." />
```

hvis filen `photo.webp` ikke eksisterer.

## Korrekt princip

```text
1. Konvertér den fysiske billedfil
2. Kontrollér billedkvaliteten
3. Opdatér filreferencen
4. Test i browseren
```

## Hjælp

Du kan eksempelvis bruge:

- Adobe Photoshop
- GIMP
- XnConvert
- et andet billedværktøj, der kan eksportere WebP

Du behøver ikke bruge terminalen.


## Ændringer

### Dimensioner
Jeg ændrede først dimensioner på billederne. Hvor jeg scalerede dem ned, så de ik var helt så store. Det hjalp også på filstørrelsen.

### Konvertering
Jeg har brugt hjemmesiden https://cloudconvert.com/jpg-to-webp til at konvertere mine billeder til webp filer

### Ændringer i html

#### Før
Bla. 
```html
<img src="/images/social-media-marketing.jpg" alt="Six people around a table with various social media symbols." class="float-left" />
```

#### Efter
```html
<img src="/images/social-media-marketing.webp" alt="Six people around a table with various social media symbols." class="float-left" />
```

Og jeg har selfølgelig også rettet html for de andre img det der er webp filen der bliver kaldt på.


---

# Opgave 17 – Husk hero-billedet i CSS

Ikke alle billeder ligger i HTML.

Starter-CSS'en indeholder:

```css
.hero {
  background-image: url("../images/digital-marketing-meeting.jpg");
}
```

Hvis du optimerer hero-billedet, skal denne reference også opdateres.

### Kontrol

Brug browserens **Network-panel** til at kontrollere, at den nye fil faktisk indlæses.


## Ændringer
```css
background-image: url("../images/digital-marketing-meeting.webp");
```

css opdateret, så den kalder på vores webp fil.


---

# Opgave 18 – Kontrollér billedkvaliteten

En mindre fil er ikke automatisk bedre.

Sammenlign originalen og den optimerede version.

Kontrollér:

- skarphed
- komprimeringsfejl
- teksturer
- farver
- samlet visuel kvalitet

Find en balance mellem:

```text
lav filstørrelse
+
acceptabel billedkvalitet
```

## Vurdering
Kvaliteren var god, så jeg prøvedet at se om jeg kunne komprimere billederne ydeligere, så de fyldte mindre. Det gjorde jeg så meget jeg kunne, uden jeg synes det gik ud over kvailiteten. 

---

# Opgave 19 – Kør Lighthouse Performance igen

Kør Lighthouse med samme indstillinger som ved baseline.

Notér:

```text
Performance før: ___73___
Performance efter: __99___
```

### Mål

```text
Performance: 90 eller højere
```

Hvis scoren fortsat er lav, skal du læse Lighthouse-anbefalingerne og undersøge, hvilke ressourcer der stadig påvirker siden.

## Score

![performance score på 99](/readimg/performancescore-efter.png "performance score på 99")


---

# DEL 3 – RESPONSIVE WEBDESIGN MED CSS FLEXBOX

Nu skal du gøre websitet responsive.

Du skal arbejde videre med den tilgængelige og optimerede version fra DEL 1 og DEL 2.

Målet er, at siden fungerer på både store og små skærme uden unødvendig vandret scrolling eller overlappende indhold.

---

## Visuelt mål

![Reference til det responsive Horiseon-layout](README-assets/horiseon-responsive-reference.png)

> Referencebilledet viser det ønskede overordnede layout. Du behøver ikke ramme hver pixel præcist. Fokus er på struktur, fleksibilitet, læsbarhed og et robust responsive layout.

---

## Læringsmål

Du skal kunne:

- analysere et eksisterende float-baseret layout
- anvende CSS Flexbox
- forstå flex-container og flex-items
- anvende `gap`
- arbejde med `flex-direction`
- anvende `justify-content` og `align-items`
- bruge `flex-wrap` efter behov
- gøre billeder fleksible
- anvende media queries
- teste flere viewport-størrelser
- fjerne overflødige floats

---

# Opgave 20 – Analysér det eksisterende layout og det gamle layoutsystem

Åbn **Device Toolbar** i Chrome DevTools.

Test eksempelvis:

```text
320 px
480 px
768 px
1024 px
1440 px
```

Undersøg:

- Bliver navigationen for bred?
- Overlapper indhold?
- Bliver serviceområderne for smalle?
- Bliver Benefits-kolonnen for smal?
- Skalerer billederne?
- Opstår vandret scrolling?

Dokumentér mindst tre problemer.

## Problemer

### Problem 1 - Header og links overskrider grænse. 
![ankerlinks går ud over header](/readimg/opg20-p1.png "ankerlinks går ud over header")
(Testet på 900px)

### Problem 2 - Billeder og overskrift hopper ud af boks
![Billeder og overskrift hopper ud af boks](/readimg/opg20-p2.png "Billeder og overskrift hopper ud af boks")
(Testet på 320px)

### Problem 3 - Indhold bliver for bredt til benefits boks og skaber vandret scroll
![Indhold bliver for bredt til benefits boks](/readimg/opg20-p3.png "Indhold bliver for bredt til benefits boks")
(Testet på 480px)


---

## Find det gamle layoutsystem

Starter-CSS'en bruger blandt andet:

```css
float: left;
float: right;
display: inline-block;
```

Undersøg, hvilke elementer disse regler forsøger at placere.

### Refleksion

```text
Hvilke elementer skal stå ved siden af hinanden?

Linkene i navgationen skal stå ved siden af hinanden på desktop.
Og de skal også stå ved siden af logoet-

Content og benefits sektionerne skal stå ved siden af hinanden.

Inde i hver content article skal billede <img> og tekst stå ved siden af hinanden.

```

```text
Hvilke elementer skal stå under hinanden?

Alle de overordnede elementer/sektioner i body skal stå under hinanden. header->hero->indhold->footer

De tre articles i content sektionen skal stå under hinanden.

Inde i benefits skal de forskellige articles stå under hinanden.
Her skal indholdet i articles også stå under hinanden. altså h3, img og p.

```

Før du skriver Flexbox, skal du forstå den ønskede struktur.

---

# Opgave 21 – Brug Flexbox i headeren

Headeren indeholder branding og navigation.

I DEL 1 har du arbejdet med navigationens semantik og fået menuen til at fungere vandret uden bullets på større skærme. Starter-CSS'en bruger oprindeligt blandt andet:

```css
.header nav {
  float: right;
}
```

I denne del skal du erstatte den gamle layoutmetode med Flexbox.

## Hjælp – start her

Du kan gøre `.header` til en flex-container:

```css
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
```

Når et element får:

```css
display: flex;
```

bliver dets **direkte children** til flex-items.

Efter dine semantiske forbedringer kan du tænke headerens struktur sådan:

```text
.header
│
├── branding / logo
└── nav
```

### Vigtig pointe

Flexbox påvirker først og fremmest de direkte children i flex-containeren.

Når Flexbox overtager placeringen af branding og navigation, skal du undersøge, om den gamle regel:

```css
float: right;
```

stadig er nødvendig.

Du skal ikke beholde gamle layoutregler, hvis Flexbox allerede løser deres funktion.

### Kontrollér navigationen igen

Efter ændringen skal navigationen på større skærme fortsat:

- være uden bullets
- have links placeret horisontalt
- have passende afstand mellem links
- kunne bruges med tastatur


## Ændringer

### Før
```css
.header {
        padding: 20px;
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
        background-color: #255D79;
        color: #ffffff;
        
    }

.header nav {
        padding-top: 15px;
        margin-right: 20px;
        float: right;
     ...
    }
```
.header nav havde float: right;

### Efter

Tilføjede følgende til .header
```css
.header {
        display: flex;
        align-items: center;
        justify-content: space-between;
    ...      
    }
```

slettede jeg float: right; fra .header nav {...}

Nu har header layoutregler flexbox.


---

# Opgave 22 – Organisér hovedindholdet før du bruger Flexbox

Før du skriver mere CSS, skal du forstå strukturen i hovedindholdet.

Den vejledende løsning organiserer indholdet efter dette princip:

```text
main.content
│
├── h1
│   └── Digital Marketing Services
│
├── .marketing
│   ├── section.services
│   │   └── Search Engine Optimization
│   │
│   ├── section.services
│   │   └── Online Reputation Management
│   │
│   └── section.services
│       └── Social Media Marketing
│
└── aside.benefits
    ├── Lead Generation
    ├── Brand Awareness
    └── Cost Management
```

## Hvad viser skitsen?

Skitsen viser:

- at `main.content` er den overordnede container
- at sidens `<h1>` ligger øverst
- at `.marketing` samler de tre serviceområder
- at `aside.benefits` er et separat område
- at de tre serviceområder har samme rolle i layoutet

`.marketing` fungerer her som en wrapper omkring de tre service-sektioner.

De enkelte serviceområder kan derfor få en fælles class:

```html
<section class="search-engine-optimization services">...</section>
```

```html
<section class="online-reputation-management services">...</section>
```

```html
<section class="social-media-marketing services">...</section>
```

### Hvorfor en fælles `.services`-class?

De tre områder har samme rolle i layoutet.

Det giver mulighed for at style dem samlet i stedet for at skrive den samme layoutregel tre gange.

### Tænk over strukturen før CSS

Før du bruger Flexbox, skal du kunne svare på:

```text
- Hvad hører sammen?
De tre services hører sammen. Det er derfor vi har samlet dem i en section med class="marketing".

De tre article i benefits hører også sammen.

.marketing sektionen og .benefits hører også sammen. 


- Hvilke elementer skal ligge ved siden af hinanden?
Det skal .marketing og benefits.


- Hvilke elementer skal ligge under hinanden?
det skal h1, .main-indhold, og footer. 


- Hvilke elementer skal være direkte children i en flex-container?

I min wrapper .main-indhold bliver .maketing og .benefits children.

De tre articles i marketing skal være children i en flex-container som bliver .marketing.

Det samme med de tre article i .benefits.

```

> Du må gerne tilføje classes eller en simpel wrapper i HTML'en, når det gør layoutet mere logisk og CSS'en lettere at vedligeholde.

## Tilføjelse

Jeg har rykket class="content" op til main.


Giver alle tre article i .marketing classen services.


---

# Opgave 23 – Brug Flexbox på `main.content`

I den vejledende løsning bruges `main.content` som flex-container.

Du må gerne tage udgangspunkt i:

```css
main.content {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: stretch;
  gap: 1.2rem;
}
```

## Skitse af Flexbox-layoutet

Målet er et desktop-layout, der overordnet kan se sådan ud:

```text
main.content
┌──────────────────────────────────────────────────────────────┐
│ h1: Digital Marketing Services                              │
├───────────────────────────────────────┬──────────────────────┤
│ .marketing                            │ aside.benefits       │
│                                       │                      │
│ ┌───────────────────────────────────┐ │ ┌──────────────────┐ │
│ │ .services                         │ │ │ Lead Generation  │ │
│ │ Search Engine Optimization        │ │ ├──────────────────┤ │
│ └───────────────────────────────────┘ │ │ Brand Awareness  │ │
│                                       │ ├──────────────────┤ │
│ ┌───────────────────────────────────┐ │ │ Cost Management  │ │
│ │ .services                         │ │ └──────────────────┘ │
│ │ Online Reputation Management      │ │                      │
│ └───────────────────────────────────┘ │                      │
│                                       │                      │
│ ┌───────────────────────────────────┐ │                      │
│ │ .services                         │ │                      │
│ │ Social Media Marketing            │ │                      │
│ └───────────────────────────────────┘ │                      │
└───────────────────────────────────────┴──────────────────────┘
```

## Hvad betyder reglerne?

```text
display: flex
→ main bliver en flex-container

flex-direction: row
→ flex-items placeres som udgangspunkt vandret

flex-wrap: wrap
→ flex-items må flytte til en ny række

align-items: stretch
→ elementerne kan strækkes i den tværgående retning

gap: 1.2rem
→ der skabes afstand mellem flex-items
```

## Hvilke elementer bliver flex-items?

Hvis HTML-strukturen er:

```text
main.content
│
├── h1
├── .marketing
└── aside.benefits
```

så bliver disse tre elementer flex-items:

```text
h1
.marketing
aside.benefits
```

### Vigtig pointe

`display: flex` påvirker først og fremmest de **direkte children** i flex-containeren.

Det betyder, at de tre `.services` ikke direkte styres af Flexbox-reglerne på `main.content`.

De ligger inde i `.marketing`.

---

## Få `<h1>` til at ligge på sin egen række

Hvis `<h1>` skal ligge over `.marketing` og `aside.benefits`, kan du bruge:

```css
main.content > h1 {
  flex-basis: 100%;
}
```

Så kan du tænke layoutet sådan:

```text
Række 1

[h1......................................................]

Række 2

[.marketing........................][aside.benefits.....]
```

### Hvad gør `flex-basis: 100%`?

I denne sammenhæng betyder det, at `<h1>` som udgangspunkt optager en hel række i flex-containeren.

Det giver plads til, at `.marketing` og `aside.benefits` kan ligge ved siden af hinanden på næste række.

---

## Det overordnede Flexbox-princip

Du kan tænke strukturen sådan:

```text
main.content
→ styrer det overordnede layout

.marketing
→ styrer de tre servicebokse

aside.benefits
→ styrer benefit-indholdet
```

Du skal altså ikke forsøge at løse hele siden med én enkelt flex-container.

I de næste opgaver arbejder du videre med `.marketing` og `aside.benefits`.

## Ændringer
Har tilføjer dette css:

```css
main.content {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        align-items: stretch;
        gap: 1.2rem;
        margin: 50px;
    }

    main.content > h1 {
        flex-basis: 100%;
    }
```

Så nu er main.content flexbox


---

# Opgave 24 – Organisér `.marketing` med Flexbox

De tre servicebokse skal stå under hinanden.

Her kan `.marketing` fungere som endnu en flex-container:

```css
.marketing {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}
```

Strukturen bliver:

```text
.marketing
│
├── .services
├── .services
└── .services
```

Her betyder:

```text
flex-direction: column
→ serviceboksene placeres lodret
```

## Lad serviceboksene dele pladsen

I stedet for at give hver serviceboks en fast procenthøjde kan du lade Flexbox fordele den tilgængelige plads:

```css
.services {
  flex: 1;
}
```

Det er mere fleksibelt end eksempelvis:

```css
.services {
  height: 32.2%;
}
```

### Hvorfor?

`flex: 1` betyder i denne sammenhæng, at de tre serviceområder får mulighed for at dele den ledige plads i `.marketing`.

Det gør det lettere at få servicekolonnen til visuelt at flugte med Benefits-kolonnen uden at bruge en "magisk" procentværdi.

## Ændringer 

jeg ændrede først navnet på css fra:
```css
.search-engine-optimization, .online-reputation-management, .social-media-marketing {
        margin-bottom: 20px;
        padding: 50px;
        min-height: 300px;
        max-width: 1100px;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        background-color: #025b92;
        color: #ffffff;
    }
```

Til
```css
.services {
        flex: 1;

        margin-bottom: 20px;
        padding: 50px;
        min-height: 300px;
        max-width: 1100px;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        background-color: #025b92;
        color: #ffffff;
    }
```

Hvor jeg også fik tilføjet en flex: 1; så hver af de tre serviceområder får mulighed for at dele den ledige plads i `.marketing`

Jeg ændrede også css navnene til 
```css
.services img {
        max-height: 200px;
    }
```

og 

```css
.services h2 {
        margin-bottom: 20px;
        font-size: 36px;
    }
```


---

# Opgave 25 – Brug Flexbox i `aside.benefits`

Benefits-området indeholder flere elementer, der skal organiseres lodret.

Du må gerne tage udgangspunkt i:

```css
aside.benefits {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1.4rem;
}
```

Her får du et andet eksempel på Flexbox:

```text
main.content
→ row

.marketing
→ column

aside.benefits
→ column
```

### Det vigtige er ikke at bruge Flexbox overalt

Brug Flexbox, når det løser et konkret layoutproblem.

Du skal kunne forklare:

- hvorfor `main.content` bruger Flexbox
- hvorfor `.marketing` bruger `column`
- hvorfor `.services` bruger `flex: 1`
- hvorfor `aside.benefits` bruger `column`

## Besvar spørgsmål
- hvorfor `main.content` bruger Flexbox
Den bruger flexbox, fordi det er `main.content`, som bestemmer forholdet mellem elementerne, h1, marketing og benefits. Ved at lave main.content til en flexbox, bliver de andre elementer til children af main.content, og retter sig derfor ind efter main.content.

- hvorfor `.marketing` bruger `column`
Det gør den fordi de tre article/services skal stå i en kolonne. De skal altså stå under hinanden. 

- hvorfor `.services` bruger `flex: 1`
Man bruger `flex: 1` på `.services`, fordi så fordeler de tre articles sig på den tilgængelige højde i .marketing


- hvorfor `aside.benefits` bruger `column`
Det gør den af samme princip som hvorfor .marketing gør. Det er fordi de tre artciles skal stå under hinanden, og det sker ved at bruge `flex-direction: column;` på `aside.benefits`



---

# Opgave 26 – Tilføj ét CSS breakpoint med media query

Desktop-layoutet skal nu tilpasses mindre skærme.

Du behøver kun **ét breakpoint**, hvis det giver et velfungerende layout.

> Du skal ikke tilføje flere breakpoints bare for at have flere.

## Hvad er et breakpoint?

Et breakpoint er det punkt, hvor layoutet har behov for at ændre sig.

Tænk derfor:

```text
Hvornår begynder mit layout at få problemer?
```

og ikke:

```text
Hvor mange breakpoints skal jeg have?
```

---

## Brug `max-width` i denne opgave

Starterprojektet er bygget som et desktop-layout. Derfor bruger vi i denne opgave `max-width` til at tilpasse layoutet til mindre skærme.

### `max-width`

```css
@media (max-width: 768px) {
    ...
}
```

betyder:

```text
Når viewporten er 768 px eller smallere
→ brug reglerne inde i media query'en
```

Du kan tænke det sådan:

```text
Standard CSS
→ desktop / større skærme

max-width
→ tilpasning til mindre skærme
```

Horiseon-starterprojektet er allerede bygget som et desktop-layout, så `max-width` passer naturligt til denne opgave.

---

## Hjælp – sådan kan du starte dit breakpoint

Du må gerne tage udgangspunkt i:

```css
@media (max-width: 768px) {
  main.content {
    flex-direction: column;
  }

  .benefits {
    width: 100%;
  }
}
```

Det betyder, at hovedlayoutet på mindre skærme går fra:

```text
DESKTOP

.marketing | .benefits
```

til:

```text
MINDRE SKÆRM

.marketing
.benefits
```

Du skal herefter undersøge, om du også skal tilpasse:

- headeren
- navigationen
- floats på billeder
- margins
- paddings
- billedstørrelser

### Eksempel på yderligere muligheder

```css
@media (max-width: 768px) {
  .header {
    flex-direction: column;
  }

  .header nav {
    float: none;
    margin-right: 0;
  }

  main.content {
    flex-direction: column;
  }

  .benefits {
    width: 100%;
  }
}
```

> Eksemplet er stilladsering og ikke nødvendigvis hele løsningen. Test din egen side og tilføj kun de regler, der er nødvendige.


---

## Test breakpointet

Brug Chrome DevTools og ændr langsomt viewportens bredde.

Undersøg:

```text
Over breakpointet
→ desktop-layout

Ved breakpointet
→ layoutet skifter

Under breakpointet
→ layoutet skal stadig være læsbart og brugbart
```

Hvis ét breakpoint løser problemerne tilfredsstillende, er det nok.

## Ændringer 

Jeg satte et breakpoint på 760 px. Da det var der websiden layout begyndte at opføre sig underligt. Det var her websidens indhold blev for stort til skærmen.

Derfor tilføjede jeg en media quyer, hvori jeg tilpassede stylingen til flere af elementerne. Så når skærmen bliver mindre end 760 px, tilpasser layoutet sig.
```css
@media (max-width: 760px) {
  .header {
    flex-direction: column;
  }

  ...
}
```



---

# Opgave 27 – Test navigationen på små skærme

På større skærme har du allerede gjort navigationen vandret og fjernet bullets. Nu skal du undersøge, om den samme løsning fungerer på mindre skærme.

Test navigationen ved blandt andet:

```text
320 px
480 px
```

Kontrollér:

- Kan alle links læses?
- Bliver links klippet?
- Overlapper de logoet?
- Er der passende afstand mellem links?
- Kan de fortsat bruges med tastatur?

Overvej om:

```css
flex-wrap
```

eller ændring af `flex-direction` kan være relevant.

## Undersøgelse

### På 320px skærmstørrelse
![Header ved 320px skærmstørrelse](/readimg/opg27-320.png "Header ved 320px skærmstørrelse.")
De tre links står tæt, og skriftstørrelse er lidt for stor. Det bliver svært at se at det er tre links og ikke fire, fordi 'Online reputation management fylder to rækker.

<br>

### På 480px skærmstørrelse
![Header ved 320px skærmstørrelse](/readimg/opg27-480.png "Header ved 320px skærmstørrelse.")

## Ændringer
Efter undersøgelse fandt jeg ud af at linksne wrapper fint rundt om hinanden, da der allerede er flex-wrap: wrap; på .header nav ul {...}.

De vigtigste ændringer der skulle til var et større mellemrum mellem linksne. jeg satte derfor gap på gap: 16px; i #nav-liste {} (media quyer). Og jeg fjernede også margin-left fra 25px til 0px når skærmen er mindre end 760px. 

![Header ved 320px skærmstørrelse efter ændringer](/readimg/opg27-320efter.png "Header ved 320px skærmstørrelse efter ændringer.")
(320px)


---

# Opgave 28 – Sammenlign med referencebilledet og gennemfør afsluttende responsive test

## Sammenlign med referencebilledet

Sammenlign dit resultat med referencebilledet.

Vurder:

- overordnet placering
- indbyrdes afstand
- størrelsesforhold
- læsbarhed
- desktop-layout
- mobile-layout

Du skal **ikke** nødvendigvis lave en pixel-perfekt kopi.

Du skal kunne forklare dine layoutvalg.

---

## Test flere viewport-størrelser

Test mindst:

```text
320 px
480 px
768 px
1024 px
1440 px
```

Kontrollér:

- ingen unødvendig vandret scrolling
- ingen overlappende indhold
- navigationen fungerer
- teksten er læsbar
- billederne passer til containeren
- Benefits fungerer både desktop og mobil
- keyboard focus er stadig synligt

Test også ved:

```text
200 % zoom
```


## Sammenligning (mangler referende billede)
Jeg har desværre ikke adgang til refernece billedet, så jeg kan ikke sammenligne de to sider.

<br>

## Kontrolléring og test

Efter at have testet siden på de forskellige skærmstørrelse, kan jeg konkludere at det hele virker og ser fint ud. Siden virker både til desktop og mobil. 

Der kommer ingen unødvendig vandret scroll eller overlappende indhold. Alt holder sig indenfor skærmen. 

Navigationen virker både med mus eller med tab. Og keyboard focus er stadig synligt.

Alt indhold tilpasser sig også ved 200% zoom.




---

# Opgave 29 – Afsluttende Lighthouse-test

Kør til sidst Lighthouse igen.

Registrér:

| Måling        | Før | Efter |
| ------------- | --: | ----: |
| Accessibility |  67   |   100   |
| Performance   |  73   |   98   |

### Målsætning

```text
Accessibility: 100
Performance: 90 eller højere
```

Responsive webdesign vurderes manuelt med Device Toolbar og zoom-test.

---

# Dokumentér dine resultater

Besvar kort:

1. Hvad var Accessibility-score før og efter?
```text
Før var scoren 67 og efter 100
```
  
<br>  

2. Hvilke accessibility-problemer fandt Lighthouse?
```text
Der var fire problemer:
  1. Billedeelementer har ikke alt-antributter
  2. farverne i baggrunden og forgrunden har ikke nok kontrastforhold.
  3. Berøringsområderne størrelse eller afstand er ikke tilfredsstillende
  4. Dokumentet har ikke et primært landmark
```

<br>

3. Hvilke accessibility-problemer krævede manuel kontrol?
![Billede af lighthouse analse resultater](/readimg/manuelkontrol.png "Billede af lighthouse analse resultater.")

<br>

4. Hvilke semantiske HTML-ændringer foretog du?
```text
Jeg ændrende div tag til bla. header-tag, nav-tag i toppen af dokumentet.

Jeg ændrende div-tagget for content til en section, og de tre elementer med div-tag i, til articles.

og så ændrende jeg benefits div-tag til en aside.
```

<br>

5. Hvilke CSS-regler blev overflødige efter HTML-ændringerne?
```text
Det var bla. css reglen .header h1 {...}. For jeg ændrede h1 til en p i logoet, hvilket betyder at den css ikke gælder mere, da den ikke kalder på noget mere. Jeg ændrede derfor reglen til .header p {...}. Så styler den det rigtige.

Også reglen .header h1 .seo {...} skulle ændres til .header p .seo {...}

```
<br>

6. Hvad var Performance-score før og efter?
```text
Før:
73

Efter:
99

```
<br>

7. Hvilke billeder optimerede du?
```text
Jeg optimere på alle billederne. De tre ikon billeder ændrede jeg bare dimensionerne, blev de blev 300x300 istedet for 1000x1000.

Alle andre billeder, ændrede jeg først dimensionerne, så de blev en del mindre. Meget mere passende til web. 
Derefter komprimerede jeg dem med https://www.websiteplanet.com/da/webtools/imagecompressor/. 
Og til sidst konvertede dem til webp med https://cloudconvert.com/jpg-to-webp.
```
<br>

8. Hvor meget blev filstørrelserne reduceret?

| Billede                            | Dimensioner Før | Dimensioner Efter | Filstørrelse Før | Filstørrelse Efter |
| ---------------------------------- | ------ | ----------: | -----------: | --------------------- |
| `digital-marketing-meeting.jpg`       |    8688 × 5792    |      1500 × 1000       |      14,2 mb        |          236 kB             |
| `search-engine-optimization.jpg`   |    7360 × 4912    |     500 × 334        |      14,9 mb        |           61 kB            |
| `online-reputation-management.jpg` |   4404 × 2877     |      500 × 327       |      6,7 mb        |         47 kB           |
| `social-media-marketing.jpg`       |    5000 × 3451    |      500 × 345       |       14,2 mb       |          80 kB             |
| `brand-awareness.png`   |    1000 × 1000    |      1000 × 1000       |       63 kB        |            1 Kb           |
| `cost-management.png` |    1000 × 1000    |      300 × 300       |       41 kB       |          10 kB             |
| `lead-generation.png`       |   1000 × 1000    |      300 × 300       |      40 kB        |           6 kB            |

<br>

9. Hvilke elementer gjorde du til flex-containere?
```text
Header satte jeg til flex, og med flex-wrap: wrap;

main.content har jeg også sat display: flex; med en flex-wrap: wrap; på.

.marketing har jeg også sat display: flex; med en flex-direction: column; på.

.benefits har jeg sat display: flex; og flex-direction: column; på. Og flex: 0 1 300px; som bestemmer at benefits ikke må vokse, men må gerne blive mindre. og bredden er 300 px.

```


10. Hvilke gamle floats kunne fjernes?

```text
Jeg har fjernet floast fra .header nav og .benefits, og her blev der istedet tilføjet flexbox.

I media quyer kunne jeg fjerne begge floats. Da jeg gerne ville have indholdet i services til at stp under hinanden. Derfor er det sat til:
```

  ```css
    .services {
        flex-direction: column;
        padding: 32px;
      }
  ```
```text
  og floats er sat til:
```
  ```css
    .float-left {
            float: none;
        }

        .float-right {
            float: none;
        }
  ```


<br>


11. Hvilket breakpoint valgte du, og hvorfor valgte du netop dette?

```text
Jeg valgte breakpoint 760 px, fordi layoutet omkring denne skærmstørrelse ikke passe på indholdet. Det var specielt services boksene der gjorde mit udfald, da det var omkring de 760px, at indhold i dem, begyndte at stå mærkeligt.

Derfor under 760px, har jeg valgt at main.content skal står som flex-direction: column;
og at bla. mit problem med service boksens indhold, løses med fjerne float og sætte til dette:

```css
.services {
    flex-direction: column;
    padding: 32px;
  }
```

<br>

12. Hvordan ændrer layoutet sig på en mobil skærm?
```text
Alt indhold ligger sig som en lang kolonne. Så alle elementer ligger sig over hinanden.

Det er lavet sådan, at når det bliver en mobil skærm, så ligger elementerne .marketing og .benefit sig efter hinanden, istedet for ved siden af hinanden. Det skaber en bedre brugeroplevelse, og man undgå vandret scroll. 

Derudover så ved mobil skærm ligger nav sig under logo'et.

```

<br>

13. Hvad sker der ved 200 % zoom?
```text
Før gik teksten ud over deres bokse. Det skete fordi indholdet blev højere end boksen faste højde på 300px. Så ved at ændre boksenes css fra height til min-height løser vi faktisk problemet. For nu har alle bokse en min-height på 300px, og kan nu dermed vokse med indholdet.

```




---

# Kontrol af din løsning

## DEL 1 – Web Accessibility

- [x] Accessibility-baseline er dokumenteret.
- [x] `<title>` er beskrivende.
- [x] `<meta name="viewport">` er tilføjet.
- [x] Semantisk HTML er anvendt.
- [x] Rene layout-wrappers bruger et passende neutralt element, fx `<div>`.
- [x] Eksisterende CSS-selectors er kontrolleret og tilpasset efter semantiske HTML-ændringer.
- [x] Navigationen bruger et passende semantisk HTML-element.
- [x] Navigationen vises uden bullets og med horisontale menupunkter på større skærme.
- [x] Dokumentstrukturen er logisk.
- [x] Headingstrukturen er logisk.
- [x] Informative billeder har relevante `alt`-tekster.
- [x] Dekorative billeder bruger `alt=""`.
- [x] Anchor-links fungerer.
- [x] Horiseon-logoet fungerer som link til `index.html`.
- [x] Links kan identificeres.
- [x] Farvekontrast er kontrolleret.
- [x] Tastaturtest er gennemført.
- [x] Keyboard-fokus er tydeligt.
- [x] Siden er testet ved 200 % zoom.
- [x] Faste højder er vurderet.
- [x] CSS er ryddet op.
- [x] HTML er valideret.
- [x] Lighthouse Accessibility er kørt igen.
- [x] Accessibility-score er 100.

## DEL 2 – Web Performance

- [x] Performance-baseline er dokumenteret.
- [x] Billeddimensioner er undersøgt.
- [x] Filstørrelser er undersøgt.
- [x] Relevante billeder er konverteret til WebP.
- [x] HTML-referencer er opdateret.
- [x] Hero-billedets CSS-reference er kontrolleret.
- [x] Billedkvalitet er vurderet.
- [x] Network-panelet er anvendt til kontrol.
- [x] Lighthouse Performance er kørt igen.
- [x] Performance-score er 90 eller højere.

## DEL 3 – Responsive Webdesign

- [x] Layoutet er analyseret i Device Toolbar.
- [x] Headeren anvender et passende Flexbox-layout.
- [x] Hovedindholdet anvender et passende Flexbox-layout.
- [x] Overflødige floats er fjernet.
- [x] Billeder er responsive.
- [x] Problematiske faste størrelser er vurderet.
- [x] Der er tilføjet ét relevant CSS breakpoint med en media query (flere er tilladt, hvis de faktisk er nødvendige).
- [x] Navigationen fungerer på små skærme.
- [x] Siden er testet ved 320 px.
- [x] Siden er testet ved 480 px.
- [x] Siden er testet ved 768 px.
- [x] Siden er testet ved 1024 px.
- [x] Siden er testet ved 1440 px.
- [x] Der er ingen unødvendig vandret scrolling.
- [x] Siden fungerer ved 200 % zoom.
- [ ] Resultatet er sammenlignet med referencebilledet.

---

# Useful Links / Nyttige links

## Chrome DevTools

https://developer.chrome.com/docs/devtools/

## Lighthouse

https://developer.chrome.com/docs/lighthouse/

## HTML

https://developer.mozilla.org/en-US/docs/Web/HTML

## Web Accessibility

https://www.w3.org/WAI/

https://www.w3.org/WAI/tutorials/images/

https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html

https://www.w3.org/WAI/WCAG22/Understanding/reflow.html

## CSS Flexbox

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout

## Responsive Webdesign

https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design

## WebP

https://developers.google.com/speed/webp/

## HTML Validation

https://validator.w3.org/

---

# Aflevering

Aflever hele projektmappen.

Dokumentér desuden:

```text
Accessibility før / efter
Performance før / efter
Responsive test ved flere viewport-bredder
```

| Test                            | Før | Efter |
| ---------------------------------- | ------ | ----------: | 
| `Accessibility`       |    67    |      100       |   
| `Performance`       |    73    |      99       | 
| `Responsive test ved flere viewport-bredder`       |    Ikke responsiv til andre skærmstørrelser    |      Responsiv til alle skærmstørrelser      |    


Du skal kunne forklare mindst:

- tre accessibility-forbedringer

#### 1. primært landmark 
```text
Der manglede et primært landmark til at starte med. Det har betydet at for f.eks screenreaders har manglet layout struktur og ikke har vist hvad det vigtigste indhold på websiden var. Derfor tilføjede jeg et main-tag i html'en. Nu ved den hvad sidens primære indhold er.
```

#### 2. Farvekontrast
```text
Før var farvekontrasten for lav benefits søljen. En for lav konstrast, kan gøre elementer svære at se eller læse. Derfor er det vigtigt med en højt farvekontrast for accessibility. Jeg ændrede derfor baggrundsfarve i benefit til en lysere blå og tekstfarven til sort. Dermed fik jeg en kontrast der levede op til AAA.
```

#### 3. Alt-antributter
```text
Før var der ingen alt-antributter, hvilket betød at skærmlæsere ikke kunne aflæse billederne. Derfor har jeg tilføjet meningsfulde alt-antributter til billederne. Så nu kan skærmlæsere aflæse billederne. 
```

<br>

- to performance-forbedringer
#### 1. Billeder skalleret i dimensioner.
```text
Mange af billeder havde meget store dimensioner i forhold til, hvad de reelt bliver vist på websiden. Derfor skallerede jeg alle billederne til passende størrelse.  
```

#### 2. Billeder komprimeret og lavet til Webp
```text
Før fyldte billeder rigtigt meget med deres filstørrelser. Flere af dem fyldte mange mb, og det påvirkede web performance ved at gøre den langsommere. Ved at skalere billeder til mere passende størrelser, komprimere dem og lave dem til webp filer, så fik jeg formindsket filstørrelse gevaldigt. Og dermed er der. mindre siden skal indlæse, og dermed kan gøre det hurtigere.
```

<br>

- to responsive design-valg
#### 1. Flexbox
```text
Et valg jeg tog for at gøre siden mere reponsiv, var at style flexbox på flere af html-elementerne. Det var bla. på selve main, så hele hjemmesiden indhold kom i en flexbox, hvor den derudover også wrapper om sig selv, når indholdet er for bredt til wrapperen. På den måde bliver den automatisk responsiv.

Andre steder jeg brugte det var bla. i .marketing, hvor jeg satte flex-direction til column. Og det samme med benefits. Så står indholdet altid under hinanden i deres containers.


```

#### 2. Breakpoints med media quyer
```text
Selvom jeg har brugt flexbox med wrap, var siden ikke fuld responsiv. På de små skærme passede indholdet ikke. Derfor indførte jeg et breakpoints med media quyer på 760px. Derfor stylede jeg så de forskellige elementer med passende styling til mobilstørrelser.
```



---

# Afsluttende note

> Formålet er ikke kun at opnå høje Lighthouse-scores. Formålet er at lære at analysere eksisterende HTML og CSS, forbedre webtilgængelighed, optimere ressourcer og udvikle et robust responsive layout med begrundede tekniske valg.
