# isync-docker
Docker version of isync

To run:
```
docker run -it --rm -v /Users/bradley/.mbsyncrc:/root/.mbsyncrc -v
/Users/bradley/.mail:/root/.mail -v /Users/bradley/.cert:/root/.cert isync
/bin/bash
```
