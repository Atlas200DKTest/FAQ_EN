# What Do I Do with the Differences Between PIL.Image.open and cv:imread Formats?<a name="EN-US_TOPIC_0197275529"></a>

## Description<a name="section7394811161215"></a>

Are the formats of images read by cv:imread and PIL.Image.open the same?

## Solution<a name="section443073715121"></a>

Images to be read by the  **PIL.Image.open\(\) **function must be in RGB format, and the  **PIL.Image.save\(\)**  function directly saves images in RGB format.

Images to be read by the** cv2.imread\(\) **function must be in BGR format.

If the inference requires images in BGR format, images read by  **cv2.imread\(\)**  can be directly used, and images read by  **PIL.Image.open\(\)**  must be converted into the BGR format before being used.

