# Design-of-FIR-Filters-using-hanning-window

#DESIGN OF FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of low pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 
```
clear;
close;

M = 51;             
fc = 0.4;            

n = 0:M-1;
w = 0.5 - 0.5 * cos(2 * %pi * n / (M-1));

hd = sin(2 * %pi * fc * (n - (M-1)/2)) ./ (n - (M-1)/2);
hd((M-1)/2 + 1) = 2 * %pi * fc;  

h = hd .* w;
h = h / sum(h);
disp(h);

subplot(2,1,1);
plot(h);
xlabel('Samples');
ylabel('Amplitude');
title('Impulse Response of Low Pass FIR Filter using Hanning Window');

[H, f] = frmag(h, 512);
subplot(2,1,2);
plot(f, H);
xlabel('Normalized Frequency');
ylabel('Magnitude');
title('Frequency Response of Low Pass FIR Filter');
```

# OUTPUT

<img width="1223" height="707" alt="image" src="https://github.com/user-attachments/assets/3154d48d-6dcd-408a-8b91-59be0043a6e4" />

# RESULT

Thus, a Low Pass FIR Digital Filter was successfully designed using the Hanning window method in SCILAB.
