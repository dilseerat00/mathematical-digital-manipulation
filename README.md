# mathematical-digital-manipulation

This project demonstrates basic image processing techniques in C using matrix operations. The operations include:

- **Grayscale Conversion**: Convert an image to black and white.
- **Blurring**: Apply a simple blur filter.
- **Rotation**: Rotate the image by 90 degrees clockwise.

The image format used in this example is PPM (Portable Pixmap), which simplifies reading and writing pixel data.

## Features

### Grayscale Conversion
Converts an image to black and white by averaging the RGB values of each pixel.

### Blurring
Applies a box blur filter to the image. Each pixel's color is averaged with its neighbors in a kernel of a specified size.

### Rotation
Rotates the image by 90 degrees clockwise. This involves mapping the pixels from the original image to their new positions in the rotated image.

## Prerequisites

- GCC (GNU Compiler Collection)
- Basic understanding of image processing concepts(matrices are applied)
- PPM image files (P3 format)

## How to Use

1. **Prepare Your Image**: Ensure your input image is in PPM P3 format and named `input.ppm`.

2. **Run the Program**: Execute the compiled program. This will process the image and generate output files.

3. **Check Output Files**: The following output files will be created:
    - `output_grayscale.ppm`: The image converted to black and white.
    - `output_blur.ppm`: The image with a blur effect applied.
    - `output_rotated.ppm`: The image rotated 90 degrees clockwise.

## Code Overview

### Reading and Writing PPM Files
Functions to read and write PPM files are provided to handle pixel data.

### Grayscale Conversion
The `convertToGrayscale` function converts each pixel to grayscale by averaging the RGB values.

### Blurring
The `applyBlur` function applies a box blur by averaging pixel values within a kernel.

### Rotation
The `rotateImage` function rotates the image 90 degrees clockwise by mapping pixel positions accordingly.

## Example Code

Here is a snippet of the image rotation function:

```c
void rotateImage(Pixel image[HEIGHT][WIDTH], Pixel rotated[WIDTH][HEIGHT]) {
    for (int y = 0; y < HEIGHT; y++) {
        for (int x = 0; x < WIDTH; x++) {
            rotated[x][HEIGHT - 1 - y] = image[y][x];
        }
    }
}
