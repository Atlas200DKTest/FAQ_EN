# What Do I Do If an Error Occurs in the deploy.sh Script During the Deployment of the Facial Recognition Application?<a name="EN-US_TOPIC_0196221492"></a>

## Symptom<a name="section20221826172014"></a>

During the deployment of the face recognition application, the following message is displayed in the execution of the  **deploy.sh**  script:  IDE-daemon-client: error while loading shared libraries: lib\_sec.so: cannot open shared object file: No such file or directory.

**Figure  1** **deploy.sh**  execution failure during facial recognition application deployment<a name="fig1047314449154"></a>  
![](figures/deploy-sh-execution-failure-during-facial-recognition-application-deployment.png "deploy-sh-execution-failure-during-facial-recognition-application-deployment")

## Solution<a name="section56211924112519"></a>

1.  Search for the  **lib\_sec.so**  file in the current system, as shown in the following figure.

    **Figure  2**  Searching for the lib\_sec.so file on the  Mind Studio  server<a name="fig10642121420269"></a>  
    ![](figures/searching-for-the-lib_sec-so-file-on-the-mind-studio-server.png "searching-for-the-lib_sec-so-file-on-the-mind-studio-server")

    As shown in the preceding figure, the file exists in  **$HOME/tools/che/ddk/ddk/lib**.

    The file exists but cannot be found by the app. Therefore, it is inferred that the environment variable is not set.

2.  Set the following environment variables in  **\~/.bashrc**:

    export DDK\_HOME=$HOME/tools/che/ddk/ddk

    export LD\_LIBRARY\_PATH=$DDK\_HOME/uihost/lib


