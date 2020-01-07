# How Do I Handle Unsupported Operators During SSD Caffe Model Conversion?<a name="EN-US_TOPIC_0196221440"></a>

## Symptom<a name="section7716124311484"></a>

During SSD Caffe model conversion, a message is displayed indicating there is an unsupported operator, as shown in the following figure.

**Figure  1**  Message indicating an unsupported operator during model conversion<a name="fig174574264513"></a>  
![](figures/message-indicating-an-unsupported-operator-during-model-conversion.png "message-indicating-an-unsupported-operator-during-model-conversion")

## Solution<a name="section23231150194913"></a>

Check the unsupported operator at the bottom of the table, as shown in the following figure.

**Figure  2**  Viewing the unsupported operator<a name="fig15988122812506"></a>  
![](figures/viewing-the-unsupported-operator.png "viewing-the-unsupported-operator")

The system prompts that the DetectionOutPut operator is not supported. In the  **Suggestion**  column on the right, select the DetectionOutput operator corresponding to the current network.

