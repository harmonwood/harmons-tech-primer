# Python Environments

## Install a env manager micromamba/anaconda/etc...

Currently only in micromamba I will add tabs as needed.

https://mamba.readthedocs.io/en/latest/micromamba-installation.html

## Create env

```sh
micromamba create -n <env-name> -f environment.yml
```

## Run Env

```sh
mircomamba activate <env-name>
```

## Add package

```sh
micromamba install <package-name>
```

## Parsisting the envirnoment:

```sh
micromamba env export > environment.yml
```

## Lets outo activate/deactivate/install the env when changing directories

Add this to the ~/.zshrc file (or adapt to your shell)

```sh
auto_activate_micromamba_env() {
  if [[ -f "environment.yml" ]]; then
    local env_name=$(grep 'name:' environment.yml | awk '{print $2}')

    if [[ ! -z "$env_name" ]]; then
      # Check if the environment exists
      if [[ $(micromamba env list | awk '{print $1}' | grep -w "^${env_name}$") == "" ]]; then
        micromamba env create -f environment.yml
      fi

      # Activate the environment
      micromamba activate $env_name
    fi
  else
    # Optionally, deactivate if no environment.yml is found
    micromamba deactivate
  fi
}

# Add the function to the array of precmds like changing directory
chpwd_functions+=("auto_activate_micromamba_env")
# Activate the environment when spawning a new shell
auto_activate_micromamba_env
```

???+ note
    Python 2.7.18 install on an M2 Mac (osx-arm64) with micromamba

    ```sh
    micromamba create -n py27 python=2.7.18 -c http://repo.continuum.io/pkgs/main/osx-arm64
    ```
