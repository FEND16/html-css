# Positionering

## Länkar för vidare läsning

* [Grunderna i positionering](http://learnlayout.com/)
    - Snabb tutorial som går igenom grunderna inom all sorts positionering. Float, position, margin, padding och flexbox.
* [CSS-Tricks | Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
    - Reference till det mesta som har med flexbox att göra
* [W3Schools - CSS Selectors](http://www.w3schools.com/cssref/css_selectors.asp)
    - Referens till CSS-selektorer att använda.
* [Smashing Magazine - CSS specificity](https://www.smashingmagazine.com/2007/07/css-specificity-things-you-should-know/)
    - Vilka selektorer som prioriteras över vilka.


## Förarbete!

För att kunna välja rätt element kan det vara bra att känna till vissa css-selektorer. Spela igenom spelet **CSS Diner** för att bekanta dit med de olika selektorerarna som finns. Det är ett rätt långt spel och tar upp vissa selektorer som man sällan använder så man behöver inte kötta igenom hela.

**[CSS Diner - CSS Game](https://flukeout.github.io/)**

Spela igenom spelet **Flexbox Froggy** för att lära dig grunderna i Flexbox. Riktigt kul!

**[Flexbox Froggy](http://flexboxfroggy.com/)**


## Övning 1

Återskapa följande layouts med hjälp av Flexbox. Ta hjälp av länkarna längst upp om du fastnar. Specieltl CSS-tricks referens.

![Flexy 1](http://i.imgur.com/19wiJL9.png)

![Flexy 2](http://i.imgur.com/8a8jiN2.png)


## Övning 2

Använd koden nedan för att lösa övningarna som kommer efter koden. Allt ska gå att lösa med flexbox och genom att välja rätt element.

###Kod

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>CSS Selectors</title>
    <link rel="stylesheet" href="main.css">
</head>
<body>
    <section class="container">
        <div class="square">
            <div class="inner-square"></div>
        </div>
        <div class="square">
            <div class="inner-square"></div>
        </div>
        <div class="square">
            <div class="inner-square"></div>
        </div>
        <div class="square">
            <div class="inner-square"></div>
        </div>
    </section>  
</body>
</html>
```

```css

body, html{
    min-height: 100%;
    height: 100%;
    width: 100%;
    display:flex;
    flex-direction: column;
    justify-content: center;
}
.container{
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
    flex: 1;
}
.square{
    width: 200px;
    height: 200px;
    background: teal;
}
.inner-square{
    width: 100px;
    height: 100px;
    background: salmon;
}
```

#### Övningar till koden ovan

* Gör så att alla `.square` hamnar längst ner på sidan.
* Gör så att alla `.inner-square` ligger i högra övre hörnet av varje `.square.`.
* Gör så att alla `.inner-square` ligger i nedre högra hörnet av `.square`.
* Gör så att varannan `.inner-square` är positionerad i nedre hörnet av `.square`.
* Gör så att bara den tredje `.square` har en annan bakgrundfärg.
* Lägg till ytterligare 4 square med en inner-square. (D.v.s kopiera redan existerande kod så att du har 8 div).
* Det börjar bli lite trångt, så använd `flex-flow` för att jämna ut fördelningen av divar så att de flyttas ner om de inte får plats.
* Använd `order` för att förflytta diven med annorlunda färg så att den ligger sist bland alla divar.

## Övning 3

Positionera era element på inlämningsuppgiften i javascript med hjälp av flexbox! Flexa allt! Huah!