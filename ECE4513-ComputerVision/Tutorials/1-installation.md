# Tutorial 1

## Python installation

skip!

## Package installation

packages needed:

- opencv-python
- numpy
- matplotlib

imports needed:

```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

## Image I/O in Python

```py
import cv2
import matplotlib.pyplot as plt

# Read an image
img = cv2.imread('image.jpg')

# If we want to display it using plt,
# we need to convert BGR to RGB
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.subplot(1,2,1)
plt.imshow(img_rgb)

# Use plt to display a gray image
plt.subplot(1,2,2)
plt.imshow(img_rgb, cmap='gray')

plt.show()
```

## Interpolation（插值）

### What is interpolation?

Estimating pixel values during resizing or transformation.

For example:

If we want to make a small image larger, then we need the computer to estimate what those extra pixels should be

### Different ways of interpolation:

| Interpolation    | Definition                            |
| ---------------- | ------------------------------------- |
| Nearest Neighbor | copy nearest pixel value              |
| Bilinear         | weighted average of 4 nearest neibor  |
| Bicubic          | weighted average of 16 nearest neibor |

### How to interpolation?

Example: make an image larger

```py
# make a image very small
img = cv2.resize(img, None, fx=0.08, fy=0.08, interpolation=cv2.INTER_LENEAR)

# Use different methods to scale it up
resized_nn = cv2.resize(img, None, fx=2, fy=2, interpolation=cv2.INTER_NEAREST)
resized_linear = cv2.resize(img, None, fx=2, fy=2, interpolation=cv2.INTER_LINEAR)
resized_cubic = cv2.resize(img, None, fx=2, fy=2, interpolation=cv2.INTER_CUBIC)

```
