# Phys710 "Hands-on introduction to HPC+QPU" 

> [!IMPORTANT]  
> This repository will be updated throughout the semester. Make sure to star and follow for updates! 

These seminar series will serve as an introduction to the practical applications of quantum computing in a HPC+QPU setting. It is designed for students who wish to explore the exciting and rapidly developing field of HPC integrated QPUs. 

This is a hands-on course where you will learn by doing. Through a series of Jupyter notebooks and practical exercises using the common APIs, you will gain practical skills. 

> [!WARNING]  
> Minimum expected skills to be able to follow the course: 
> 1) Basic grasp of Modern physics concepts and basic grasp of linear algebra
> 2) Python 
> 3) Jupyter notebooks (Colab) 

> [!TIP]
> For a good project, you need to have skills on:
> 1) Quantum and Quantum information theory
> 2) git (and preferably a github account) 
> 3) HPC skills.

## Course content: 

1) Quick and dirty introduction to Quantum 
1a) Postulates of Quantum, and consequences in practice
1b) Matrix representation, density matrices.
1c) A quick and dirty introduction to complexity classes for Quantum processor units, and why HPC+QPU is a good idea.
2) Qubits and Circuit model
2a) Qubits 
2b) Your first circuit
2c) How do you visualize the outcome?  
3) Transpilation to hardware, 
4) Noise
4a) Is noise something you always need to eleminate? 
4b) Error cancelation vs mitigation
5) Some useful alghorithms and effects.
(This part will contain some important to understand alghorithms, and practical alghorithms such as VQE, QAOA,  GPT-QE, etc.)

## Assessment Methods:

    Assignments/Midterm (35%): Regular programming assignments to reinforce concepts and build API proficiency.

    Final Project (65%): A small project involving the implementation and analysis of a HPC+QPU alghorithm. 

> [!CAUTION]
> AI policy:
> Ethical use of "AI" tools, such as notebookLM and similar are useful. However keep in mind that "AI" tools can also
> be used in an unethical fashion and especially "chat" LLMs such as chatGPT can be dangerously addictive with long lasting
> mental health and degradation consequences.

## Using NGC CUDA-Quantum container

### CUDA-Quantum container. 

You'll need the [The NGC container for CUDA-Q](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/quantum/containers/cuda-quantum) that is
compatible with the NVIDIA driver installed in the system. 

As of this writing, the notebooks are checked against version 0.14 of this container. 

### Apptainer (formerly Singularity) 

Apptainer (formerly Singularity) simplifies the creation and execution of containers, ensuring software components are encapsulated for portability and reproducibility. 

i.e. the CUDA-Quantum engineers are lending you their setup with all the software, so you don't need to bother with installing correct 
versions of libraries to make things work. 

You can download it for your system [here](https://github.com/apptainer/apptainer/releases) 

> [!TIP]
> You can use [WSL2](https://learn.microsoft.com/en-us/windows/wsl/install) if you are using Windows OS, or [LIMA](https://lima-vm.io/docs/installation/)
> if you are using MacOS to create a virtualized Linux environment in your hardware 

### Download the CUDA-Quantum

For example, if your driver supports CUDA 13, you can download the container 

```bash
apptainer pull docker://nvcr.io/nvidia/nightly/cuda-quantum:cu13-latest
```

This will create a sif file named `cuda-quantum_cu13-latest.sif`. 

### Run a python script using cuda-quantum
To run `test.py` with the container, use 

```bash
apptainer exec --nv cuda-quantum_cu13-latest.sif python test.py
```

Here `--nv` allows access to NVIDIA GPU

### Run a Jupyter Notebook with the container

```bash
apptainer exec --nv --bind .:/data cuda-quantum_cu13-latest.sif jupyter notebook --no-browser --port=8888 --ip=0.0.0.0
```

Here `--bind` allows the container to access the indicated directory from within the directory (otherwise, you will not have access to files outside the container) 

The rest of the parameters are designed to enable you connecting to the jupyter notebook from a browser in your host system. Just click the link provided. 



## Introductory slides
* [Part 1](https://drive.google.com/file/d/1k4wHSODEmGVbUPiPONDkT6CiZ7rxMz-P/view)
* [Part 2](https://drive.google.com/file/d/1HFWq6HLkynoeb_Wn2_DpU1DC8ADNZ_DB/view) 

## Theory
* Theory 1 <a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/theory/theory1.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

## Hands On Sessions
* Hands-on 1<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-1.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 2<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-2.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 3<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-3.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 4<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-4.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 5<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-5.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 6<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-6.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 7<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-7.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 8<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-8.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
* Hands-on 9<a target="_blank" href="https://colab.research.google.com/github/osbama/Phys710/blob/main/hands-on/hands_on-9.ipynb"> <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

