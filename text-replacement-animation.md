# Text Replacement Animation

This animation creates a string of random characters to the character being generated as it types the sentence. Only one use then it stops. [Demo](http://phil.devnation.co.uk/text-animations/replacement.php)

## HTML

```
<section id="text-replacement"> <!-- Text Replacement animation -->
    <h1 id="op" class="header">Text Animation and some random text to expand the amount it aniamtes</h1>
</section>
```

## CSS

```
/* Text replacement animation ================================= */
h1 {
  width:900px;
  margin: 0px auto;
  font-weight:200;
  font-size:3em;
}

.header{
  display:none;
}
```

## Javascript

```
// Text replacement reveal animation

var SPY = function() {
  function e(a, d, b) {
    var c, f, g, h;
    b == a.length ? k.animationComplete = !0 : (g = d.innerHTML, h = Math.floor(21 * Math.random() + 5), c = 32 == a[b] ? 32 : a[b] - h, f = setInterval(function() {
      d.innerHTML = g + String.fromCharCode(c);
      c == a[b] ? (clearInterval(f), c = 32, b++, setTimeout(function() {
        e(a, d, b);
      }, 10)) : c++;
    }, 5));
  }
  var k = {};
  return k = {animationComplete:!1, text:function(a) {
    this.animationComplete = !1;
    a = document.getElementById(a);
    for (var d = a.innerHTML, b = [], c = 0;c < d.length;c++) {
      b.push(d.charCodeAt(c));
    }
    a.innerHTML = "";
    e(b, a, 0);
  }};
}();


$( 'document' ).ready(function() {
  
  // Hide header
  $( '.header' ).hide();
  // Transition background
  $( '.london' ).fadeIn( 1200 );
  
  
  // Timeout for crypto text
  setTimeout( function() { 
    $( '.header' ).fadeIn( 'slow' );
      SPY.text( 'op' );
  }, 1000);
  
});
```