# How Do I Use the OpenCV in Applications?<a name="EN-US_TOPIC_0197312120"></a>

## Description<a name="section755473935714"></a>

How do I use the OpenCV in applications?

## Solution<a name="section15482118135818"></a>

After the installation of  Mind Studio, the header file of the OpenCV is automatically deployed. You can directly reference the header file in the C++ code. The file is stored in the  **/ddk/include/third\_party/opencv/include/**  directory in the DDK.

For details about how to use the OpenCV, see the face recognition application. For details about the calling code of opencv, reference the  **face\_feature\_mask/face\_feature\_mask.cpp**  file by visiting  [https://github.com/Ascend/sample-facialrecognition](https://github.com/Ascend/sample-facialrecognition).

In a non-C++ environment \(such as Python\), you need to install the OpenCV. There is no Python OpenCV on the Atlas 200 DK. If you need to call the Python OpenCV on the Atlas 200 DK, you need to install the Arm OpenCV.

