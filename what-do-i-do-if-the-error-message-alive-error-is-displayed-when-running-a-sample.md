# What Do I Do If the Error Message"alive error" Is Displayed When Running a Sample?<a name="EN-US_TOPIC_0196221438"></a>

## Symptom<a name="en-us_topic_0160789474_section14919151728"></a>

If  Mind Studio  and the host are not on the same PC, the following error message is displayed after  **Run**  is clicked to execute an app.

![](figures/en-us_image_0196221404.png)

## Cause Analysis<a name="en-us_topic_0160789474_section97721308312"></a>

IDE-daemon listens to the static IP address during startup. If the IP address is not set,  Mind Studio  cannot run an app.

## Solution<a name="en-us_topic_0160789474_section4574115520412"></a>

Run the  **sudo vi /etc/network/interfaces**  command in the system IP configuration file to set the IP address of the host to a static IP address, as shown in the following figure.

![](figures/en-us_image_0196221394.png)

