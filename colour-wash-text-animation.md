# Colour Wash Text Animation

Animate the text colour in a wash from top to bottom with this CSS animation effect [Demo](http://phil.devnation.co.uk/text-animations/wash.php)

## HTML

```
<section id="text-colour"> <!-- Colour Wash text animation -->
    <p class="one">"Drink and be merry.</p>
    <p class="two">If only to forget</p>
    <p class="three">all that matters</p>
    <p class="four">and is important."</p>
    <p class="five">- Utopian Fool</p>
</section> <!-- end of Colour Wash text animation -->
```

## CSS

```
/* Text-colour animation ================================== */
#text-colour {
    width: 600px;
    float: none;
    margin: 50px auto;
    text-align: center;
}
#text-colour p {
    font-size: 48px;
    color: #111;
    line-height: 50px;
    display: inline-block;
    text-align: justify;
    margin: 20px;
}
p.one {
    animation: anione 30s linear infinite;
}
p.two {
    animation: anione 30s linear 1s infinite;
}

p.three {
    animation: anione 30s linear 2s infinite;
}

p.four {
    animation: anione 30s linear 3s infinite;
}

p.five {
    animation: anione 30s linear 4s infinite;
}
@keyframes anione {
    0%,100% {
    color: #111;
    }

    5%,95% {
        color: #3b3643;
    }

    10%,90% {
        color: #897d9b;
    }

    15%,85% {
        color: #9b7d99;
    }

    20%,80% {
        color: #9b837d;
    }

    25%,75% {
        color: #999b7d;
    }

    30%,70% {
        color: #7d9b83;
    }

    35%,65% {
        color: #7d909b;
    }

    40%,60% {
        color: #837d9b;
    }
     50% {
        color: #9b7d95;
     }
}
```