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
![Image](../with_crops/cathedral_output.jpg)

![Image](../crops/church_output.jpg)
![Image](../with_crops/church_output.jpg)

![Image](../crops/self_portrait_output.jpg)
![Image](../with_crops/self_portrait_output.jpg)

In these exampls, we can see some of the black borders as well as some of the colored borders being chopped off. Our approach is relatilvely considervative in terms of the method and threshold.

---

Thank you