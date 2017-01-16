# Cross Browser

## Intro

Det är lätt att drabbas av **Browser Bias**. Eftersom man oftast använder sig utav samma webbläsare hela tiden är det svårt att tänka sig att sidan inte skulle fungera på samma sätt på en annan webbläsare. Verkligheten är ju dock att olika webbläsare visar en hemsida på olika sätt, och nu snackar vi inte bara om *Internet Explorer*. För att lösa många kompabilitetsproblem mellan olika webbläsare brukar man använda **vendor-prefix**. Specifika nyckelord som man använder framför css-egenskapen för att visa att egenskapen ska visas på ett speciellt sätt beroende på vilken webbläsare du använder. Nedan är de mest vanliga prefix som används i nuläget.

| Vendor | prefix |
|---|---|
| Apple | –webkit– |
| Google | -webkit- |
| Mozilla | -moz- |
| Opera | -o- |
| Microsoft | -ms-   |


Många prefix är inte nödvändiga att ha längre men det kan ändå vara säkrast att ha med. Om vi tar t.ex. `border-radius`:

```css
.box{
    -webkit-border-radius: 4px;
    border-radius: 4px;
}
```

I nästan samtliga fall funkar det att bara skriva `border-radius: 4px;` medan i äldre versioner av Safari kan `-webkit-` behöva användas. Att lägga till dessa prefix är ett enkelt sätt att gardera sig mot eventuella problem som kan uppstå med äldre webbläsare. Dock så löser detta ovan inte alla problem, vi har fortfarande kompabilitetsproblem med IE t.ex. som inte klarar av rundade hörn på detta sätt. För att veta vilka egenskaper vi måste använda prefix på och vilka vi kan skippa kan man använda **Can I Use** samt **Should I Prefix** som finns länkade nedan.

## Länkar att använda


##### Can I Use?

Främsta källan att använda och ett bra verktyg är: **[Can I Use?(Länk)](http://caniuse.com/)**. Här ser man vilka egenskaper som stöds i vilka webbläsare. Tjänsten används mest för att kolla "hur grönt det är" d.v.s om det stöds i flera av de stora webbläsarna. Är det en grön låda för webbläsare är det fullt implementerat. Gult betyder att det är implementerat men det finns många buggar. Rött betyder att det inte fungerar alls.

Förutom att se vilka browsers som stödjer vad kan man även se anteckningar från andra användare och samlade resurser om just den egenskapen man undersöker så som kända problem:

![Known Issues](http://i.imgur.com/ZMTIM7R.png)

_Här kan man se hur man kan lösa vissa problem om man stöter på ett problem som är bundet till en viss webbläsare, så som att flexbox inte fungerar i Edge som det ska eller dylikt. Här brukar det även finnas lösningar på dessa problem_

Det finns även en hel del resurser att tillgå, tutorials och liknande kopplat till en viss egenskap man har sökt på:

![Resources](http://i.imgur.com/FP1of5m.png)

##### Should I Prefix?

Du kan kolla vilka egenskaper som behöver använda prefix och vilka prefix man måste använda och på vilket sätt med **[Should I prefix?(Länk)](http://shouldiprefix.com)**. Detta är dock ett urval och man får ta innehållet med en nypa salt.

_Should I Prefix_ berättar vad du behöver använda för prefix eller om du inte behöver använda det alls. Som tidigare nämnts behövs oftast inte t.ex. `-webkit-`prefix i de flesta browsers längre. Dock så skadar det inte att faktiskt ha med prefixet. Det kommer helt enkelt att ignoreras om det inte behövs, men om det behövs kommer det att användas, så genom att använda det skyddar man sig lite extra. Tänk på att ordningen är viktig när man använder prefixes. Man vill ha den "riktiga" egenskapen sist, d.v.s den som är fastställd av **W3C**. Övriga prefix är just från olika *vendors*, alltså olika företag som har webbläsaren.


#### HTML5 Please

Ännu en sidan som kollar upp vilka egenskaper vi kan använda i vilka browsers är: **[html5please.com](http://html5please.com/)**. Här finns kortare beskrivning och tips kopplat till varje egenskap som du kan tänkas använda.

### Feature queries (@supports)

En nyare specifikation i CSS är den `@supports`-querien. Ungefär som en media query kan man här kolla efter om webbläsaren som används stödjer en viss egenskap. Syntaxen är liknande media queries så en är väldigt lätt att använda. Man skriver en `@supports`-query på samma sätt som media query och kollar efter en viss egenskap:

```css
/* If this browser supports flex */
@supports (display: flex) {
    /* Use flex */
    .box { 
        display: flex; 
    }
}

```


Här är en mindre introduktion till användande av `@supports`:
* [SitePoint | Introduktion to @supports (Länk)](https://www.sitepoint.com/an-introduction-to-css-supports-rule-feature-queries/)

### Autoprefixer

Autoprefixer används i stor utsträckning av nästan samtliga webbutvecklare. Det är bra att få in en vana att alltid använda standard prefixes när man skriver kod själv. Dock så finns det verktyg som hjälper en att automatiskt prefixa våra egenskaper med hjälp av `Can I Use`. 

Autoprefixer använder sig utav _can i use_-databaser för att hitta vilka egenskaper som ska prefixas och vilka som inte behöver det. Detta kan vara bra som en sista grej man gör innan man pushar upp sin sida. Det finns många sätt att använda verktyget och oftast är det automatiseras med olika byggverktyg. Dock finns det en sidan som man kan använda för denna uppgift som är lite enklare att använda:
**[Autoprefixer Online
(Länk)](https://autoprefixer.github.io/)**



