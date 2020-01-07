# What Do I Do If the Error Message "Permission denied:xxx/tornado-6.0.2.egg-info" Is Displayed When the Presenter Server Is Started?<a name="EN-US_TOPIC_0196221479"></a>

## Symptom<a name="section1851443531515"></a>

When the presenter server service is started, the message "Permission denied: '/usr/local/lib/python3.5/dist-packages/tornado-6.0.2.egg-info" is displayed, as shown in the following figure.

**Figure  1**  Error reported during the start of the Presenter Server service<a name="fig10642121420269"></a>  
![](figures/error-reported-during-the-start-of-the-presenter-server-service.png "error-reported-during-the-start-of-the-presenter-server-service")

## Solution<a name="section1618075381517"></a>

According to the error information, the installed version of the tornado library is 6.0.2. In this version,  **tornado.gen**  does not have the  **coroutine**  attribute. It is suspected that the installed version is incorrect. Compared with the tornado library installed in Ubuntu where the presenter server can be properly started, it is found that tornado library 5.1 should be installed.

Therefore, run the following commands to uninstall the original tornado library and install the 5.1 version respectively:

**pip3 uninstall tornado**

**Pip3 install tornado==5.1**

