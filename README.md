# FIR-FILTER-DESIGN
# EXP 4 A: Design-of-FIR-Digital-Filter-using-Rectangular-Window

# AIM 1:  To perform Design-of-LOWPASS FIR-Digital-Filter-using-Rectangular-Window using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 

clc;

close;


M = input('Enter the Odd Filter Length = ');

Wc = input('Enter the Digital Cut off frequency = ');


alpha = (M - 1) / 2; // Center Value


for n = 1:M

    if (n == alpha + 1)
    
        hd(n) = Wc / %pi;
        
    else
    
        hd(n) = sin(Wc * ((n - 1) - alpha)) / (((n - 1) - alpha) * %pi);
        
    end    
end


// Rectangular Window
for n = 1:M

    W(n) = 1;
    
end


// Windowing filter coefficients

h = hd .* W;


disp(h, 'Filter Coefficients are');


[hzm, fr] = frmag(h, 256);


// Magnitude Response

subplot(2, 1, 1);

plot(2 * fr, hzm);

xlabel('Normalized Digital Frequency w');

ylabel('Magnitude');

title('Frequency Response of FIR LPF using Rectangular Window');


// Magnitude Response in dB

hzm_dB = 20 * log10(hzm);


subplot(2, 1, 2);

plot(2 * fr, hzm_dB);

xlabel('Normalized Digital Frequency W');

ylabel('Magnitude in dB');

title('Frequency Response of FIR LPF using Rectangular Window');


# OUTPUT: 
<img width="853" height="783" alt="image" src="https://github.com/user-attachments/assets/b9fdd33e-6c82-4f40-9798-613c3babcd59" />
<img width="612" height="707" alt="image" src="https://github.com/user-attachments/assets/542fbd51-8a97-4a02-8fdf-905f79b6b304" />


# RESULT: 

Thus design of low pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 2: To perform DESIGN OF HIGH PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ; 

close ; 

M=input('Enter the Odd Filter Length ='); 

Wc=input('Enter the Digital Cut off frequency ='); 

alpha= (M -1)/2 // Center Value 

for n = 1:M 

if (n ==alpha+1) 

hd(n)=1-Wc/ %pi ; 

else 

hd(n) =-sin(Wc *((n -1)-alpha)) /(((n -1)-alpha)*%pi); 

end 

end 

// Rectangular Window 

for n = 1:M 

W(n) =1; 

end 

//Windowing filter coefficients 

h = hd.*W; 

disp(h,'Filter Coefficients are') 

[hzm,fr]= frmag (h,256) ;

subplot(2 ,1 ,1) 

plot(2*fr, hzm) 

xlabel( ' Normalized Digital Frequency w'); 

ylabel( 'Magnitude '); 

title( ' Frequency Response of  FIR LPF using Rectangular Window ') 

hzm_dB = 20* log10 (hzm);

subplot (2 ,1 ,2); 

plot(2*fr , hzm_dB); 

xlabel( ' Normalized Digital Frequency W' ); 

ylabel( 'Magnitude in dB'); 

title('Frequency Response of FIR HPF using Rectangular Window');


# OUTPUT: 
<img width="950" height="795" alt="image" src="https://github.com/user-attachments/assets/b5099184-b385-485e-97e5-dab92a60d42b" />
<img width="598" height="753" alt="image" src="https://github.com/user-attachments/assets/17d62810-63b2-4c5e-8fa7-8804c3f560d0" />


# RESULT: 
Thus design of HIGH pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 3: To perform DESIGN OF BAND PASS FIR DIGITAL FILTERS using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ; 

close ; 

M=input('Enter the Odd Filter Length ='); 

Wc=input('Enter the Digital Cut off frequency ='); 

Wc2=Wc(2); 

Wc1=Wc(1); 

alpha= (M -1)/2 // Center Value 

for n = 1:M 

if (n ==alpha+1) 

hd(n) =(Wc2-Wc1)/%pi ; 

else 

hd(n) =((sin(Wc2 *((n -1)-alpha)))-(sin(Wc1 *((n -1)-alpha))))/(((n -1)-alpha)*%pi);

end 

end 

// Rectangular Window 

for n = 1:M 

W(n) =1; 

end 

//Windowing filter coefficients 

h = hd.*W; 

disp(h,'Filter Coefficients are') 

[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 

plot(2*fr, hzm) 

xlabel( ' Normalized Digital Frequency w'); 

ylabel( 'Magnitude '); 

title( ' Frequency Response of FIR BPF using Rectangular Window ')

hzm_dB = 20* log10 (hzm); 

subplot (2 ,1 ,2); 

plot(2*fr , hzm_dB); 

xlabel( ' Normalized Digital Frequency W' ); 

ylabel( 'Magnitude in dB'); 

title('Frequency Response of FIR BPF using Rectangular Window');


# OUTPUT: 
<img width="898" height="806" alt="image" src="https://github.com/user-attachments/assets/838b23af-9a06-4768-8abc-ac6ce76b051e" />
<img width="688" height="842" alt="image" src="https://github.com/user-attachments/assets/4d213fda-e6a6-441a-92d8-94a70d822350" />


# RESULT: 
Thus design of BAND pass FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.

# AIM 4: To perform DESIGN OF BAND STOP FIR DIGITAL FILTER using SCILAB.

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
clc ; 

close ; 

M=input('Enter the Odd Filter Length =');

Wc=input('Enter the Digital Cut off frequency ='); 

Wc2=Wc(2); 

Wc1=Wc(1); 

alpha= (M -1)/2 // Center Value 

for n = 1:M 

if (n ==alpha+1) 

hd(n) =1-((Wc2-Wc1)/%pi) ; 

else 

hd(n) =((sin(Wc1 *((n -1)-alpha)))-(sin(Wc2 *((n -1)-alpha))))/(((n -1)-alpha)*%pi); 

end 

end 

// Rectangular Window 

for n = 1:M 

W(n) =1; 

end 

//Windowing filter coefficients

h = hd.*W; 

disp(h,'Filter Coefficients are') 

[hzm,fr]= frmag (h,256) ; 

subplot(2 ,1 ,1) 

plot(2*fr, hzm) 

xlabel( ' Normalized Digital Frequency w'); 

ylabel( 'Magnitude '); 

title( ' Frequency Response of  FIR BSF using Rectangular Window ') 

hzm_dB = 20* log10 (hzm); 

subplot (2 ,1 ,2); 

plot(2*fr , hzm_dB); 

xlabel( ' Normalized Digital Frequency W' ); 

ylabel( 'Magnitude in dB'); 

title('Frequency Response of FIR BSF using Rectangular Window');


# OUTPUT: 
<img width="888" height="805" alt="image" src="https://github.com/user-attachments/assets/5261a176-8e06-4fdc-a845-87accbcd409f" />
<img width="637" height="885" alt="image" src="https://github.com/user-attachments/assets/c8470c29-d24a-4ecc-9baa-02c1f92f14f0" />


# RESULT: 
Thus design of BAND STOP FIR digital filter using-Rectangular-Window waveforms were plotted and output was verified.
