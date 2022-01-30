# TP2-Traitement-du-signal
# Rapport : TP2- Jeux de mots Synthèse et analyse spectrale d’une gamme de musique

## réalisé par Wafae Hamdaoui et Oumayma EL Bakkali

## Objectifs du TP:
 Comprendre comment manipuler un signal audio avec Matlab, en effectuant 
certaines opérations classiques sur un fichier audio d’une phrase enregistrée via 
un smartphone.<br/>

 Comprendre la notion des sons purs à travers la synthèse et l’analyse spectrale 
d’une gamme de musique.<br/>
# Jeux de mots
-------------------------------------------------------------------
« phrase.wave » est un fichier audio enregistré à l’aide d’un smartphone, en 
prononçant lentement la phrase : 
         - « Rien ne sert de courir, il faut partir à point ».
  1-Premierement on va charger le fichier  dans MATLAB à l’aide de la commande « audioread » puis on va Tracer le signal enregistré en fonction du temps :
 ```Matlab
   clear all;
   close all;
   clc;
   File = 'phrase.wav';
   % lit les données du fichier nommé filename et renvoie des données échantillonnées,x, et le fréquence dléchantillonnage pour ces données, Fs.
   [x,fs] = audioread(File);
   N=length(x);
   y=x(1:N/2);
   sound(y,fs);
   plot(x);
 ```
 ### Output :
![image](https://user-images.githubusercontent.com/93142901/151712108-29a3e6a3-e190-412f-ab6d-8c683304daec.png)<br/>
-On remarque que la modification de la fréquence d’échantillonnage revient à appliquer 
un changement d’échelle y(t) = x(at) en fonction de la valeur du facteur d’échelle, cela 
revient à opérer une compression ou une dilatation du spectre initial d’où la version 
plus grave ou plus aigüe du signal écouté.</br>
![image](https://user-images.githubusercontent.com/93142901/151712601-c72497f0-5e3d-4a22-b4e1-c0978b9264b7.png)<br/>
2-A partir du signal on peut extraire les indices de début et de fin de chaque mot,et donc on peut aussi les segementer et  Réarranger la phrase:
```Matlab
  % segmenter la phrase rien ne sert de
  riennesertde=x(1:74272);
  %segmenter le mot courir 
  courir=x(80117:93762);
  %segmenter la phrase il faut
  faut=x(101596:124998);
  %segmenter la phrase  partir a point
  partir=x(124604:N);
  % Creer un veecteur phrase2 et Réarranger les mot  pour écouter la phrase 
    synthétisée « Rien ne sert de partir à point, il faut courir ».
  phrase2=[riennesertde  partir   faut  courir];
  sound(phrase2,fs)
```
# Synthèse et analyse spectrale d’une gamme de musique
-------------------------------------------------------------------
```Matlab
 clear all
close all
clc
%declarons La fréquence de chaque note
fe= 8192 ;
fla=440;
fdol=262;
fre=294;
fmi=330;
ffa=349;
fsol=392;
fsi=494;
fdo2=523;
te=1/fe;
t=[0:te:1];
%chaque note peut être considérée comme étant un son pur produit par un signal sinusoïdal
la=sin(2*pi*fla*t);
dol=sin(2*pi*fdol*t);
re=sin(2*pi*fre*t);
mi=sin(2*pi*fmi*t);
fa=sin(2*pi*ffa*t);
sol=sin(2*pi*fsol*t);
si=sin(2*pi*fsi*t);
do2=sin(2*pi*fdo2*t);

son=[dol re mi fa sol la si do2];
sound(son,fe);
```
Utiliser l’outil graphique d’analyse de signaux signalAnalyzer pour visualiser le spectre de notre gamme:<br/>
![image](https://user-images.githubusercontent.com/93142901/151715942-56018b20-5628-4755-88b1-128ed5897b02.png)</br>
on peut Observer les 8 fréquences contenues dans la gamme et on peut aussi 
vérifier leur valeur numérique à l’aide des curseurs.</br>
Tracer le spectrogramme qui permet de visualiser le contenu fréquentiel du signal 
au cours du temps (comme le fait une partition de musique) mais la précision sur l’axe 
des fréquences n’est pas suffisante pour relever précisément les 8 fréquences.
![image](https://user-images.githubusercontent.com/93142901/151715878-6e1379fa-6b82-4555-a826-837e8298916a.png)</br>





