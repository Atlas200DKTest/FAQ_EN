# Why is the HFBC Format Required for the VDEC of DVPP?<a name="EN-US_TOPIC_0197099111"></a>

## Analysis<a name="section510145717399"></a>

The video decoder \(VDEC\) outputs data in Hisi Frame Buffer Compress \(HFBC\) format to reduce the bandwidth for writing data to the memory. Then the VPC module decompresses the HFBC data. The VDEC and VPC module are independent from each other.

## Advantages of the HBFC format<a name="section068991518406"></a>

The following figure shows the data processing procedure.

![](figures/en-us_image_0197147745.png)

-   After obtaining data in HFBC format from the VDEC, you can call the VPC module to resize or crop the data. For example, resize or crop the obtained HFBC data \(1920\*1080\) to YUV data \(224\*224\). The resizing or cropping operation is performed according to the configuration parameter, and is relatively flexible. You only need to call the VPC module once, ensuring high performance, as the dotted line in the preceding figure.
-   If you need the source image, the HBFC format is not helpful, but does not affect the service functions at all.

