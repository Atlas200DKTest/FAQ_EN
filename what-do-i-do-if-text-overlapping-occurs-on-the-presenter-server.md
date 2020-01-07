# What Do I Do If Text Overlapping Occurs on the Presenter Server?<a name="EN-US_TOPIC_0197320523"></a>

## Description<a name="section52055115270"></a>

What do I do if text overlapping occurs on the Presenter Server?

## Solution<a name="section741873632717"></a>

In the CPP code implemented by the engine postprocessing, the following statement needs to be executed each time a text is sent to the Presenter Server:

**DetectionResult oneResult;**

Place this statement in the loop statement that sends text to the Presenter Server.

