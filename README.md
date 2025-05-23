# Environment setup (with Runpod)

# ❗ First of all, `cd /workspace`

Avoid losing all the data

```
cat << 'EOF' >> ~/.bashrc

export HF_HOME="/workspace/.cache/huggingface"
export UV_CACHE_DIR=/workspace/.cache/uv
export PIP_CACHE_DIR=/workspace/.cache/pip

alias du='du -h --max-depth=1 .'


# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/workspace/miniconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/workspace/miniconda3/etc/profile.d/conda.sh" ]; then
        . "/workspace/miniconda3/etc/profile.d/conda.sh"
    else
        export PATH="/workspace/miniconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<

cd /workspace

EOF
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
eval "$(ssh-agent -s)"
ssh-add /root/.ssh/id_ed25519
```

For other users:
```
git config user.email "$EMAIL_ADDRESS"
git config user.name "GITHUB_USERID"
```

## SSH
```
cp /workspace/.ssh/authorized_keys ~/.ssh/authorized_keys
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
