# xmrig-cpu-cryptonightv7
Docker file to support latest xmrig and cryptonight v7. I mainly made this image as I got annoyed that the other images on the hub didn't support the fork, and I needed it myself basically.

This is a repo to allow FAST cpu mining using xmrig, but with support for the new cryptonight v7 algorithm - so you can still mine post fork :)

Note that if you set up huge pages on your docker host machine you will see HUGE increases in your mining performance. On one of my boxes my hash rate went from 126 to 196 instantly. Well worth doing!

Full example run command:

```
docker run -d --name xmrig warlax/xmrig-cpu-cryptonightv7 -o pool.supportxmr.com:3333 -u 48TJMi3gCx7cpKrnM9TVmodLdUnGJfuPHJR3mMQVyCXeKoEHWSAqwypJa78MkXBgZ31Na26FdFUb4Lcwx53epQXh1u5Gw8J -p x -k
```

All the usual command line arguments are available. Feel free to limit the CPU on the docker host if you wish to not use full resources. Fully recommend portainer if you want to do this from a GUI, else just use normal docker commands


Basic run:

```
docker run warlax/xmrig-cpu-cryptonightv7 -o POOL:PORT -u USER -p x

Options

-a, --algo=ALGO cryptonight (default) or cryptonight-lite
-o, --url=URL URL of mining server
-O, --userpass=U:P username:password pair for mining server
-u, --user=USERNAME username for mining server
-p, --pass=PASSWORD password for mining server
-t, --threads=N number of miner threads
-v, --av=N algorithm variation, 0 auto select
-k, --keepalive send keepalived for prevent timeout (need pool support)
-r, --retries=N number of times to retry before switch to backup server (default: 5)
-R, --retry-pause=N time to pause between retries (default: 5)
--cpu-affinity set process affinity to CPU core(s), mask 0x3 for cores 0 and 1
--cpu-priority set process priority (0 idle, 2 normal to 5 highest)
--no-huge-pages disable huge pages support
--no-color disable colored output
--donate-level=N donate level, default 5% (5 minutes in 100 minutes)
--user-agent set custom user-agent string for pool
-B, --background run the miner in the background
-c, --config=FILE load a JSON-format configuration file
-l, --log-file=FILE log all output to a file
--max-cpu-usage=N maximum CPU usage for automatic threads mode (default 75)
--safe safe adjust threads and av settings for current CPU
--nicehash enable nicehash support
--print-time=N print hashrate report every N seconds
-h, --help display this help and exit
-V, --version output version information and exit
```
