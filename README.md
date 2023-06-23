# 16-Bit-BinaryDivider
16 Bit Binary Divider Using Restoring Division Algorithm For Unsigned Numbers

Table of contents
=================

<!--ts-->
   * [INTRODUCTION](https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider#introduction)
   * [ALGORITHM](https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider#algorithmn)
   * [RESULTS](https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider#results)
     * [WAVEFORMS](https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider#waveforms)
<!--te-->

<br>

## INTRODUCTION

The restoring division algorithm is a widely used method for performing binary division. It follows a simple iterative approach, repeatedly subtracting the divisor from the dividend and shifting both the dividend and quotient registers until the division is complete. The algorithm starts by aligning the binary numbers by appending zeros to the left of the dividend, ensuring they have the same number of bits. Then, it compares the current dividend with the divisor, subtracting if possible and setting the corresponding bit in the quotient register. After each subtract operation, the registers are shifted left. This process continues until all the bits in the dividend have been processed. The result is a quotient stored in the quotient register and a remainder in the dividend register. The restoring division algorithm serves as a fundamental technique in binary division.

<br>

## ALGORITHMN

<br>

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/fbcad88d-a525-421e-8868-9921611a9b66">
</p>
<br>


<br>


### STEPS
1.	Load the 16/8 bit Divisor And Dividend Value into the system 
<br>
2.	The system takes these value at positive edge of input ‘Ready’ , Which is provided by the user .
<br>
3.	Clear all the previous results (if any).
<br>
4.	Save the divisor value in a intermediate register.
<br>
5.	Compute 2’s compliment of the divisor 
<br>
6.	Initialize Count value as 16(5’d16) .
<br>
7.	Extend the 16 bit Dividend as 32 bit by filling in zeros (barrel extend).
<br>
8.	At Launch positive indicating the necessary initial conditions have been met
<br>
9.	Left shift the 32 bit extended dividend by one bit.
<br>
10.	Save the first 16 MSB bits in a intermediate register 
<br>
11.	Add 2’s compliment of the divisor to first 16 MSB bits
<br>
12.	If the MSB bit of the system is 1,then LSB is same zero and first 16 bits is replaced by the saved 16 bits (mentioned in step 10).
<br>
13.	If the MSB is zero then the LSB is made 1
<br>
14.	Decrement count value and repeat from step 10 if count value is not zero.
<br>
15.	After Count is zero ,the system indicates through the intermediate ‘Done’ Signal
<br>
16.	 The Lower 16 bits are Quotient and upper 16 bits are remainder,Which are provided by Inter_rem and Inter_Ouot.
<br>
17.	To provided different values to the system ,Make Input ‘Ready’ as zero and repeat from step 1.
<br>

# RESULTS

Output waveform obtained in the transcript window as follows : <br>

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/bb0b6776-0cd4-4688-a0a2-61250eb6b834">
</p>
<br>



As per the test cases provided in the test bench we can look into the transcript window and the waveform obtained and verify the division implementation
<br>

<p align="center">
  
  <img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/e5e1e648-59aa-456f-9481-beb82176e647">
</p>
<br>



## WAVEFORMS


<table>
  <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/1e148692-9d30-45ed-9572-e96c5bad28aa" width=550 height=300></td>
    <td><img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/7fa06b7c-e87c-467d-ab5c-6d79b4492168" width=550 height=300></td>
     
  </tr>
  <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/d8673306-bcca-4bde-971a-1c2fbfd7ce2b" width=550 height=300></td>
    <td><img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/10e94a77-818a-4c54-b06a-39ed91a3d0cb" width=550 height=300></td>
    
  
 </tr>
 <tr>
     <td><img src="https://github.com/Chetan-G-Gokhale/16-Bit-BinaryDivider/assets/126239004/fbe11979-5aad-4260-a23b-efc167fc3039" width=550 height=300></td>
    
    
  
 </tr>
</table>


