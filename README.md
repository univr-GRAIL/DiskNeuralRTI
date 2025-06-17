# DiskNeuralRTI Implementation
This is a PyTorch implementation of DiskNeuralRTI. 

## Getting Started
Download and extract DiskNeuralRTI  
Change working directory to DiskNeuralRTI  
## Create a virtual environment:   
    python -m venv neuralenv  
### Activate a virtual environment:  
    On Windows:  
       neuralenv\Scripts\activate  
    On Linux/macOS:  
       source neuralenv/bin/activate  
## Install Dependencies:    
    Please install the dependencies using the following command:    
      pip install -r requirements.txt  
    Make sure you're in a Python environment, neuralenv    
## Training  
    To train DiskNeuralRTI on your dataset, modify the training parameters.  
    Edit utils/params.py to point to your dataset and training config.  
       data_path: "your_dataset_path/",  
       output_path: "output/"  
       mask: "True/False"  
    Once the training is completed, you will find an output file inside the output_path directory.   
    The output contains:
        The model and compressed coefficient used for testing.
        The image planes and JSON file used for interactive relighting using the [openlime](https://github.com/cnr-isti-vclab/openlime) web visualizer.
## Run   
    python train.py  
    
   If the codes run correctly, you will find the output file [input-file/output] in the directory  

## Test/Relighting  
    To generate a relighted image:  
    open test.py  
    Modify these variables:  
    model_path = "output/model_name.pth"  # your trained model  
    gt_path = "your_test_image"  

## Run:  
    python test.py  
    It will output a relighted image model_path + '/relighted' folder.  




