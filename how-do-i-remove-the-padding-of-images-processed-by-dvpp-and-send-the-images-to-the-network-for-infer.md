# How Do I Remove the Padding of Images Processed by DVPP and Send the Images to the Network for Inference?<a name="EN-US_TOPIC_0197840051"></a>

## Description<a name="section103624392404"></a>

Assume that the image size required by network inference is 200\*200 and the source image size is 1440\*1440. Images obtained by JPEG decoding are 1536\*1440 \(128\*16 aligned\). How do I obtain 200\*200 images without padding from the decoded images and send the images to the network for inference?

## Solution<a name="section12390115974010"></a>

1.  Call the VPC module to perform cropping and resizing on the images obtained by JPEG decoding, and obtain the 208\*200 images \(16\*2 aligned\) with padding.
2.  Use AIPP to process the images processed by the VPC module \(configure AIPP during model conversion\) and crop the images to obtain 200\*200 images without padding that meet the network requirements.

