# EXP 3 : IIR-BUTTERWORTH-FITER-DESIGN

## AIM: 

 To design an IIR Butterworth filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 
```
clc;
clear;

fs = 9000;
fc = 1000;
N  = 3; 

// Normalized cutoff frequency (0..1, where 1 = Nyquist)
frq = fc / (fs/2);

// Design digital Butterworth IIR low-pass filter
hz = iir(N, 'lp', 'butt', frq, []);

// Show the transfer function
disp("Transfer function (hz):");
disp(hz);

// Frequency response (magnitude)
[nMag, fr] = frmag(hz, 512);   // 512 points

// Convert normalized frequency to Hz
f_Hz = fr * fs;

// Plot Magnitude in dB
clf();
plot(f_Hz, 20*log10(abs(nMag) + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
xtitle("3rd Order Butterworth Low-Pass Filter");
xgrid();
```
## PROGRAM (HPF): 
```
clc;
clear;

fs = 9000;
fc = 1000;
N  = 3;

// Normalized cutoff frequency (0..1, where 1 = Nyquist)
frq = fc / (fs/2);

// Design digital Butterworth IIR high-pass filter
hz = iir(N, 'hp', 'butt', frq, []);

// Show the transfer function
disp("Transfer function (hz):");
disp(hz);

// Frequency response (magnitude)
[nMag, fr] = frmag(hz, 512);   // 512 points

// Convert normalized frequency to Hz
f_Hz = fr * fs;

// Plot Magnitude in dB
clf();
plot(f_Hz, 20*log10(abs(nMag) + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
xtitle("3rd Order Butterworth High-Pass Filter");
xgrid();
```

## OUTPUT (LPF) : 

<img width="765" height="625" alt="image" src="https://github.com/user-attachments/assets/36bcc244-68aa-4680-a3d4-938ab154812c" />


## OUTPUT (HPF) : 

<img width="765" height="593" alt="image" src="https://github.com/user-attachments/assets/fc5962a1-3216-4013-b4d5-96a86855bea7" />


## RESULT: 

The design of IIR Butterworth filter (LPF & HPF) using SCILAB was successfully executed.
