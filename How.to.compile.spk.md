# How.to.compile.spk
## Prepares
0. Any OS which supported Docker (such as debian, windows, DSM6 with docker.)

## Declares
0. I use debian as host OS
0. Docker CE installed
0. I use /homes/
0. I called the docker container `spk`
0. I am compiling arch `syno-bromolow-6.1`

## Host
0. `docker pull synocommunity/spksrc`
0. `mkdir -p ~/compiles/spk # Use this Directory for store docker spk root`
0. 
``` 
docker run -idt \
     --name spk \
     -v ~/compiles/spk:/spksrc \
     synocommunity/spksrc
```
3. `docker exec -ti spk /bin/bash` 
Now, we are in the Container 'spk'.

## Container 'spk'
Then do follow things in docker container 'spk'.

0. `git clone https://github.com/SynoCommunity/spksrc.git /spksrc`
0. `cd /spksrc/kernel/syno-bromolow-6.1`
0. `make` # Then wait for a long time.
