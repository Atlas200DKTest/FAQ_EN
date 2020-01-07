# How Do I Turn Three-Channel Source Images to Single-Channel Images Required as Input Data?<a name="EN-US_TOPIC_0197320306"></a>

## Description<a name="section6121513102316"></a>

The source images are in three channels, but single-channel data is required during data input. How do I modify the code to turn the source images to single-channel images?

## Solution<a name="section1710418500234"></a>

Convert the source three-channel images into gray scale images. The code example is as follows:

```
bool face_emotion_inference::ImageYUV2BGR (
  const vector<ImageData<u_int8_t>> &resized_image,
  vector<Mat> &bgr_image) {
  for (vector<ImageData<u_int8_t>>::const_iterator resized_img_iter = resized_image.begin();
       resized_img_iter != resized_image.end(); ++resized_img_iter) {
 
    int img_height = resized_img_iter->height;
    int img_width = resized_img_iter->width;
    //std::cout<<"img height, img width"<<img_height<<"  "<<img_width<<std::endl;
    Mat src(img_height * kNv12SizeMolecule / kNv12SizeDenominator,
            img_width, CV_8UC1);
 
    int copy_size = img_width * img_height * kNv12SizeMolecule
                    / kNv12SizeDenominator;
    int destination_size = src.cols * src.rows * src.elemSize();
    int ret = memcpy_s(src.data, destination_size, resized_img_iter->data.get(),
                       copy_size);
    CHECK_MEM_OPERATOR_RESULTS(ret);
    
    Mat dst_temp;
    cvtColor(src, dst_temp, CV_YUV2BGR_NV12);
    Mat dst;
    dst_temp.convertTo(dst, CV_32FC3);
    //for(int i = 0; i < dst.rows; i++)
    //{
    //      for(int j = 0; j < dst.cols; j++)
            //{
                //std::cout<<"("<<dst.at<Vec3b>(i,j)[0]<<",";
                //std::cout<<dst.at<Vec3b>(i,j)[1]<<",";
                //std::cout<<dst.at<Vec3b>(i,j)[2]<<")";
            //}
            //std::cout<<std::endl;
    //}
    //imwrite("dst_temp.jpg", dst_temp);
    //imwrite("BGR.jpg",dst);
    //dst_temp = imread("face1.jpg");
    //dst_temp.convertTo(dst, CV_32FC3);
    bgr_image.push_back(dst);
  }
  return true;
}
```

