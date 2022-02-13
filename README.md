# Exoplanet-Classifier

Every day, large space telescopes such as the Hubble Space Telescope, MOST, and CAROT find new solar systems which could contain life-harboring exoplanets. However, it is difficult for scientists to sift through thousands of images to find the few samples which indicate the presence of exoplanets. 

![image](https://github.com/cpalappillil/Exoplanet-Classifier/blob/main/exoplanet.jfif)

To quantify this classification task, we used flux curves generated by NASA. The flux curves plot measured light intensity over an exposure interval. Fluctuations in light intensity are caused by an object occluding the starlight from the telescope lens. Regular fluctuations in light intensity may indicate the presence of an exoplanet because the flux pattern could be created by a regularly orbiting body.

Non-Exoplanet Flux Curves:
![image](https://github.com/cpalappillil/Exoplanet-Classifier/blob/main/Non-Exoplanet%20Flux%20Curve%20(1).png)

Exoplanet Flux Curves:
![image](https://github.com/cpalappillil/Exoplanet-Classifier/blob/main/Exoplanet%20Flux%20Curve.png)

We aim to develop a model to perform binary classification on the NASA exoplanet flux curve dataset. However, we found that model training was challenging due to the dataset's class imbalance (roughly 100 non-exoplanet flux curves for every exoplanet flux curve). To mitigate this, we utilize the Synthetic Minority Oversampling Technique (SMOTE) algorithm. The SMOTE algorithm selects two examples from the underrepresented class and draws a line in feature space to connect these two points. It then continuously samples from the connecting line segment and appends to the training dataset.

![image](https://github.com/cpalappillil/Exoplanet-Classifier/blob/main/SMOTE-Algorithm.png)

After applying the SMOTE algorithm, we were able to achieve class balance. We then applied a simple K-nearest neighbors classification model to perform the binary classification. The model was able to classify flux curves from a novel testing dataset with 99% accuracy.

![image](https://github.com/cpalappillil/Exoplanet-Classifier/blob/main/Confusion%20Matrix.png)
