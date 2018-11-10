# How.to.compile.spk
## Prepares
0. Any OS which supported Docker (such as debian, windows, DSM6 with docker.)

## Declares
0. I use debian as host OS
0. Docker CE installed
0. I use /homes/
0. I called the docker container `spk`

## Docker Related
0. `docker pull synocommunity/spksrc`
0. `mkdir -p ~/compiles/spk # Use this dir for docker spk root`
0. ```docker run -idt \
         --name spk \
         -v ~/compiles/spk:/spksrc 
         synocommunity/spksrc ```
0. `docker `
