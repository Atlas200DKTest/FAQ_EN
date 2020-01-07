# What Do I Do If the MongoDB Service Fails to Be Stopped During Uninstallation?<a name="EN-US_TOPIC_0196221418"></a>

## Symptom<a name="en-us_topic_0160789093_section20371103812615"></a>

During the uninstallation, the MongoDB service fails to be stopped due to abnormal operations \(for example, manually deleting database files\), as shown in  [Figure 1](#en-us_topic_0160789093_fig1147210535611).

**Figure  1**  MongoDB service stop failure during the uninstallation<a name="en-us_topic_0160789093_fig1147210535611"></a>  
![](figures/mongodb-service-stop-failure-during-the-uninstallation.png "mongodb-service-stop-failure-during-the-uninstallation")

## Solution<a name="en-us_topic_0160789093_section15677586271"></a>

You can run the  **kill**  or  **pkill**  on Linux to forcibly stop the MongoDB, for example,  **pkill mongodb**. Then, uninstall MongoDB.

