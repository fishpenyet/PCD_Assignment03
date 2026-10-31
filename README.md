# PCD Assignment 03 — Segmentation & Morphological Processing

**Name:** Naila Syakira  
**NIM:** 25/555286/PA/23270

This repository contains Digital Image Processing Assignment 03, focused on **image segmentation** and **morphological operations**. The goal is to isolate a target object from its background and demonstrate how morphological operations can clean up segmentation artifacts. The methods implemented are listed below.

## Methods Used

### Segmentation & Morphological Techniques
- **Region Growing** — Stack-based flood-fill segmentation using intensity thresholding from a seed pixel
- **Binary Dilation** — 3×3 structuring element to expand foreground regions
- **Binary Erosion** — 3×3 structuring element to shrink foreground regions
- **Repeated Morphological Closing** — Multi-pass dilation followed by multi-pass erosion to bridge large gaps (simulating a larger structuring element)

## Files
- `PCD_Assignment03.ipynb` — implementation and experiments
- `PCD_Assignment03_ReportAnalysis.pdf` — analysis report

## Notes
The experiment uses a single grayscale image of a textured silver coin as the reference. A region growing algorithm is implemented from scratch using an explicit stack and a 4-connectivity neighborhood. It successfully identifies the overall circular boundary of the coin but leaves behind internal gaps caused by the coin's embossed details. To fix this, binary dilation and erosion are implemented from scratch and combined into a repeated closing operation. Parameters such as the seed coordinate `(332, 332)`, the intensity threshold `T = 37`, and the repetition count `N = 21` were tuned empirically to balance gap-filling against the loss of boundary precision.
