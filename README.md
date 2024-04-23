# Brain Tumor Segmentation using U-Net and Attention U-Net
 Brain Tumor Segmentation using U-Net and Attention U-Net


## Overview

This project utilizes deep learning models, specifically U-Net and Attention U-Net architectures, to segment brain tumors from MRI scans. The models are trained and evaluated using the BraTS2020 dataset, which consists of multi-modal MRI scans. The project is implemented in Python using PyTorch, a popular deep learning library.

## Project Structure

- **Data Handling**: MRI scan data is managed using the `BrainScanDataset` class, which loads and preprocesses data from .h5 files.
- **Model Architecture**: The project includes implementations of the U-Net and Attention U-Net models for segmentation tasks.
- **Training and Evaluation**: Models are trained using custom training loops, and performance is evaluated on a validation set.
- **Visualization**: Functions are provided to display MRI channels, segmentation masks, and overlay masks on MRI images.

## Installation

Before running the project, ensure that the following prerequisites are installed:

- Python 3.8 or later
- PyTorch 1.7 or later
- NumPy
- Matplotlib
- h5py

You can install the necessary libraries using pip:

```bash
pip install torch numpy matplotlib h5py
```

## Usage

### Data Preparation

Place your .h5 files containing the MRI scans and masks in a directory. The data should be structured as follows:

- Each .h5 file contains:
  - An 'image' dataset with dimensions (Height, Width, Channels).
  - A 'mask' dataset with dimensions (Height, Width, Channels).

### Configuring the Dataset

Modify the `directory` variable in the script to point to your data directory:

```python
directory = "/path/to/your/data"
```

### Running the Models

To train and evaluate the models, run the main script:

```bash
python brain_tumor_segmentation.py
```

### Visualizing Results

After training, you can visualize the MRI scans, masks, and model predictions using the provided visualization functions:

- `display_image_channels(image)`: Displays the different MRI channels.
- `display_mask_channels_as_rgb(mask)`: Displays the mask channels in RGB format.
- `overlay_masks_on_image(image, mask)`: Overlays the segmentation masks on the MRI images.

## Customizing the Models

You can adjust the model parameters and training settings in the `UNet` class and the training loop. Parameters such as the number of filters, number of epochs, and learning rate can be modified to optimize performance.

## Saving and Loading Models

To save a trained model:

```python
save_model(model, 'path/to/save/model.pth')
```

To load a trained model:

```python
model.load_state_dict(torch.load('path/to/save/model.pth'))
```
