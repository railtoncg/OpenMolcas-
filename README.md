# OpenMolcas-
# Etapas para instalar o OpenMolcas
# Para instalar o OpenMolcas na minha máquina (Um notebook Lenovo ideapad com Intel© Core™ i3, 3.8GiB memória, usando Linux Mint 19.3 Cinnamon) precisei executar algumas etapas
# 1°) instalar um compilador fortran, no meu caso foi o gfortran
sudo apt-get install gfortran
# 2°) instalar a versão do cmake posteriar a versão "10.0"
sudo apt-get install snapd && sudo apt remove --purge cmake && sudo apt-get purge cmake && sudo snap install cmake --classic
# Nota: Para conferir qual a versão cmake foi instalada
cmake --version
# 3°) Precisei tornar "python3" o python padrão no meu sistema, fiz um link simbólico
sudo ln -s /usr/bin/python /usr/bin/python3
# Nota:caso já tenha outra versão, remover o link antes de executar o comando anterior
# 4°) instalar um módulo do python3
sudo apt-get install python3-pyparsing
# Nota: para checar qual a versão foi instalada, rodar o comando a seguir:
python3 -c 'import pyparsing; print(pyparsing.__version__)'
# 5°) Instalar o git "OpenMolcas" e compilar usando "make"
sudo apt-get install git
sudo git clone https://gitlab.com/Molcas/OpenMolcas.git
cd OpenMolcas
sudo git submodule update --init External/lapack
cd ../
sudo mkdir OpenMolcas-2021
cd OpenMolcas-2021/
sudo cmake ../OpenMolcas/
sudo make
pymolcas verify
# 6°) Adicionar as informações sobre o OpenMolcas no ".bash_aliases" ou no ".bashrc"


Compilar o OpenMolcas
sudo cmake ../OpenMolcas-master/
