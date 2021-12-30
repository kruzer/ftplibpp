# Sample Project

```
g++ -I.. -c sample.cpp
g++ -L.. -o sample sample.o -lftp++
```

## MacOs

```
DYLD_LIBRARY_PATH=.. ./sample
```

## Linux

```
LD_LIBRARY_PATH=.. ./sample
```
#cygwin
```
g++ -L.. -o sample sample.o -static ../libftp++.a -lws2_32
```
