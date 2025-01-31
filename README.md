# PotatoAugmentation

## Overview
This script performs various data augmentation techniques. It applies transformations such as flipping, rotation, color adjustments such as brightness adjustment, contrast adjustment, hue shifts, channel shifts, and also Gaussian noise addition. The augmented images are saved in a separate directory.

## Features
- Horizontal and vertical flipping
- Rotation at specified angles
- Brightness and contrast adjustments
- Hue shifts in the HSV color space
- Channel shift transformations
- Addition of Gaussian noise
- Saves original (untouched) image along with augmented versions

## Directory Structure
The script expects the following directory structure with .jpg and .png images in each of the class folders:

```bash
./data/
    ├── name_of_directory/
        ├── train/
            ├── class_1/
            ├── class_2/
            ├── ...
        ├── test/
            ├── class_1/
            ├── class_2/
            ├── ...
```

The augmented images will be saved in:

```bash
./data/name_of_directory_augmented_all/
    ├── train/
        ├── class_1/
        ├── class_2/
        ├── ...
```

## Dependencies
Ensure you have the following dependencies installed:

```bash
pip install opencv-python numpy
```

The versions used were:

| Tool   | Version   |
|--------|-----------|
| Python | 3.11.5    |
| Numpy  | 1.24.3    |
| OpenCV | 4.10.0.84 |

## Usage
1. Place the dataset inside the `./data/` directory.
2. Modify the `dirname` variable in the script to match your dataset directory.
3. Run the script:

```bash
python augment.py
```

## Customization
- Modify `resize_dim` to change the target image size.
- Adjust `rotation_angles`, `brightness_factors`, `contrast_factors`, `hue_shift_factors`, and other augmentation parameters as needed.
- Enable or disable different augmentation techniques by changing the corresponding boolean flags or commenting out unwanted mechanisms.

## Output Example
For an input image `image1.jpg`, the script will generate multiple versions such as:

```bash
image1_flip_horizontal.JPG
image1_flip_vertical.JPG
image1_rotate_90.JPG
image1_brightness_0.75.JPG
image1_contrast_-0.25.JPG
image1_channel_shift.JPG
image1_hist_eq.JPG
image1_noise.JPG
image1_untouched.JPG
```

If all augmentation methods are enabled.

## Notes
- The script currently processes images in the `train/` directory only. To include the `test/` directory, uncomment the relevant lines in the script.
- The script checks for `.jpg` and `.png` file extensions.
- The brightness, contrast, and hue shifts are applied with predefined factors.

## License
This project is open-source and available under the MIT License.

