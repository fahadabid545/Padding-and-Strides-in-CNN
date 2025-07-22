# 📚 Understanding Padding and Strides in Convolutional Neural Networks (CNNs)

This README provides a concise yet complete explanation of **padding** and **strides** in CNNs, including what they are, how they affect output size, and how to calculate dimensions.

---

## 🧠 What is Padding?

**Padding** refers to the process of adding extra pixels (typically zeros) around the border of an input image before applying a convolution. It helps control the spatial size of the output.

### 🎯 Why Use Padding?

- Preserve spatial dimensions after convolution
- Prevent excessive shrinking of image
- Allow edge features to be learned

### 🔄 Types of Padding:

| Type          | Description                                         |
|---------------|-----------------------------------------------------|
| `valid`       | No padding (may shrink output size)                |
| `same`        | Output has same spatial size as input              |
| Custom (e.g., `padding=1`) | Manual padding with fixed pixels       |

---

## 🏃 What is Stride?

**Stride** is how many pixels the filter moves at each step when sliding across the input.

### 🔍 Effect of Stride:

| Stride | Effect                            |
|--------|-----------------------------------|
| 1      | Standard convolution, detailed    |
| 2+     | Downsamples, reduces output size  |

---

## 🧪 In Code (Keras / TensorFlow Example)

```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Conv2D

model = Sequential([
    Conv2D(32, kernel_size=3, strides=1, padding='same', input_shape=(28, 28, 1))
])
