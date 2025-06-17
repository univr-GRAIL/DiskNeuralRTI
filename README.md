# DiskNeuralRTI Implementation
This is a PyTorch implementation of DiskNeuralRTI. 

## Getting Started
Download and extract DiskNeuralRTI  
Change working directory to DiskNeuralRTI  
## Create a virtual environment:   
&nbsp;&nbsp;&nbsp;&nbsp;python -m venv neuralenv  
### Activate a virtual environment:  
On Windows:  
    &nbsp;&nbsp;&nbsp;&nbsp;neuralenv\Scripts\activate  
On Linux/macOS:  
    &nbsp;&nbsp;&nbsp;&nbsp;source neuralenv/bin/activate  
## Install Dependencies:    
Install the dependencies using the following command:    
    &nbsp;&nbsp;&nbsp;&nbsp;pip install -r requirements.txt  
    &nbsp;&nbsp;&nbsp;&nbsp;Make sure you're in a Python environment, neuralenv    
## Training  
To train **DiskNeuralRTI** on your dataset, modify the training parameters.  
    Edit utils/params.py to point to your dataset and training config.  
      &nbsp;&nbsp;&nbsp;&nbsp; data_path: "your_dataset_path/",  
       &nbsp;&nbsp;&nbsp;&nbsp;output_path: "output/"  
      &nbsp;&nbsp;&nbsp;&nbsp; mask: "True/False"  
Run   
&nbsp;&nbsp;&nbsp;&nbsp;python train.py  
Once the training is completed, you will find an output file inside the `output_path` directory.

The output contains:
- The model and compressed coefficients used for testing.
- The image planes and JSON file used for interactive relighting using the [OpenLIME tool](https://github.com/cnr-isti-vclab/openlime) web visualizer.

   
If the codes run correctly, you will find the output file [input-file/output] in the directory  

## Test/Relighting  
To generate a relighted image:  
   &nbsp;&nbsp;&nbsp;&nbsp; open test.py  
   &nbsp;&nbsp;&nbsp;&nbsp; Modify these variables:  
    &nbsp;&nbsp;&nbsp;&nbsp; model_path = "output/model_name.pth"  # your trained model  
    &nbsp;&nbsp;&nbsp;&nbsp;gt_path = "your_test_image"  

## Run:  
python test.py  
    It will output a relighted image model_path + '/relighted' folder.  




