# What Do I Do If the silence Operator Is Not Supported During Model Conversion?<a name="EN-US_TOPIC_0197347959"></a>

## Description<a name="section2887174311195"></a>

Model conversion failure is caused by the unsupported silence operator.

## Solution<a name="section1955510913206"></a>

The silence operator is used to shield unnecessary log information.

The silence operator does not perform any operation in the Caffe source code. Therefore, you can comment out the silence layer in  **prototxt**  before model conversion.

