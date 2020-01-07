# What Do I Do If a Message Indicating Layers Objects Are Not Supported During Caffe Model Conversion?<a name="EN-US_TOPIC_0196221386"></a>

## Symptom<a name="section1760921964310"></a>

The following error is reported during Caffe model conversion:

```
The weight file is consisted of layers-structure 
which is deprecated in caffe and unsupport in OMG. It is recommended to convert layers-structure 
to layer-structure by caffe tool.
```

## Solution<a name="section85644565466"></a>

The  **layers **objects in the model file are not supported by the model conversion tool. You need to change them to  **layer **objects and modify the  **layer **attributes if necessary.

Use the following Caffe tools on GitHub to convert  **layers **objects to  **layer **objects:  **\\caffe-master\\tools\\upgrade\_net\_proto\_binary.cpp**  and  **\\caffe-master\\tools\\upgrade\_net\_proto\_text.cpp.**

