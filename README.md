float  a, b;
int  m, n, o, p, s;
void setup() {

  size(400, 500);
  background(255);
  colorMode(HSB, 360, 100, 100);
  a=1.0/400*width;
  b=1.0/500*height;
  m=100;
  n=100;
  o=100;
  p=100;
  s=0;      
}

void draw() {

  background(148,49,56);
  
  //céu
  fill(148,39,86);
  rect(0, 350*b, 400*a, 200*b);
  
  //nave
  fill(148,29,100);
  arc(200*a, 50*b, 100*a, 50*b, radians(180), radians(360), CHORD);
  fill(148,39,86);
  arc(200*a, 50*b, 350*a, 100*b, radians(0), radians(180), CHORD);

  //cidade
  fill(148,49,56);
  rect(0, 470*b, 400*a, 50*b);
  rect(0, 460*b, 40*a, 10*b);
  rect(10*a, 460*b, 10*a, -30*b);
  rect(200*a, 470*b, 30*a, -100*b);
  rect(180*a, 470*b, 20*a, -80*b);
  rect(230*a, 470*b, 20*a, -60*b);
  rect(310*a, 470*b, 30*a, -30*b);
  arc(325*a, 440*b, 30*a, 20*b, radians(180), radians(360), CHORD);
  rect(360*a, 470*b, 10*a, -20*b);

  //escudo 
  fill(148,29,100);
  rect(0, 250*b, 400*a, 50*b);

 //bombas
  fill(0);
  ellipse(50*a, m*b, 20*a, 20*b);
  ellipse(150*a, n*b, 20*a, 20*b);
  ellipse(250*a, o*b, 20*a, 20*b);
  ellipse(350*a, p*b, 20*a, 20*b);
  m= m + int(random(0, 5));
  n = n + int(random(0, 5));
  o= o + int(random(0, 5));
  p= p + int(random(0, 5));
  if (m >= 350)
    m=100;
  if (n>= 350)
    n=100;
  if (o>= 350)
    o=100;
  if (p>= 350)
    p=100;
    
//Pontuação
  text("Pontos:" +s, 50, 20);
}
void mousePressed() {
  if (mouseY>=250 && mouseY<=300 && m>=250 && m<=300
    || mouseY>=250 && mouseY<=300 && n>=250 && n<=300
    || mouseY>=250 && mouseY<=300 &&  o>=250 && o<=300
    || mouseY>=250 && mouseY<=300 &&  p>=250 && p<=300) {
    if (m>=250 && m<=300)
      m=100;
    if (n>=250 && n<=300)
      n=100;
    if (o>=250 && o<=300)
      o=100;
    if (p>=250 && p<=300)
      p=100;
    s=s+1;
  }

    }
