# Entertaining-bandana
Follow the line

![buh](https://github.com/nicolasbaez/Entertaining-bandana/blob/main/xp037.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
h = 255;
draw = (_) => {
  clear();
  noFill();
  beginShape();
  for (i = 1; i < 3; i += 0.1)
    for (j = 1; j < 6; j += 0.6) {
      r = w * 2 * noise(i, j, w);
      x = r * sin(i) * cos(j);
      y = r * sin(i) * sin(j);
      z = r * cos(i);
      stroke(h, 0, h);
      curveVertex(x, y, z);
      stroke(h);
      vertex(x, y, z);
    }
  endShape();
  w -= 0.01;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp037.gif", 628, { delay: 0, units: "frames" });
  }
};
