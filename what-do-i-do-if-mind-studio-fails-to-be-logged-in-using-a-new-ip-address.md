# What Do I Do If  Mind Studio  Fails to Be Logged in Using a New IP Address?<a name="EN-US_TOPIC_0196221445"></a>

## Symptom<a name="section1499410410435"></a>

After the IP address is changed, the  **env.conf**  file in  **\~/tools/scripts**  is modified and the network is restarted. However, the login to  Mind Studio  using a new IP address still fails.

## Solution<a name="section1252062216442"></a>

1.  Check the  **env.conf**  file and ensure that the configured IP address is correct.
2.  Restart  Mind Studio. The login is successful.

    >![](public_sys-resources/icon-note.gif) **NOTE:**   
    >After the IP address is changed, you need to restart  Mind Studio  to allow the server to identify the new IP address.  


