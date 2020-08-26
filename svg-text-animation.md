# SVG Text Animation

All SVG here with the typing text example. [Demo](http://phil.devnation.co.uk/text-animations/svg-text.php)

## HTML

```
<section id="svgtext"> <!-- SVG text animation -->
    <div class="svg-container">
        <svg width="100%" height="100%">
             <path id="path">
                    <animate attributeName="d" from="m0,110 h0" to="m0,110 h1100" dur="6.8s" begin="0s" repeatCount="indefinite"/>
            </path>
            <text font-size="18" font-family="Montserrat" fill='hsla(36, 95%, 2%, 1)'>
                <textPath xlink:href="#path">I'm An Animated Typing Example all made from svg textPath I'm All SVG.
                </textPath>
            </text>
        </svg>
    </div>
</section> <!-- end of SVG text animation -->
```