# pacman exercise
<html>
<SCRIPT>
    var pos = 0;
    const pacArray = [
        ['PacMan1.png', 'PacMan2.png'],
        ['PacMan3.png', 'PacMan4.png']
    ];
    var direction = 0;
    var focus = 0;

  function Run() {
        let img = document.getElementById("PacMan");
        let imgWidth = img.width
        focus = (focus + 1) % 2;
        direction = checkPageBounds(direction, imgWidth);
        img.src = pacArray[direction][focus];
        if (direction) {
            pos -= 20;
            img.style.left = pos + "px";
        } else {
            pos += 20;
            img.style.left = pos + 'px';
        }
        // Use setTimeout to call Run every 200 millesecs
        setTimeout(Run, 100);
    }

  function checkPageBounds(direction, imgWidth) {
        //
        // Complete this to reverse direction on hitting page bounds
        // 
        if (pos <= 0) {
            direction = 0;
        } else if (pos + imgWidth >= window.innerWidth) {
            direction = 1;
        }
        return direction;
        }
        
    
</SCRIPT>

<body>
    <img id="PacMan" src="PacMan1.png" width='200' onclick="Run()" style="position:absolute"> </img>
  <p>MIT License

Copyright (c) 2020 John Williams

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.</p>
</body>

</html>
