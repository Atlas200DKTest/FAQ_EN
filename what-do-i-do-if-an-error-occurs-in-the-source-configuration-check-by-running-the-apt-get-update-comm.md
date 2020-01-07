# What Do I Do If an Error Occurs in the Source Configuration Check by Running the apt-get update Command During  Mind Studio  Installation?<a name="EN-US_TOPIC_0196221471"></a>

## Symptom<a name="section187236589283"></a>

-   Problem 1:

    In environment preparation before  Mind Studio  deployment, after the source dependencies are configured and the  **apt-get update**  command is executed, the following error message is displayed:

    ```
    Aborted (core dumped) 
    Reading package lists... Done
    E: Problem executing scripts APT::Update::Post-Invoke-Success 'if /usr/bin/test -w /var/cache/app-info -a -e /usr/bin/appstreamcli; then appstreamcli refresh > /dev/null; fi'
    E: Sub-process returned an error code
    ```

-   Problem 2:

    In environment preparation before  Mind Studio  deployment, after the source dependencies are configured and the  **apt-get update**  command is executed, the following error message is displayed:

    ```
    E: Could not get lock /var/lib/dpkg/lock - open (11: Resource temporarily unavailable) 
    E: Unable to lock the administration directory (/var/lib/dpkg/), is another process using it?
    ```


## Solution<a name="section1027210256303"></a>

-   Solution to Problem 1:

    If the libappstream3 library is missing, run the following commands to clear the related software package and perform the update:

    ```
    sudo apt-get purge libappstream3
    sudo apt-get update
    ```

-   Solution to Problem 2:

    Run the following commands to delete the lock:

    ```
    sudo rm /var/cache/apt/archives/lock
    sudo rm /var/lib/dpkg/lock
    ```


