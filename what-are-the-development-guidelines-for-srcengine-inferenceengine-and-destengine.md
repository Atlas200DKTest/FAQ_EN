# What Are the Development Guidelines for SrcEngine, InferenceEngine, and DestEngine?<a name="EN-US_TOPIC_0196221509"></a>

Almost all nodes \(except the model\) on the  Mind Studio  canvas are engines, which are the basic elements of a graph.

A graph is initialized during the start of the application framework. Then, code is written to inject data to the first engine. Once data is input, the engine starts to work. Data is input to and processed by one engine, and then output to the next engine. The next engine starts to work once receiving the input from the previous engine. This applies to the subsequent engines until the last engine finishes processing and outputs the result, which means that a single execution ends.

In normal cases, the dataset is prepared first, and then the dataset is injected into the pre-processing engine by frame. After the pre-processing is complete, the data is handed over to the model inference engine. After the model inference is complete, the data to the post-processing engine to finish an entire inference process.

Generally, the pre-processing engine converts the input data into the format required by the model. For CV applications, the Huawei-developed DVPP can be called to implement image pre-processing, such as cropping and format conversion.

Inference is performed by obtaining the handling result of the previous layer and calling a related model.

The post-processing node performs subsequent operations based on the inference result, which can be directly printed as a log \(output to a file\). If the result is the coordinates of two points of a rectangle, the post-processing node can draw a rectangle on the original image based on the coordinates of the two points and compile programs as required.

