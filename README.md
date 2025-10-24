# Colour-Visual-Cryptography-Code
Official implementation of the Code for the paper "A Dynamic Multi-Share Visual Cryptography Scheme with Autoencoder-Based Image Enhancement in LAB Color Space."


# Dynamic Multi-Share Visual Cryptography Scheme

This repository contains the source code and trained weights for the novel Color Visual Cryptography (CVC) pipeline. Our method combines a lightweight Autoencoder for image enhancement, AES-256 encryption, and Shannon entropy-based dynamic share generation.

## 1. Project Goal (Addressing Novelty)

The primary goal is to demonstrate a hybrid CVC approach that maintains high visual fidelity and adaptive security.
* **Enhancement:** Uses a lightweight Autoencoder to denoise and refine features in the LAB color space.
* **Adaptivity:** Uses Shannon entropy to dynamically determine the optimal number of shares (n=3 to 5) per channel, balancing security and computational overhead.
* **Security:** Employs AES-256 encryption on refined color channels before secret sharing.

## 2. Repository Contents

| File/Folder | Description |
| :--- | :--- |
| `cvc_pipeline.py` | Contains the complete Python pipeline, including the `LABAutoencoder` class definition and all functions (encryption, sharing, reconstruction, decryption). |
| `lab_autoencoder.pth` | **Trained PyTorch Model Weights.** This binary file is essential for running the `AUTOENCODER_PROCESS`. |
| `requirements.txt` | List of all required Python libraries. |
| `test_image/` | Sample images (e.g., `peppers.jpg`, `baboon.jpg`) used for replication of metrics. |

## 3. Setup and Installation

1.  **Clone the Repository:**
    ```bash
    git clone [YOUR REPO URL]
    cd [YOUR REPO NAME]
    ```

2.  **Install Dependencies:** It is recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Place Weights:** Ensure the binary file `lab_autoencoder.pth` is in the repository's root directory.

## 4. How to Run the Pipeline

The main script will execute the full forward and backward CVC process on a sample image.

1.  Place your desired test image (e.g., `peppers.jpg`) into the repository folder.
2.  Open `cvc_pipeline.py` and set the `image_path` variable at the top of the main execution block.
3.  Execute the script:
    ```bash
    python cvc_pipeline.py
    ```

The script will output the share images, channel comparisons, and the final reconstructed image, replicating the results discussed in **Section V: Experimental Results** of the paper.
