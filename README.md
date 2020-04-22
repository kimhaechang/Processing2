```
void setup(){
  size(500,500);
  strokeWeight(16);
  stroke(0,255,0);
}
void draw(){
  if(mousePressed)
   line(pmouseX, pmouseY, mouseX, mouseY);
}
```
설명 : void setup에서 화면의 크기는 500*500이고 void draw에서 마우스와 상호작용하여 마우스 클릭 시 선을 그어주게 되는데 이 때 void setup에서 strokeWeight를 통해 선의 굵기는 16pts, stroke를 통해 색은 초록색을 띄고있는 펜을 형성하게끔 하는 코드입니다.
```
void setup() {
  size(800, 300);
  textSize(128);
}
int i, dir=1, sp=1;
void draw() {
  fill(0);
  background(128);
  fill(0,255,0);
  text("Andong", i, 250);
  if (i>width-128/2*7) dir=-1;
  if (i<0) dir=1;
  i= i+dir*sp;
}
void keyPressed(){
  sp = key-'0';
}
```
설명 : void setup 에서 화면의 크기는 800*300이고 글씨의 크기를 128로 지정해주고 있습니다. void draw에서는 실행되어질때 마다 background를 통해 항상 검은색이 나오게 해주었고 text를 통해 Andong 이라는 문자를 바로윗줄 fill 을 통하여 색은 초록색으로 하고 위치는 계속 변하도록 변수로 두었습니다. 
void keyPressed는 키보드의 입력값에 따라 속도가 변하도록 선언 해 주는데 이때 key 값은 ASCII 값이기때문에 정수로 변환하기 위하여 '0'을 빼주어야 합니다. 마지막으로 void draw 에서 if 문을 통하여 문자열이 오른쪽 끝 지점에 닿았을 시 다시 방향을 반대로 돌려주고 void keyPressed를 통하여 얻은 sp 값을 통해 지점에 닿지 않았을 경우 속도가 키보드 값에 따라 변하면서 계속 오른쪽으로 이동하도록 선언 해 줍니다.
```
PFont f;
void setup() {
  size(640, 360);
  f = createFont("굴림",30);
  textFont(f);
}

void draw() {
  background(0);
  float c = map(mouseX, 0, width, 0, 255);
  float d = map(mouseX, 0, width, 0, 200);
  fill(255, c, 0);
  rect(width/2-80, height/2-25, d, 30);
  fill(0);
  text("컴공 화이팅!",width/2-80,height/2);
}
```
설명 : 먼저 문자열의 서식을 지정해주기 위해 PFont를 변수 f로 선언 해주고 creatFont를 통해 굴림체에 크기는 30으로 하여서 f에 저장합니다. 마지막으로 문자열의 서식을 미리 지정해놓은 f로 쓴다는 textFont(t)를 선언 해줍니다. 화면의 크기는 640*360이며 void draw에서 rect를 통해 화면 중심근처에 사각형을 형성하여 주고 사각형의 가로크기를 변수로 지정해 주고 바로 윗줄의 사각형의 색을 지정해주는 fill에서 Green부분을 변수로 지정 해주는데 마우스가 오른쪽으로 이동하면서 값이 변화 하도록 하기 위해서 map 함수를 사용 해 줍니다. 결론적으로 마우스 오른쪽으로 이동하면 노란색 사각형이 형성되는데 이 때 숨겨진 글씨 컴공 화이팅!을 나오게 하기위하여 text를통해 선언 해 주고 색은 배경색과 동일한 검은색으로 선언 해 줍니다.
```
void setup(){
  size(300,800);
  rectMode(CENTER);
}
void draw(){
  background(0);
  fill(255,140,0);
  ellipse(80,230,45,45); // 얼굴
  fill(255,140,0);
  ellipse(220,230,45,45); // 왼쪽 귀
  fill(255,140,0);
  ellipse(150,300,200,200); // 오른쪽 귀
  fill(0);
  rect(105,270,45,7); // 왼쪽 눈썹
  rect(195,270,45,7); // 오른쪽 눈썹
  ellipse(107,293,15,15); // 왼쪽 눈
  ellipse(193,293,15,15); // 오른쪽 눈
  ellipse(150,320,17,17); // 코
  fill(255);
  ellipse(160,335,25,25); // 왼쪽 수염
  ellipse(140,335,25,25); // 오른쪽 수염 
  
}
```
설명 : void setup에서 화면의 크기를 300*800으로 지정하고, 사각형을 그려줄때 사각형의 중심을 기점으로 그려주도록 rectMode(CENTER)을 해줍니다.
void draw  에서는 카카오톡 라이언을 그리기 위하여 귀 와 얼굴 눈 코 수염 부분은 원을 그려야 하므로 ellipse 를 사용 해 주었고 눈썹은 사각형이므로 rect를 사용 해 주었습니다. 배경색은 background를 통해 검은색으로 하였습니다.
```
PImage bg;
int x, y;
void setup() {
  size(640, 360);
  bg = loadImage("moonwalk.jpg");
}
void draw() {
  background(bg);
  stroke(255, 255, 0);
  line(0, y, width, y);
  stroke(0, 0, 255);
  line(x, 0, x, height);
  y++;
  x++;
  if (y>height) {
    y=0;
    if (x>width) {
      x=0;
    }
  }
}
```
설명 : 먼저 processing 에서 이미지파일을 불러오기 위해 PImage를 통하여 변수 bg로 선언 해 줍니다. void setup에서 화면의 크기를  640*360으로 지정한 후 앞서 선언된 이미지 변수 bg에 loadImage를 통하여 moonwalk.jpg를 불러와 저장합니다. void draw 에서는 배경을 불러온 이미지로 지정 해줍니다. 그리고 길이가 화면의 폭과 같고 y값이 변수인 노란색의 선과 길이가 화면의 높이와 같고 x값이 변수인 파란색 선을 선언 해 줍니다. 마지막으로 if문을 통하여 각 두개의 변수값이 계속 커지면서 화면밖으로 나갈시 처음으로 돌아가도록 선언 해 줍니다.
