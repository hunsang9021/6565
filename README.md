# 6565

var playMode = 'sustain';
var sample;

function setup() {
  createCanvas(710,50);
  soundFormats('mp3', 'ogg');
  sample = loadSound('assets/Damscray_-_Dancing_Tiger_02.mp3');
}

function draw() {
  background(255,255,0);
  var str = 'Click here to play! Press key to toggle play mode.';
  str += ' Current Play Mode: ' + playMode+'.';
  text(str, 10, height/2);
}

function mouseClicked() {
  sample.play();
}
function keyPressed(k) {
    togglePlayMode();
}

function togglePlayMode(){
  if (playMode == 'sustain'){
    playMode = 'restart';
  }
  else {
    playMode = 'sustain';
  }
  sample.playMode(playMode);
}
