# pacman-con-mov


//declaro mis variables con sus nombres 

int posicionenX=20;
float posicionenY=450;
float Inferior=PI/4;
float Superior=7*PI/4;
int cambioInferior=0;
int cambioSuperior=1;
// las fracciones de pi representan angulos dentro de la circunferencia 
//esto solo sucede una vez 
void setup(){
//Tamaño y del Canvas
size(700,700);
}
//lo que yo ponga aqui va a aparecer varias veces
void draw(){
//Fondo 
background(155);

//dibujo
noStroke();
fill(200,0,2);
//usamos un arco para lograr dibujar el personaje 

arc(posicionenX,posicionenY,70,70,Inferior,Superior); 

//condicionales para lograr el movimiento de la boca

if(Superior<7*PI/4){
  cambioSuperior=1;
}
if(Superior>2*PI){
  cambioSuperior=0;
}
if(cambioSuperior==0){
 Superior-=0.05;
}
if(cambioSuperior==1){
 Superior+=0.05;
}
//cambios de la parte de abajo del dibujo 

if(Inferior<0){
  cambioInferior=1;
}
if(Inferior>PI/4){
  cambioInferior=0;
}
if(cambioInferior==0){
  Inferior-=0.05;
}
if(cambioInferior==1){
  Inferior+=0.05;
}

//dibujo del ojo 

fill(0); 
ellipse(posicionenX+10,posicionenY-20,6,6);

posicionenX++;

//cambios en la posicion de y del dibujo completo al ser mayor que 480 su pos en y

if(posicionenX>480){
posicionenX=15;
posicionenY=random(40,460);
}
//cierro corchetes 
}
