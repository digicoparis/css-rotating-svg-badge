# css rotating svg badge

A simple rotating Svg badge, using Css & HTML only. Infinite loop animation.

[Frontend Tutorial] How to make a badge with rotating text (infinite loop) for any website? Fast tutorial with Illustrator, Html & Css

There are many ways to achieve that. I found it faster using a software (Illustrator, Figma...) rather than creating text and splines programmatically from code.

Step 1. Make your badge in Adobe Illustrator / Figma / whatever. In Illustrator, this involve to make a perfect circle path, then use this path for "Path text" tool (T).

Step 2. Export your badge as .SVG file (embedded format, only outlines).

Step 3. Include your SVG in website/app assets, so your code can access it.

Step 4. Create the basic HTML structure for the badge, it looks like this:

<div>
<img src="files/Texte-cercle-rotating-01.svg" alt="badge" width="100" height="100" class="rotating-text-01">
</div>

Class is the important information as we'll use it next for animation ("rotating-text-01").

Step 5. Animate the SVG file with matching CSS:

<style>
.rotating-text-01{
  animation-name: rotateA;
  animation-duration: 30s;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}

@keyframes rotateA{
  from{ transform: rotate(-360deg); }
  to{ transform: rotate(360deg); }
}
</style>

Step 6. Tweak "animation-duration" CSS property to your needs, so it's not too slow or too fast, according to length of text and your needs.

Step 7. Enjoy! It's a very lightweight animation as it doesn't involve any JavaScript. Perfect for mobile devices (my SVG file is 7 Kb, code less than 0.1 Kb), it won't hurt any smartphone performance.
