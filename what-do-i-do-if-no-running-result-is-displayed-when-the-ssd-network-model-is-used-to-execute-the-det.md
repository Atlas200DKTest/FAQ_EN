# What Do I Do If No Running Result Is Displayed When the SSD Network Model Is Used to Execute the Detector App?<a name="EN-US_TOPIC_0196221497"></a>

## Symptom<a name="section512664984119"></a>

When the trained SSD detector app is used to recognize texts in various scenarios, the model can be imported successfully, but the output cannot be viewed on the post-processing node.

[Figure 1](#fig43062011114910)  shows the orchestration process.

**Figure  1**  Detector orchestration process<a name="fig43062011114910"></a>  
![](figures/detector-orchestration-process.png "detector-orchestration-process")

## Solution<a name="section8758137105016"></a>

Ensure that the process orchestration engine is correctly deployed. Check key configurations when the project type is correct and the network connection is normal.

-   SSD is the dataset with  **Data Type**  of  **Image**  imported in  **My Datasets**, as shown in  [Figure 2](#fig51871639165810).

    **Figure  2**  Dataset import<a name="fig51871639165810"></a>  
    ![](figures/dataset-import.png "dataset-import")

-   depoy\_ssd is the model imported in  **My Models**, as shown in  [Figure 3](#fig32801913104).

    **Figure  3**  Importing the SSD network model<a name="fig32801913104"></a>  
    ![](figures/importing-the-ssd-network-model.png "importing-the-ssd-network-model")

    The required height and width of the input image are 300 x 300.

-   Change the  **Resize**  value of the ImagePreProcess node to be the same as that required by the model, as shown in  [Figure 4](#fig1199017311324).

    **Figure  4**  Configuring the ImagePreProcess node<a name="fig1199017311324"></a>  
    ![](figures/configuring-the-imagepreprocess-node.png "configuring-the-imagepreprocess-node")


After the preceding configurations are correct, run the orchestration process again. Right-click  **SSDPostProcess**  and choose  **image result**  from the shortcut menu to view the image processing result.

