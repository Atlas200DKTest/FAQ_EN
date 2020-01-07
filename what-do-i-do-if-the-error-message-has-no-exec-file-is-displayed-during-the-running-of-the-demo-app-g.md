# What Do I Do If the Error Message "has no exec file" Is Displayed During the Running of the Demo App "General Classification Network"?<a name="EN-US_TOPIC_0196221463"></a>

## Symptom<a name="section1641725321110"></a>

During the execution of the general classification network app according to the guide, the error message "has no exec file" is displayed.

## Solution<a name="section121169915126"></a>

Run the following command on the server where  Mind Studio  is located to check the deployed cross compilation environment:

**ls -alF /usr/lib/aarch64-linux-gnu**

The information shown in the following figure indicates that the  Mind Studio  server is not configured with a cross compilation environment.

**Figure  1**  Lack of the cross compilation environment configuration<a name="fig1199017311324"></a>  
![](figures/lack-of-the-cross-compilation-environment-configuration.png "lack-of-the-cross-compilation-environment-configuration")

Configure the cross compilation environment by referring to  **Configuring the UI Host Cross Compilation Environment**  in  _Ascend 310 Atlas 200 Developer Kit User Guide_.

The following figure shows the command output when the cross compilation environment has been configured.

**Figure  2**  Command output showing the configured cross compilation environment<a name="fig1047314449154"></a>  
![](figures/command-output-showing-the-configured-cross-compilation-environment.png "command-output-showing-the-configured-cross-compilation-environment")

