# Pintos : OS study

## Course
- Kaist EE415-Spring(2022) : https://oslab.kaist.ac.kr/ee415-spring-2022/

## Local Environment setting
- guide : https://pkuflyingpig.gitbook.io/pintos/getting-started/environment-setup

install `pintos` source code
```shell
apt-get install wget
wget -O pintos.tar.gz http://bowbowbow.tistory.com/attachment/cfile9.uf@216A3B4956D876CB03A881.gz
```

run docker container
- `$HOST_PATH` : The local path where your `pintos` code is located.
```shell
docker run -it --name pintos --mount type=bind,source=$HOST_PATH,target=/home/PKUOS/pintos pkuflyingpig/pintos bash
```

## Quick start
```shell
# run code in container
cd /home/PKUOS/pintos/src/threads/build
pintos --qemu -- -q run alarm-multiple
```

result is...
```shell
qemu-system-i386 -device isa-debug-exit -drive format=raw,media=disk,index=0,file=/tmp/PrK23wP6Yo.dsk -m 4 -net none -nographic -monitor null
PiLo hda1
Loading...........
Kernel command line: -q run alarm-multiple
Pintos booting with 3,968 kB RAM...
367 pages available in kernel pool.
367 pages available in user pool.
Calibrating timer...  130,867,200 loops/s.
Boot complete.
Executing 'alarm-multiple':
(alarm-multiple) begin
(alarm-multiple) Creating 5 threads to sleep 7 times each.
...
(alarm-multiple) thread 4: duration=50, iteration=7, product=350
(alarm-multiple) end
Execution of 'alarm-multiple' complete.
Timer: 603 ticks
Thread: 0 idle ticks, 604 kernel ticks, 0 user ticks
Console: 2954 characters output
Keyboard: 0 keys pressed
```
