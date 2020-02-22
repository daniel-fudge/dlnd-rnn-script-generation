# dlnd-rnn-script-generation
This repo trains a Deep Recurrent Neural Network (RNN) to generate a Seinfeld TV script based on 9 seasons of scripts.  
The motivation for this program was the 3rd project in the Udacity Deep Learning [Nanodegree](https://www.udacity.com/course/deep-learning-nanodegree--nd101). 

## How to run on AWS
This project can be executed directly from within the [dlnd_tv_script_generation.ipynb](dlnd_tv_script_generation.ipynb) 
Jupyter notebook.  Due to the time required to train the model, it is recommended that a GPU is used.  The output shown 
in the report and notebook were generated on AWS' Deep Learning AMI (Ubuntu 18.04) Version 26.0 with a p2.xlarge instance.

1. Launch your AWS instance and ssh into it.
   - Remember to add a "Custom TCP Rule" to your security group inbound rules to allow Jupyter notebooks.
   
   #### From AWS CLI
1. Configure Jupyter notebook  
   ```bash
   jupyter notebook --generate-config
   sed -ie "s/#c.NotebookApp.ip = 'localhost'/#c.NotebookApp.ip = '*'/g" ~/.jupyter/jupyter_notebook_config.py
   ```

1. Clone the repo.
   ```bash 
   git clone https://github.com/daniel-fudge/dlnd-rnn-script-generation
   ```

1. Activate Python 3 environment with PyTorch, CUDA 10 and MKL-DNN.
   ```bash 
   source activate pytorch_p36
   ```

1. Start Jupyter notebook
   ```bash   
   jupyter notebook --ip=0.0.0.0 --no-browser
   ``` 

1. Record the long URL generated by the previous command, it should have the format 
http://[some_ip]:8888/?token=[your_token].
   
   #### From your local PC
1. Connect to the notebook from your browser by replacing [some_ip] with your instances IPv4 Public IP.

1. Open `dlnd_tv_script_generation.ipynb`.

1. Read and/or run the cells at your leisure!!  :)   

## How to run on Local PC   
Although it is not recommended to train on a local PC, you may want to run locally to debug.  

1. Clone repo to PC.
   ```shell script
   git clone https://github.com/daniel-fudge/dlnd-rnn-script-generation
   ```

1. [OPTIONAL] Install [Anaconda3](https://www.anaconda.com/distribution/).

1. [OPTIONAL] Create a virtual environment.
   ```shell script
   conda update conda
   conda create -n script python=3.7 
   conda activate script
   conda install pytorch
   conda install matplotlib
   conda install tqdm
   conda install ipykernel
   conda install jupyter
   ipython kernel install --name=script
   ```
   
1. [OPTIONAL] Activate the virtual environment.
   ```shell script
   conda activate script
   ```

1. Launch Jupyter.
   ```shell script
   cd dlnd-rnn-script-generation
   jupyter notebook
   ```

1. Open `dlnd_face_generation.ipynb`.

1. Read and/or run the cells at your leisure!!  :)
 
## Report
A [report](report.html) was generated from the [Jupyter Notebook](dlnd_tv_script_generation.ipynb) for those who prefer 
to simply view the notebook as a html file.

## License
This code is copyright under the [MIT License](LICENSE).

## Contributions
Please feel free to raise issues against this repo if you have any questions or suggestions for improvement.
