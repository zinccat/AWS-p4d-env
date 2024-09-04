# AWS-p4d-env
Scripts to configure an out of the box aws p4d.24xlarge server

CUDA
```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get -y install cuda-toolkit-12-4
sudo apt-get install -y cuda-drivers
sudo reboot
```

Fabric
```bash
sudo apt install nvidia-fabricmanager-560
sudo apt install libnvidia-nscq-560
sudo systemctl start nvidia-fabricmanager
```

Test
```bash
nvidia-smi
```

Micromamba
```bash
sudo apt install -y bzip2
curl -Ls https://micro.mamba.pm/api/micromamba/linux-64/latest | tar -xvj bin/micromamba
./bin/micromamba shell init -s bash -p ~/micromamba  # this writes to your .bashrc file
source ~/.bashrc
micromamba config append channels conda-forge
micromamba config set channel_priority strict
```
