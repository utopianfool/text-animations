# Rolling Text Animation

This lovely banner text is a nice touch. Be aware! Its not responsive in its current state. [Demo](http://phil.devnation.co.uk/text-animations/rolling.php)

## HTML

```
<section id="rolling-text"> <!-- Rolling text animation -->
    <div class="page">
        <div id="home-news">
            <div class="home_header">
                <strong>Spend</strong>
                <span>your time coding</span>
            </div>
            <div class="home_header">
                <strong>Javascript</strong>
                <span>works well with CSS </span>
            </div>
            <div class="home_header">
                <span>explore. Write.</span>
                <strong>share</strong>
            </div>
        </div>
    </div>
</section> <!-- end of rolling text animation -->
```

## CSS

```
/* Rolling text animation styles ============================ */
#rolling-text {
    width: 100%;
    font: 400 12px/1 'Helvetica Neue', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  background: -webkit-linear-gradient(90deg, #4CB8C4 10%, #3CD3AD 90%); /* Chrome 10+, Saf5.1+ */
  background:    -moz-linear-gradient(90deg, #4CB8C4 10%, #3CD3AD 90%); /* FF3.6+ */
  background:     -ms-linear-gradient(90deg, #4CB8C4 10%, #3CD3AD 90%); /* IE10 */
  background:      -o-linear-gradient(90deg, #4CB8C4 10%, #3CD3AD 90%); /* Opera 11.10+ */
  background:         linear-gradient(90deg, #4CB8C4 10%, #3CD3AD 90%); /* W3C */ 
}
.page{
  margin:0 auto;
  padding: 20px;
  width: 800px;
}
#home-news{
  font-size: 40px;
    text-align:center;
    text-transform:uppercase;
    color:#464646;
    height: 45px;
    line-height: 45px;
    overflow:hidden;
    position:relative;
}.home_header {
    position:absolute;
    width:100%;
    z-index:99;
    color:#000;
    text-shadow: 0 1px 1px rgba(0, 0, 0, 0.3);
}
.home_header_on {
    z-index:100;
}.home_header strong {
    color: white;
}.home_header span, .home_header strong {
    position:relative;
    top:-50px;
}.home_header_on *:nth-child(1) {
     top: 0;
    -webkit-transition: top .6s ease-in-out;
    -moz-transition: top .6s ease-in-out;
     transition: top .6s ease-in-out;
}.home_header_on *:nth-child(2) {
    top: 0;
    -webkit-transition: top .6s ease-in-out .15s;
    -moz-transition: top .6s ease-in-out .15s;
    transition: top .6s ease-in-out .15s;
}.home_header_on *:nth-child(3) {
    top: 0;
    -webkit-transition: top .6s ease-in-out .3s;
    -moz-transition: top .6s ease-in-out .3s;
    transition: top .6s ease-in-out .3s;
}.home_header_out *:nth-child(1) {
    top: 50px;
    -webkit-transition: top .6s ease-in-out;
    -webkit-transition: top .6s ease-in-out;
    -moz-transition: top .6s ease-in-out;
}.home_header_out *:nth-child(2) {
    top: 50px;
    -webkit-transition: top .6s ease-in-out .15s;
    -moz-transition: top .6s ease-in-out .15s;
    transition: top .6s ease-in-out .15s;
}.home_header_out *:nth-child(3) {
    top: 50px;
    -webkit-transition: top .6s ease-in-out .3s;
    -moz-transition: top .6s ease-in-out .3s;
    transition: top .6s ease-in-out .3s;
}
```

## Javascript

```
// Rolling text animation
function switchClass(i) {
   var lis = $('#home-news > div');
   lis.eq(i).removeClass('home_header_on');
   lis.eq(i).removeClass('home_header_out');
    lis.eq(i = ++i % lis.length).addClass('home_header_on');
    lis.eq(i = ++i % lis.length).addClass('home_header_out');
    setTimeout(function() {
        switchClass(i);
    }, 3500);
}

$(window).load(function() {
   switchClass(-1);
});
```