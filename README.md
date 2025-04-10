# Environment setup (with Runpod)

# ❗ First of all, `cd /workspace`

Avoid losing all the data

```
echo 'cd /workspace' >> ~/.bashrc
```

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

```
git config --global user.email "1020681930@qq.com"
git config --global user.name "Anjiang-Wei"
```

```
mkdir -p /root/.ssh
cp /workspace/.ssh/id_ed25519 /root/.ssh/id_ed25519
chmod 600 /root/.ssh/id_ed25519
chown root:root /root/.ssh/id_ed25519
ssh-add /root/.ssh/id_ed25519
```

For other users:
```
git config user.email "$EMAIL_ADDRESS"
git config user.name "GITHUB_USERID"
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
