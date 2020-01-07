# Failed to Run the Sample Again<a name="EN-US_TOPIC_0197323456"></a>

## Description<a name="section1698923820415"></a>

The Presenter Server page does not respond when a human detection sample is executed again after adaptation and replacement.

## Solution<a name="section122891428134216"></a>

To run an application repeatedly, ensure that the name displayed on the Presenter Server is unique. For example:

bash run\_videoanalysispersonapp.sh 192.168.1.2_** video**_  "/home/HwHiAiUser/sample/person.mp4" &

In the preceding command, you need to change  **video**  to ensure that the name is unique on the Presenter Server page.

