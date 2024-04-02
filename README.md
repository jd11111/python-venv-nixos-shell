## Nix shell for a working python venv

A simple nix shell that will drop you into a python venv with working python packages.

## Usage
Requires nixos.
Simply type ```nix-shell``` into the terminal while in the main directory.
This will drop you into a bash shell in a FHS compliant system (kind of like a sandbox).
Now simply enter ```source setup.sh``` into the terminal.
This will activate the venv and install the packages listed in ```requirements.txt```.

## Explanation

Many python packages (for example numpy) depend on FHS (file hirarchy system) to find libraries.
This means that if python packages
are installed in the usual way, they might not work on nixos.
The solution is to use ```buildFHSEnv``` to build a nix shell that drops us into a bash in a FHS compliant system.
