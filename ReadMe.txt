# Understanding DCT vs DWT

This program demonstrates the comparison between Discrete Cosine Transform (DCT) and Discrete Wavelet Transform (DWT) for image compression and progressive decoding. The implementation reads an RGB image file of size **512x512** as input, applies DCT and DWT independently on each channel, and displays the reconstructed images side by side for analysis.

## Features
1. **DCT and DWT Encoding/Decoding**:
   - The program converts the image into frequency domain representations using DCT and DWT.
   - Depending on the input parameter, it reconstructs the image using only a subset of coefficients.
2. **Progressive Decoding (n = -1)**:
   - Animates the progressive reconstruction for both DCT and DWT with **64 iterations for DCT** and **10 iterations for DWT**.
3. **Quality Comparison (n = -2)**:
   - Implements progressive decoding for both transforms with **64 iterations**, ensuring equivalent coefficient usage for fair visual comparison.

## Usage
Compile and run the program from the command line as follows:

```bash
# Compile the code
javac ImageDisplay.java

# Run the program
java ImageDisplay <path to RGB file> <n>