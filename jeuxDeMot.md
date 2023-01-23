# Tp2-jeux-de-mot
%% Jeux de mots
%Question 1:

[y,fs]=audioread("C:\Users\Dell\Desktop\TS\MyAudio.m4a");

%Question 2:

%sound(y,fs)
%plot(y)

%Question 3:

%sound(y,fs*2)
%sound(y,fs/2)
%sound(y,fs)

%Question 4:

stem(y)
%Après le traçage de la fonction y on peut arriver a voir que le morceau
%Rien ne sert de est contenue dans la partie de l'index 1025 j'usqu'à 2.05e05

%Question 5:

phrase1=y(1025:(2.05e05));
%stem(phrase1)
%sound(phrase1,fs)

%Question 6:

phrase2=y((2.239e+05):(2.642e+05));
%sound(phrase2,fs)

phrase3=y((2.987e+05):(3.81e+05));
%sound(phrase3,fs)

phrase4=y((4e+05):(5.28e+05));
%sound(phrase4,fs)

%Question 7:
phrase5=[phrase1 ,phrase4 ,phrase3,phrase2];
%sound(phrase5,fs)

%% Synthèse et analyse spectrale d’une gamme de musique

%Synthèse d’une gamme de musique

%Question 1:

fs=8192;
ts=1/fs;
N=5000;
t=(0:N-1)ts;
note1=10cos(2pi262t);
%sound(note1,fs)
note2=10cos(2pi294t);
%sound(note2,fs)
note3=10cos(2pi330t);
%sound(note3,fs)
note4=10cos(2pi349t);
%sound(note4,fs)
note5=10cos(2pi392t);
%sound(note5,fs)
note6=10cos(2pi440t);
%sound(note6,fs)
note7=10cos(2pi494t);
%sound(note7,fs)
note8=10cos(2pi523*t);
%sound(note8,fs)
scale=[note1,note2,note3,note4,note5,note6,note7,note8];
sound(scale,fs)

%Spectre de la gamme de musique

%Question 2:

f=(0:N-1)*(fs/N);
spectrum_scale=fft(scale);
signalAnalyzer(abs(fftshift(spectrum_scale)));
