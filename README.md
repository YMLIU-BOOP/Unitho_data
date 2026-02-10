# Unitho 2.0 Dataset (Open Subset)

Unitho 2.0 is a dataset designed for **multi-stage lithography modeling**, covering the complete  
**Layout - Mask - Contour - Source** pipeline under diverse process conditions at the **55 nm** node.

This repository currently releases an **open subset** of the full dataset for research and benchmarking.

## Key Characteristics

- **Process node:** 55 nm  
- **Pipeline stages:** Layout, Mask, Contour, Source  
- **Image format:** PNG, **512 × 512**, pixel-wise aligned across stages  
- **Physical field of view:** **6000 nm × 6000 nm** per image  
  - **Pixel size:** 6000 / 512 ≈ **11.71875 nm/pixel**
- **Process coverage:** **36** distinct process configurations (see below)  
  - All 36 configurations are included in the training and in-domain test sets of the full dataset.  
  - The released subset covers a portion of the full data.

## Process Parameters

Each sample is generated under one lithography process configuration defined by:

- **Source type:** `Annular`, `Circular`, `Bull's Eye`
- **Resist threshold:** `0.09231251`, `0.1236402`, `0.1436665`
- **Focus:** `0 nm`, `50 nm`
- **Exposure dose:** `1.0x`, `1.2x`

These factors form **3 × 3 × 2 × 2 = 36** configurations.

## Data Format

Each sample consists of a stage-aligned tuple:

> **(Layout, Mask, Contour, Source)**

All images are spatially aligned and stored as PNG files with consistent resolution **512 × 512**.

### Stage Description

- **Layout:** design pattern
- **Mask:** mask pattern corresponding to the layout under the given process setting
- **Contour:** printed/simulated wafer contour corresponding to the mask
- **Source:** illumination source representation (stored as an image)

## File Naming Convention

Files are named using the **process-condition name** .  



