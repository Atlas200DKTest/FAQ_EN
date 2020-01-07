# How Do I Quickly Stop the Presenter Server Process?<a name="EN-US_TOPIC_0197319622"></a>

## Description<a name="section2056755971815"></a>

Each time I want to stop the Presenter Server process, I need to find the corresponding process and then kill it. How can I kill the process quickly?

## Solution<a name="section18115152196"></a>

Save the following code as the  **stop.sh**  script. The following script uses the face detection application as an example. You can modify other examples by referring to the code.

```
#!/bin/sh
 
i=$(ps -ef | grep presenter | grep face_detection | grep -o '[0-9]\+' | head -n1)
if [ -z "$i" ] ;then
echo presenter sever not in process!
exit
fi
kill -9 $i
echo presenter sever stop success!
```

To stop the Presenter Server process, run the  **bash stop.sh**  command.

