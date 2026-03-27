# Design-of-FIR-Filters-using-hanning-window

# AIM: 
To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 
PC Installed with SCILAB 

# PROGRAM
a. Design of Low Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;

for n = 1:M
    if (n == alpha+1) then
        hd(n) = Wc/%pi;
    else
        hd(n) = sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Hanning Window
for n = 1:M
    W(n) = 0.5 - 0.5*cos((2*%pi*(n-1))/(M-1));
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR LPF using Hanning Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR LPF using Hanning Window');
```
b. Design of High Pass FIR Digital filter
```
clc;
close;

M = input('Enter the Odd Filter Length = ');
Wc = input('Enter the Digital Cut off frequency = ');

alpha = (M-1)/2;
for n = 1:M
    if (n == alpha+1) then
        hd(n) = 1 - (Wc/%pi);
    else
        hd(n) = -sin(Wc*((n-1)-alpha))/(((n-1)-alpha)*%pi);
    end
end

// Hanning Window
for n = 1:M
    W(n) = 0.5 - 0.5*cos((2*%pi*(n-1))/(M-1));
end

h = hd .* W;

disp("Filter Coefficients:");
disp(h);

[hzm,fr] = frmag(h,256);

subplot(2,1,1)
plot(2*fr,hzm)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude');
title('Frequency Response of FIR HPF using Hanning Window');

hzm_dB = 20*log10(hzm);

subplot(2,1,2)
plot(2*fr,hzm_dB)
xlabel('Normalized Digital Frequency w');
ylabel('Magnitude in dB');
title('Frequency Response of FIR HPF using Hanning Window');
```
c. Design of Band Pass FIR Digital filter
```
clc ; 
close ;
 
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = ');

alpha= (M -1)/2 // Center Value 
for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =(Wc2-Wc1)/%pi ; 
    else 
        hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
    end 
end 

//Hanning Window 
for n = 1:M 
    W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 

//Windowing filter coefficients 
h = hd.*W; 

disp("Filter Coefficients:");
disp(h);

[hzm,fr]= frmag (h,256) ; 
subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BPF using Hanning Window ') 

hzm_dB = 20* log10 (hzm);
 
subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BPF using Hanning Window');
```
d. Design of Band Stop FIR Digital filter
```
clc ; 
close ; 
M=input('Enter the Odd Filter Length ='); 
Wc1 = input('Enter the Lower Cut off frequency = ');
Wc2 = input('Enter the Upper Cut off frequency = '); 
 
alpha= (M -1)/2 // Center Value 
for n = 1:M 
    if (n ==alpha+1) 
        hd(n) =1-((Wc2-Wc1)/%pi); 
    else 
        hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 
    end 
end 
//Hanning Window 

for n = 1:M 
    W(n) = 0.5-(0.5*cos((2*%pi*(n-1))/(M-1))); 
end 
//Windowing filter coefficients 

h = hd.*W;
 
disp("Filter Coefficients:");
disp(h);
 
[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 
plot(2*fr, hzm) 
xlabel( ' Normalized Digital Frequency w'); 
ylabel( 'Magnitude '); 
title( ' Frequency Response of FIR BSF using Hanning Window ') 

hzm_dB = 20* log10 (hzm); 

subplot (2 ,1 ,2); 
plot(2*fr , hzm_dB); 
xlabel( ' Normalized Digital Frequency W' ); 
ylabel( 'Magnitude in dB'); 
title('Frequency Response of FIR BSF using Hanning Window'); 
```

# OUTPUT
a. Design of Low Pass FIR Digital filter

<img width="2877" height="1798" alt="image" src="https://github.com/user-attachments/assets/3cfe85a0-0e71-4111-997a-b3e6d10f995b" />

b. Design of High Pass FIR Digital filter

<img width="2879" height="1799" alt="image" src="https://github.com/user-attachments/assets/adcc916a-f510-4d4d-b44b-5ecb04529f73" />

c. Design of Band Pass FIR Digital filter

<img width="2877" height="1792" alt="image" src="https://github.com/user-attachments/assets/d9ed10c2-62a2-402c-94a6-ffa1b65298f5" />

d. Design of Band Stop FIR Digital filter

<img width="2867" height="1784" alt="image" src="https://github.com/user-attachments/assets/8c2e7ac7-f0c4-4047-b22c-abdd86042a46" />

# RESULT
The FIR Filters were successfully designed using Hanning window Technique.
