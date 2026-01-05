# Music Source Seperation (MSS) Theory
<br>

While learning how to mix and master different instruments and making into a complete piece, I have always wondered how each sounds can be seperated.
<br>
<br>
> Its like reversing a cooked pizza back to the ingredient states...


Computer sees the song or vocal as a long stream of numbers representing air pressure moving your speaker cone in and out. It doesn't know what a "guitar" or "vocal" is.

<br>

## How do sound waves becomes a song?

First, we need to know how the sound waves harmonate with each other to make a song.

As different instruments have different frequencies and density, some parts get overlapped with each other.


<br>


## How to seperate noise?

Time-frequency representation

- audio signals are first converted into a **spectrogram**  using **Short-Time Fourier Transform**

<img width="617" height="443" alt="W" src="https://github.com/user-attachments/assets/bafa5e61-f802-4af6-b37a-7dfe729c6447" />

### How to read spectrogram?

- X axis (left to right) shows **time**
- Y axis (bottom to top) shows **pitch/frequency**
- colour / brightness shows **loudness**

<br>

### Vocals VS Instruments


![spectrogram-pic-1_orig](https://github.com/user-attachments/assets/6a83fe31-f998-493c-86a1-a7a386343a6e)

> This is piano note

![spectrogram-pic-2_orig](https://github.com/user-attachments/assets/9f68dc08-9e92-4f5b-8a2b-d6e764103173)

> This is vocal

This vocal line has vibrato, represented by the waves whereas piano has no vibrato.




<br>

### how seperating vocals using AI works (machine learning)

<br>

The core feature of AI is the **U-net**.

U - net was originally developed for medical image segmentation (for example, identifying tumors or organs in an MRI scan) 

<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/90f612b7-91ae-4431-a713-3e7f40fe2c6a" />


<br>

researchers realised that separating instruments from a spectogram is mathematically identical to segmenting organs from a medical scan.

<br>

The vocals are simply the target object which the AI needs to segment out of the complex "background image" of the rest of the music.


<br>

#### U - net structure

##### Encoder (the analyser)

**Main job**

<br>

1. **Downsampling** (compression) - takes the original spectogram and progressively shrinks it through layers of convolutions.


<br>

2. **Feature Extraction** - as it shrinks the "image"

<br>

##### Decoder (the reconstructor)

> It abstract knowledge from the encoder to build the final, separated output.

<br>

**Main job**

1. **Upsampling** (decompression) - takes the compressed summary and progressively expands it back to the original size of the spectogram.

<br>

2. **Skip Connections** - the decoder takes input not only from the compressed bottleneck but also directly from the corresponding layers of the encoder. This ensures that the final output mask retains details like 's' and 't' sounds of a voice or the sharp attack of a guitar pick that were lost during the initial compression.

   

Sources:

Google Gemini 3 pro model

https://www.joshualindsay.com/blog/resonance-in-singing-with-spectrogram-analysis

images:

https://media.geeksforgeeks.org/wp-content/uploads/20251007111045128990/u_net.webp





