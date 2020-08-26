# Green Sock Reveal Animation

This animation reveals the text by moving a block that is placed over the text using Green Sock. You have to include the Green Sock Javascript library. [Demo](http://phil.devnation.co.uk/text-animations/reveal.php)

<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/gsap/1.20.4/TweenMax.min.js"></script>

## HTML

```
<section id="fading-in"> <!-- Green sock reveal animation -->
    <div class="text-reveal">
        <div class="text-stuff">
            <p>This text is going to be revealed by GREEN SOCK moving a div.</p>
            <div class="text-cover">
            </div>
        </div>
    </div>
</section> <!-- end of Green sock reveal animation -->
```

## CSS

```
/* green sock text animation */
.text-stuff {
    margin-top: 50px;
    position: relative;
    width: 900px;
    color: #333;
    font-size: 30px;
    overflow: hidden; 
}
.text-cover {
    position: absolute;
    top: 0;
    left:0;
    height: 100px;
    width: 900px;
    background-color: #fff;
    z-index: 1020;
}
```

## Javascript

```
// Text cover animation
    TweenMax.to(".text-cover", 5, {ease: SteppedEase.config(50), left:1000, yoyo: true, repeat: 7});
```