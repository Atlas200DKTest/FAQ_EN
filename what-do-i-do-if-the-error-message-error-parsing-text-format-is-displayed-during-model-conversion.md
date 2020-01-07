# What Do I Do If the Error Message "Error parsing text-format..." Is Displayed During Model Conversion?<a name="EN-US_TOPIC_0196221433"></a>

## Description<a name="section10435181814317"></a>

During model conversion, the error information shown in the following figure is displayed.

**Figure  1**  Model conversion failure<a name="fig1228161315813"></a>  
![](figures/model-conversion-failure-0.png "model-conversion-failure-0")

The  **convertModel.log**  file reports the following error.

**Figure  2**  Model conversion log<a name="fig63765414413"></a>  
![](figures/model-conversion-log.png "model-conversion-log")

## Solution<a name="section1539715189455"></a>

According to the log, it is inferred that the data in the model should be an integer, but the actual input is a character with the symbol  **@**. Check the model file. It is found that the defined dimension parameters are incorrect, as shown in the following figure.

**Figure  3**  Definition of model file dimensions<a name="fig174574264513"></a>  
![](figures/definition-of-model-file-dimensions.png "definition-of-model-file-dimensions")

Change the dimensions in the model file to the correct dimensions.

