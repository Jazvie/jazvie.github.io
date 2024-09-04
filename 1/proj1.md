# Project 1

Hello, here is things.

## Section 1: Images

![Image](../outputs/emir_output.jpg)
![Image](../outputs/cathedral_output.jpg)
![Image](../outputs/church_output.jpg)
![Image](../outputs/icon_output.jpg)
![Image](../outputs/harvesters_output.jpg)
![Image](../outputs/lady_output.jpg)
![Image](../outputs/melons_output.jpg)
![Image](../outputs/monastery_output.jpg)
![Image](../outputs/onion_church_output.jpg)
![Image](../outputs/sculpture_output.jpg)
![Image](../outputs/self_portrait_output.jpg)
![Image](../outputs/three_generations_output.jpg)
![Image](../outputs/tobolsk_output.jpg)
![Image](../outputs/train_output.jpg)


## Section 2: Cropping

As a part of the extra bells and whistles, we can add cropping. For cropping, the mindset was that we would rather remove less if it means preserving 'important' information. For example, the bars are not always straight, and therefore there may be parts of the image that may be lost if we are to cut further down. This is why some but not all of the colored bars are removed. This implementation is based off of the simple observation that borders are mostly just black lines, or deviate little from black lines. Therefore, we can place a threshold on the variance of the pixel values until it reaches a certain point. Although it is not a problem for these images, we also kept a maximum possible area of cutoff as to prevent searching too far and either cutting too much or spending needless time doing computations.


![Image](../crops/cathedral_output.jpg)
With cropping:
![Image](../with_crops/cathedral_output.jpg)

![Image](../crops/church_output.jpg)
With cropping:
![Image](../with_crops/church_output.jpg)

![Image](../crops/self_portrait_output.jpg)
With cropping:
![Image](../with_crops/self_portrait_output.jpg)

In these exampls, we can see some of the black and white borders as well as some of the colored borders being chopped off. Our approach is relatilvely considervative in terms of the method and threshold.

## Section 3: Edge-Based Alignment

This section concerns only one image in particular, that being of emir.tif, as it is the only one notably impacted by this change, besides maybe the train. In order to explain why this is the case, we must explain the original implementation. Before, we made use of normalized-cross-correlation, which worked as a suitable measure as it managed relative differences better than other ones like l2 or l2 distance. This however caused a problem because the man's outfit was very blue in this picture, and thus there is a huge area in the slide with a mass of lagre values for the blue layer, and none for the red. Therefore the program would be way off, as it would try to align his outfit with the door or his beard, which have more red and green. To fix this problem, we can make use of an edge detection kernel and a convolution. Here we take both a vertical and horizontal edge detector kernel, sum the output, and then run the alignment function on that. We see a massive improvement in emir. Moreover this made some improvments on train, as this image would have trouble on smaller pyramids prior to this adjustment.

![Image](../without_edge/emir_output.jpg)
Now with edge-detection:
![Image](../with_edge/emir_output.jpg)


## Section 3: Automatic Contrasting

This one is a purley aesthetic change, and so viewer is the judge as to if it is preferable or not. Here we convert the image to YcrCb and use the value of Y as out measure of contrast. We then linearly scale all values accordingly and then convert back. We see overall this has the effect of making things darker and moodier.

![Image](../with_lum/melons_output.jpg)
Without Contrasting:
![Image](../with_edge/melons_output.jpg)

![Image](../with_lum/emir_output.jpg)
Without Contrasting:
![Image](../with_edge/emir_output.jpg)

![Image](../with_lum/harvesters_output.jpg)
Without Contrasting:
![Image](../with_edge/harvesters_output.jpg)

![Image](../with_lum/icon_output.jpg)
Without Contrasting:
![Image](../with_edge/icon_output.jpg)

![Image](../with_lum/lady_output.jpg)
Without Contrasting:
![Image](../with_edge/lady_output.jpg)

![Image](../with_lum/train_output.jpg)
Without Contrasting:
![Image](../with_edge/train_output.jpg)

---

Thank you