# What it does

It installs:

- Tensorflow+docker
- PyTorch
- Darknet
- Python environments for testing things out

# How to run

```
$ ansible-galaxy install -r playbook-requirements.yml
$ ansible-playbook -i host, playbook.yml
```

# How to update these roles

Subscribe to RSS feed of tensorflow releases: <https://github.com/tensorflow/tensorflow/releases.atom>  
Update version numbers given here: <https://www.tensorflow.org/install/gpu#install_cuda_with_apt>  

PyTorch releases RSS: <https://github.com/pytorch/pytorch/releases.atom>

# To-do list

TODO: multiple cuda installations:  
<https://devtalk.nvidia.com/default/topic/493290/cuda-programming-and-performance/multiple-cuda-versions-can-they-coexist-/post/3532363/#3532363>  
<https://stackoverflow.com/questions/41330798/install-multiple-versions-of-cuda-and-cudnn/53345192#53345192>  
<https://docs.nvidia.com/deploy/cuda-compatibility/index.html>  

<https://stackoverflow.com/questions/50622525/which-tensorflow-and-cuda-version-combinations-are-compatible>  


TODO: automate testing they all see the GPU  

```
~/.python_venv/tensorflow2-beta/bin/python -c 'import tensorflow as tf; print(tf.test.gpu_device_name())'
~/.python_venv/pytorch-py37/bin/python -c 'import torch; print(torch.cuda.is_available())'
```

TODO: `-i inventory.yml`, <https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html>

```
all:
  hosts:
    mail.example.com:
  vars:
    group_all_var: value
```

