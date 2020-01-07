# How Do I Locate the Fault During Video Decoding?<a name="EN-US_TOPIC_0197740727"></a>

The video decoding process consists of three phases: video stream obtaining, data transmission, and DVPP decoding. If any of the three phases is faulty, a decoding error may occur. You are advised to locate the fault as follows:

1.  Use the 1.1.T22.B883, 1.3.T25.B883, or a later version \(some bugs are fixed\).
2.  In the video stream obtaining phase, save the data and use a third-party tool \(**eseye\_u.exe**\) to check whether the video can be properly played.
3.  During data transmission, write the data \(to be transmitted from the host to the device\) to a file, and use the third-party tool \(**eseye\_u.exe**\) to check whether the data can be properly played. Determine whether the network transmission is faulty based on the result.
4.  If the fault is still not located, the DVPP decoding may be faulty. Check whether the decoding code is faulty by referring to the decoding code in the released DDK sample.
5.  If the fault is still not located, you can use the sample code of DVPP in the DDK to decode and verify the stream reserved in step 3.

