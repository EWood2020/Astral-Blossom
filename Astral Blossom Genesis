function setup() {
  // Increased canvas size for higher resolution
  createCanvas(1920, 1080);
}

function draw() {
  background(0); // Black background for deep space effect
  translate(width / 2, height / 2); // Centering the drawing
  
  // Modify these parameters to play with the fractal's appearance
  let branches = 4; // Number of branches per split
  let depth = 8; // Depth of recursion, careful with increasing too much
  
  // Initial call to the more complex fractal function
  drawComplexFractal(0, 0, 150, -PI / 2, depth, branches);
  noLoop(); // Disable continuous drawing
}

function drawComplexFractal(x, y, len, angle, depth, branches) {
  if (depth == 0) {
    return;
  }

  // Parameters for visual variation
  let lenShrink = random(0.5, 0.7); // Length shrink factor per iteration
  let angleOffset = PI / 6; // Angle variation between branches

  // Draw branches
  for (let i = 0; i < branches; i++) {
    let newAngle = angle + random(-angleOffset, angleOffset);
    let newLen = len * lenShrink;
    let newX = x + cos(newAngle) * newLen;
    let newY = y + sin(newAngle) * newLen;

    // Use color to represent depth
    let col = lerpColor(color(255, 100, 0, 150), color(0, 100, 255, 150), depth / 10);
    stroke(col);
    strokeWeight(depth * 1.5); // Thicker lines for more depth
    line(x, y, newX, newY);

    // Recursive call
    drawComplexFractal(newX, newY, newLen * lenShrink, newAngle, depth - 1, branches);
  }
}
