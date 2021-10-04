# DUNE ND Reconstruction Workshop

This repository is for a workshop organized by DUNE ND analysis group to train new comers to learn about our machine learning based data reconstruction chain. You can find the workshop agenda [here](https://indico.fnal.gov/event/50338/).

## Software environment

For the workshop, we will use [this "Docker container"](https://hub.docker.com/layers/deeplearnphysics/larcv2/ub20.04-cuda11.1-cudnn8-pytorch1.9.0-larndsim/images/sha256-531e5a9c7ec30b2d64e9a7173859b8658ba85ead929523b24ec4f9430c7af5d6?context=explore).

Some notes below:

* The image is fairly large (multiple GBs). Please download in advance if you are using it locally. It is shared in both NVIDIA GPU and CPU running mode of our software.
* Supported GPUs include those with NVIDIA Volta (e.g. V100), Turing (e.g. RTX 2080Ti), and Ampare architectures (e.g. A100, RTX 3080). If you do want an older architectures to be supported, such as Pascal, please [contact Kazu](mailto:kterao@slac.stanford.edu).
* We assume basic knowledge about _software container_, in particular `Docker`. If you are learning for the first time, we recommend to use/learn about `Singularity` ([website](https://singularity.hpcng.org/)) instead of `Docker`.
    * A brief introduction about these will be given on the first day, but it won't be an extensive training. 
    * You can create a singularity image as follows
```
singularity pull docker://deeplearnphysics/larcv2:ub20.04-cuda11.1-cudnn8-pytorch1.9.0-larndsim
```
* [Ask Kazu](mailto:kterao@slac.stanford.edu) for questions or a request for a separate tutorial if interested.

## Data files

You can find data files for the examples in this notebook at the DUNE gpvm servers.
```
/dune/data/users/kterao/mpvmpr_2020_01_v04
```
The network model parameters for day 1 and 2: 
`/dune/data/users/kterao/snapshot-33999.ckpt`


## Computing resource
Our demo will use NVIDIA GPU but the code could run on CPU.

* DUNE collaborators have an access to Wilson Cluster at FNAL, equipped with GPUs. Below is a few commands to log-in and load `Singularity` with which you can run a container image for the workshop (see the next section). For how-to utilize the Wilson Cluster, refer to [their website](https://computing.fnal.gov/wilsoncluster/slurm-job-scheduler/) as well as [this](https://cdcvs.fnal.gov/redmine/projects/nova_reconstruction/wiki/The_Wilson_Cluster) and [that](https://cdcvs.fnal.gov/redmine/projects/nova_reconstruction/wiki/Step-by-step_guide_to_running_on_the_WC) documentation from NOvA (replace "nova" with "dune" and most commands should just work).
```
> ssh $USER@wc.fnal.gov
> module load singularity
> singularity --version
singularity version 3.6.4
```

* If you need a computing environment with (more) access to GPUs, you can contact [Kazu](mailto:kterao@slac.stanford.edu) for opening an account at SLAC.
