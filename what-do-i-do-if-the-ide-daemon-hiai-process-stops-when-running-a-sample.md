# What Do I Do If the IDE-daemon-hiai Process Stops When Running a Sample?<a name="EN-US_TOPIC_0196221450"></a>

## Symptom<a name="en-us_topic_0160789477_section289913286525"></a>

The following error message is displayed after  **Run**  on  Mind Studio  is clicked to execute a sample.

![](figures/en-us_image_0196221449.png)

## Cause Analysis<a name="en-us_topic_0160789477_section9899928165210"></a>

The IDE-daemon-hiai process is used for data backhaul. The process stops due to  Mind Studio  misoperations or manual operations.

## Solution<a name="en-us_topic_0160789477_section689912812522"></a>

1.  Log in to the  Mind Studio  server as the  Mind Studio  installation user.
2.  Run the following commands to set the environment variables:

    ```
    export  LD_LIBRARY_PATH=~/tools/che/ddk/ddk/uihost/lib
    export  PATH=$PATH:~/tools/che/ddk/ddk/uihost/bin
    ```

3.  Run the following commands to restart the IDE-daemon-hiai process:

    **cd \~/tools/che/ddk/ddk/uihost/bin**

    **./IDE-daemon-hiai**


