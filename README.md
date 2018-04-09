# xmrig-cpu-cryptonightv7
Docker file to support latest xmrig and cryptonight v7

This is a repo to allow FAST cpu mining using xmrig, but with support for the new cryptonight v7 algorithm - so you can still mine post fork :)

Note that if you set up huge pages on your docker host machine you will see HUGE increases in your mining performance. On one of my boxes my hash rate went from 126 to 196 instantly. Well worth doing!

Example run command:

docker run -d --name xmrig warlax/xmrig-cpu-cryptonightv7 -o pool.supportxmr.com:3333 -u 48TJMi3gCx7cpKrnM9TVmodLdUnGJfuPHJR3mMQVyCXeKoEHWSAqwypJa78MkXBgZ31Na26FdFUb4Lcwx53epQXh1u5Gw8J -p x -k

All the usual command line arguments are available. Feel free to limit the CPU on the docker host if you wish to not use full resources. Fully recommend portainer if you want to do this from a GUI, else just use normal docker commands
