# What Do I Do If the RTSP Video Stream Cannot Be Used in the Sample Program?<a name="EN-US_TOPIC_0197324298"></a>

## Description<a name="section453954114485"></a>

When the vehicle detection application is running, the RTSP video stream fails to be run and is not displayed on the UI.

## Cause Analysis<a name="section11178522175215"></a>

The possible causes are as follows:

-   The video stream is faulty.
-   The application running mode is incorrect.

Play the RTSP video stream in the media player. If the playback succeeds, the RTSP video stream is normal. Then, the fault may be caused by the incorrect running mode.

Check the .config file and find that the RTSP video stream uses  **channel1**. In the program running command,  **channel1**  indicates the video file path, and an RTSP video stream should use  **channel2**. Therefore, it is suspected that the RTSP video stream uses  **channel1**  instead of  **channel2**  because no space is used to occupy  **channel1**  during startup.

## Solution<a name="section123665634818"></a>

When the  **run **script is executed, the RTSP video stream needs to use  **channel2**. In this case, a space is required to occupy  **channel1**. Otherwise, the program cannot identify whether the current file is an MP4 file or an RTSP video stream.

For example:

bash run\_videoanalysiscarapp.sh 192.168.1.2 video " " "rtsp://192.168.2.37:554/cam/realmonitor?channel=1&subtype=0" &

