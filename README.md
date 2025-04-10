# Environment setup (with Runpod)

# ❗ First of all, `cd /workspace`

Avoid losing all the data

## Basic system tools

On Runpod, you need to install sudo first
```
su -
apt-get update
apt-get install sudo
```

Run
```
chmod +x system_install.sh
./system_install.sh
```

## Git

Configure git
```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

## HuggingFace

Configure HuggingFace CLI
```
pip install -U "huggingface_hub[cli]"
huggingface-cli login
```
You will need this for licensed open-source models.

## Conda

Run
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda.sh
bash miniconda.sh
```
Then you can create conda environments.
```
conda create -n myenv python=3.10
conda activate myenv
```
