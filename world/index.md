---
layout: default
title: The World of Kolijar
permalink: /world/
spoiler: None
---

# The World of Kolijar

Kolijar is an island with three kingdoms, each ruled by an ancient house. The three houses are bound together by the **Trinity Accord**, a centuries-old mutual defence pact.

| Kingdom | Ruling house | Sigil | Capital / seat |
|---------|--------------|-------|----------------|
| **Kreturia** | Curatal | Lion on blue | Drivaran castle (village of Teyerun below) |
| **Harenjun** | Lome | Stag on green | Verekel |
| **Lustralia** | Desallez | Phoenix on red | Pokaril |
## Kreturia pronounced kreh-TOO-ree-ah
Bright and almost fairy-like, with flowers and colour everywhere. Ruled by King Herrellus and Queen Reyira, seat of power is Drivaran castle

<div class="sigil-wrap">
  <img class="sigil-zoom" width="128" height="128" alt="curatal_128" src="https://github.com/user-attachments/assets/168ea521-e743-4218-aa2c-7b7cc9511101" />
</div>

## Harenjun
Forests and snow-capped mountains. Its people are artisans, such as bakers and sculptors, who love music and keep libraries devoted to the arts. Ruled by Parell and Maris Lome. Princesses Merinda and Narenna.

<div class="sigil-wrap">
  <img class="sigil-zoom" width="128" height="128" alt="lome_128" src="https://github.com/user-attachments/assets/493dc2fa-feb3-477d-b2da-fc15f4f43060" />
</div>


## Lustralia pronounced lus-TRAH-lee-ah
Structured, militaristic and full of statues. Its coastline is called Teverin. Ruled by Janto and Generra Desallez. Prince Jeraldian.

<div class="sigil-wrap">
  <img class="sigil-zoom" width="128" height="128" alt="desallez_128" src="https://github.com/user-attachments/assets/d3c00053-3e04-41a5-b65b-ce10682f616c" />
</div>

## The Crystal
The Kolijar crystal is the island's beating heart and the source of all power across the three kingdoms.

## The First Order of Sorcery
A mysterious order of sorcerers and knights. See the [glossary]({{ "/world/glossary/" | relative_url }}).

## Quotes
Explore memorable lines from the world of Kolijar in the [Quotes page]({{ "/world/Quotes/" | relative_url }}).


<!-- Magnifier styles and script -->
<style>
.sigil-wrap{display:inline-block;position:relative;margin:0.25rem}
.sigil-zoom{width:128px;height:128px;cursor:zoom-in;display:block}
.magnifier-lens{position:absolute;border:2px solid rgba(0,0,0,0.6);border-radius:50%;width:120px;height:120px;pointer-events:none;background-repeat:no-repeat;display:none;box-shadow:0 4px 12px rgba(0,0,0,0.25);z-index:1000}
@media (max-width:600px){ /* disable lens on very small screens */ .magnifier-lens{display:none} }
</style>

<script>
(function(){
  function makeMagnifier(img, zoom){
    var lens = document.createElement('div');
    lens.className = 'magnifier-lens';
    document.body.appendChild(lens);

    var rect, cx, cy;
    function moveLens(e){
      e.preventDefault && e.preventDefault();
      var pos = getCursorPos(e, img);
      var x = pos.x; var y = pos.y;
      if(x > img.width || x < 0 || y > img.height || y < 0){ lens.style.display = 'none'; return; }
      lens.style.display = 'block';

      // position lens centered on cursor
      var lensW = lens.offsetWidth/2;
      var lensH = lens.offsetHeight/2;
      var pageX = pos.pageX - lensW; // using page coords so lens can be absolutely positioned on body
      var pageY = pos.pageY - lensH;
      lens.style.left = pageX + 'px';
      lens.style.top = pageY + 'px';

      // background position (ratio)
      var bgX = -((x * cx) - lens.offsetWidth/2);
      var bgY = -((y * cy) - lens.offsetHeight/2);
      lens.style.backgroundPosition = bgX + 'px ' + bgY + 'px';
    }

    function enterHandler(e){
      rect = img.getBoundingClientRect();
      lens.style.width = '120px';
      lens.style.height = '120px';
      cx = (img.naturalWidth / img.width) * zoom;
      cy = (img.naturalHeight / img.height) * zoom;
      lens.style.backgroundImage = 'url(' + img.src + ')';
      lens.style.backgroundSize = (img.width * cx) + 'px ' + (img.height * cy) + 'px';
      lens.style.display = 'block';
      moveLens(e);
    }

    function leaveHandler(){ lens.style.display = 'none'; }

    function getCursorPos(e, img){
      var a = img.getBoundingClientRect();
      var pageX = (e.touches ? e.touches[0].pageX : e.pageX);
      var pageY = (e.touches ? e.touches[0].pageY : e.pageY);
      var x = pageX - (a.left + window.pageXOffset);
      var y = pageY - (a.top + window.pageYOffset);
      return {x: x, y: y, pageX: pageX, pageY: pageY};
    }

    // events
    img.addEventListener('mousemove', moveLens);
    img.addEventListener('touchmove', moveLens);
    img.addEventListener('mouseenter', enterHandler);
    img.addEventListener('touchstart', enterHandler);
    img.addEventListener('mouseleave', leaveHandler);
    img.addEventListener('touchend', leaveHandler);

    // cleanup on page unload
    window.addEventListener('unload', function(){ lens.parentNode && lens.parentNode.removeChild(lens); });
  }

  // attach to all images with class "sigil-zoom"
  document.addEventListener('DOMContentLoaded', function(){
    var imgs = document.querySelectorAll('img.sigil-zoom');
    imgs.forEach(function(img){
      // wait until image is loaded to get naturalWidth
      if(img.complete){ makeMagnifier(img, 2.5); }
      else { img.addEventListener('load', function(){ makeMagnifier(img, 2.5); }); }
    });
  });
})();
</script>
