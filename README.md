# EVA-8-Session-5---Assignment-


import numpy as np
from PIL import Image
import os

#Check if the file exist before trying to open it
if os.path.exists("image.jpg"):
    # Open the image
    im = Image.open("image.jpg")

    # Convert the image to a numpy array
    im_arr = np.array(im)

    # Find the minimum and maximum intensity values
    min_intensity = np.min(im_arr)
    max_intensity = np.max(im_arr)

    # Normalize the image
    im_norm = (im_arr - min_intensity) / (max_intensity - min_intensity) * 255

    # Convert the normalized image back to an image object
    im_norm = Image.fromarray(im_norm)

    # Save the normalized image
    im_norm.save("image_norm.jpg")
else:
    print("The file image.jpg does not exist.")
