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
  Premierement on va charger le fichier  dans MATLAB à l’aide de la commande « audioread » puis on va Tracer le signal enregistré en fonction du temps :
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
 ![image](https://user-images.githubusercontent.com/93142901/151711655-4a929dfb-ff8f-4381-86f1-9167f005b524.png)
-On remarque que la modification de la fréquence d’échantillonnage revient à appliquer 
un changement d’échelle y(t) = x(at) en fonction de la valeur du facteur d’échelle, cela 
revient à opérer une compression ou une dilatation du spectre initial d’où la version 
plus grave ou plus aigüe du signal écouté.
