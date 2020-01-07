# Does ret=ai\_model\_manager-\>process Support the Multi-Input Multi-Output Scenario?<a name="EN-US_TOPIC_0196221389"></a>

**ret = ai\_model\_manager\_-\>Process**  supports the multi-input multi-output scenario. For details, see the code in  **MindInferenceEngine1.cpp**.

```
    // put buffer to FrameWork directly, InputSize has only one
    hiai::AITensorDescription inputTensorDesc = hiai::AINeuralNetworkBuffer::GetDescription();
    for (int i = 0; i < predict_input_data_.size(); i++) {
        std::map<uint8_t *, int> tmp = predict_input_data_[i];
        for (std::map<uint8_t *, int>::iterator it = tmp.begin();it != tmp.end(); ++it) {
            shared_ptr<hiai::IAITensor> inputTensor =
                hiai::AITensorFactory::GetInstance()->CreateTensor(inputTensorDesc, (void *)(it->first), it->second);
            input_data_vec.push_back(inputTensor); // AIModelManager push input data
        }
     }
```

