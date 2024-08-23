# Processing-image-data-for-Deep-Learning

This project demonstrates basic image processing techniques using Python. It covers the following topics:

1. **Reading an Image File and Converting it to a Numpy Array**
2. **Resizing an Image**
3. **Converting an RGB Image to Grayscale**

## Libraries Used

- **Matplotlib:** For reading and displaying images.
- **Pillow:** For image resizing.
- **OpenCV:** For advanced image processing, such as RGB to Grayscale conversion.

## How to Run the Code

1. **Reading an Image:**

   The image is fetched from the web using `wget` and then loaded using `matplotlib.image`. The image is converted into a numpy array.

   ```python
   import matplotlib.image as mpimg
   import matplotlib.pyplot as plt

   img = mpimg.imread('/content/puppy-care-guide-for-new-parents.jpg')
   ```

   The shape of the image can be checked using:

   ```python
   print(img.shape)
   ```

2. **Displaying the Image:**

   The image is displayed using Matplotlib's `imshow` function.

   ```python
   img_plot = plt.imshow(img)
   plt.show()
   ```

3. **Resizing the Image:**

   The image is resized using the Pillow library.

   ```python
   from PIL import Image

   img = Image.open('/content/puppy-care-guide-for-new-parents.jpg')
   img_resized = img.resize((200, 200))
   img_resized.save('dog_image_resized.jpg')
   ```

   The resized image is then displayed.

   ```python
   img_res = mpimg.imread('/content/dog_image_resized.jpg')
   img_res_plot = plt.imshow(img_res)
   plt.show()
   ```

4. **Converting RGB Image to Grayscale:**

   The image is converted to grayscale using OpenCV.

   ```python
   import cv2

   img = cv2.imread('/content/puppy-care-guide-for-new-parents.jpg')
   grayscale_image = cv2.cvtColor(img, cv2.COLOR_RGB2GRAY)
   ```

   The grayscale image is displayed using `cv2_imshow`.

   ```python
   from google.colab.patches import cv2_imshow
   cv2_imshow(grayscale_image)
   ```

   Finally, the grayscale image is saved.

   ```python
   cv2.imwrite('dog_grayscale_image.jpg', grayscale_image)
   ```

## Notes

- The image displayed using `cv2.imshow()` is not supported in Google Colab, so `cv2_imshow` from `google.colab.patches` is used instead.
- The example image used in this project is a sample puppy image fetched from the web.

## Requirements

- Python 3.x
- Libraries: `matplotlib`, `Pillow`, `OpenCV`, `numpy`
- Google Colab or any local Python environment

## Conclusion

This project provides a simple introduction to image processing in Python using common libraries. It covers basic tasks such as reading, displaying, resizing, and converting images.
