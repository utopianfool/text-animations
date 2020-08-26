# Animated Text Carousel

This animation has two examples of text appearing from the left and then disappearing from whence it came. Longer sentences can take a bit too long to disappear.

Edit the speed of the data-period in the html and javascript. This animation is responsive and made using a single span. Add text at the begining of the sentence and have the ending change or type out whole sentences. [Demo](http://phil.devnation.co.uk/text-animations/carousel.php)

## HTML

```
<section id="Text carousel"> <!-- Animated text carousel -->
    <h1>This animation is
        <span
            class="txt-rotate"
            data-period="1000"
            data-rotate='[ "fun.", "simple.", "pure JS.", "pretty.", "easy to customise" ]'></span>
    </h1>
    <h2>Made using a single &lt;span&gt; and is responsive!</h2>
    <p><span class="txt-rotate"
            data-period="1000"
            data-rotate='[ "Lets try aimating whole sentences...", "Like the one before."]'></span>
</section> <!-- end of animated text carousel -->
```

## Javascript

```
// Text carousel animation
var TxtRotate = function(el, toRotate, period) {
  this.toRotate = toRotate;
  this.el = el;
  this.loopNum = 0;
  this.period = parseInt(period, 10) || 1000; // edit period to change speed of typing, also edit data-period in html span. Original period 10 || 2000
  this.txt = '';
  this.tick();
  this.isDeleting = false;
};
```