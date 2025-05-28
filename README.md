
# DCT vs DWT Image Compression – CS576 Assignment 3

This project compares image compression techniques using **Discrete Cosine Transform (DCT)** and **Discrete Wavelet Transform (DWT)**. It processes a 512x512 RGB image and demonstrates how compression affects image quality by progressively using fewer coefficients.

## 🛠️ Implementation Details

- **Programming Language:** Java (no external libraries)
- **Compression Methods:**
  - **DCT (8x8 blocks):** Follows JPEG compression approach. Converts each block to frequency space and keeps only the first m coefficients (in zig-zag order) during decoding.
  - **DWT (Recursive decomposition):** Follows JPEG2000 compression. Uses wavelet transform on the entire image and retains a square of n coefficients in the lower-left corner during decoding.
- **Input Parameters:**
  - **First:** Image path (512x512 RGB, 24 bits per pixel).
  - **Second:** Number of coefficients `n` used during decoding. Special values:
    - `n = 262144`: Full reconstruction (no compression).
    - `n = -1`: Progressive decoding comparison with 64 iterations for DCT and 10 for DWT.
    - `n = -2`: Progressive decoding with 64 equal iterations for DCT and DWT.
- **Output:** Displays two images side by side – one decoded using DCT and the other using DWT.

## 📖 Usage
```bash
# Compile
javac *.java

# Run with full reconstruction
java ImageDisplay input.rgb 262144

# Run with reduced coefficients (e.g., 16384 coefficients)
java ImageDisplay input.rgb 16384

# Progressive decoding comparison (Part A)
java ImageDisplay input.rgb -1

# Progressive decoding with equal iterations (Part B)
java ImageDisplay input.rgb -2
```

## 📚 Key Concepts
- **DCT (Discrete Cosine Transform):** Efficient for block-based compression. Retains energy in low-frequency coefficients.
- **DWT (Discrete Wavelet Transform):** Provides multiresolution analysis. Works on the entire image and retains different regions for reconstruction.
- **Progressive Decoding:** Compares reconstruction quality as more coefficients are used in both DCT and DWT.
