# UNet for Polyp Segmentation in Colonoscopy Images

A deep learning project implementing UNet architecture for automated polyp segmentation in colonoscopy images using the Kvasir-SEG dataset.

## Problem Statement

Colorectal cancer is the 3rd most common cancer worldwide. During colonoscopy procedures, 14-30% of polyps are missed by physicians. This project aims to build an automated polyp segmentation system to assist doctors in identifying polyp boundaries accurately.

## Dataset

**Kvasir-SEG Dataset**
- 1,000 polyp images from colonoscopy procedures
- Pixel-wise segmentation masks provided
- Source: [Simula Research Laboratory](https://datasets.simula.no/kvasir-seg/)

## Architecture

**UNet** - Encoder-Decoder with Skip Connections

Key components:
- **Encoder**: Captures context through convolutions and pooling
- **Bottleneck**: Bridge between encoder and decoder
- **Decoder**: Enables precise localization through upsampling
- **Skip Connections**: Preserve spatial information from encoder to decoder

## Experiments

| Experiment | Description |
|------------|-------------|
| Exp 1 | Shallow UNet (depth=2) vs Standard UNet (depth=4) |
| Exp 2 | UNet WITH vs WITHOUT skip connections |
| Exp 3 | Loss function comparison: BCE vs Dice vs Combined |

## Evaluation Metrics

- **Dice Coefficient**: Primary metric measuring overlap between prediction and ground truth
- **IoU (Intersection over Union)**: Jaccard index for segmentation quality
- **Precision & Recall**: Additional classification metrics

## Installation

```bash
# Clone the repository
git clone [https://github.com/YOUR_USERNAME/polyp-segmentation-unet.git](https://github.com/Priti0427/polyp-segmentation-unet)
cd polyp-segmentation-unet

# Install dependencies
pip install -r requirements.txt
```

## Usage

### Run in Google Colab (Recommended)

1. Upload `UNet_Polyp_Segmentation.ipynb` to Google Colab
2. Enable GPU: Runtime → Change runtime type → GPU
3. Run all cells

### Run Locally

```bash
jupyter notebook UNet_Polyp_Segmentation.ipynb
```

## Project Structure

```
polyp-segmentation-unet/
├── UNet_Polyp_Segmentation.ipynb   
├── UNet_Polyp_Segmentation_Proposal.pptx  
├── requirements.txt                
├── README.md                        
└── .gitignore                       
```

## Results

Final test set evaluation for the **Standard UNet with Skip Connections** from `UNet_Polyp_Segmentation_Final.ipynb`:

| Metric | Value |
|--------|-------|
| Loss | 0.1749 |
| Dice | 0.8412 |
| IoU | 0.7315 |
| Precision | 0.8893 |
| Recall | 0.8091 |

These values are taken from the final test set evaluation in `UNet_Polyp_Segmentation_Final.ipynb`.



## References
1. Ronneberger, O., Fischer, P., & Brox, T. (2015). U-Net: Convolutional Networks for Biomedical Image Segmentation. MICCAI.
2. Jha, D., et al. (2020). Kvasir-SEG: A Segmented Polyp Dataset. MMM 2020.
3. Fan, D.P., et al. (2020). PraNet: Parallel Reverse Attention Network for Polyp Segmentation. MICCAI 2020.

## License
This project is for educational purposes as part of a Deep Learning course at Drexel University.

