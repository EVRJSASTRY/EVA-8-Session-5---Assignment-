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


from sklearn import preprocessing
import numpy as np
x_array = np.array([2,3,5,6,7,4,8,7,6])
normalized_arr = preprocessing.normalize([x_array])
print(normalized_arr)


from sklearn import preprocessing
import numpy as np
x_array = np.array([2,3,5,6,7,4,8,7,6])
normalized_arr = preprocessing.normalize([x_array])
print(normalized_arr)


import pandas as pd
housing = pd.read_csv("/content/sample_data/california_housing_train.csv")

from sklearn import preprocessing
x_array = np.array(housing['total_bedrooms'])
normalized_arr = preprocessing.normalize([x_array])
print(normalized_arr)

from sklearn import preprocessing
import pandas as pd
housing = pd.read_csv("/content/sample_data/california_housing_train.csv")
scaler = preprocessing.MinMaxScaler()
names = housing.columns
d = scaler.fit_transform(housing)
scaled_df = pd.DataFrame(d, columns=names)
scaled_df.head()

from sklearn import preprocessing
import pandas as pd
housing = pd.read_csv("/content/sample_data/california_housing_train.csv")
scaler = preprocessing.MinMaxScaler(feature_range=(0, 2))
names = housing.columns
d = scaler.fit_transform(housing)
scaled_df = pd.DataFrame(d, columns=names)
scaled_df.head()

