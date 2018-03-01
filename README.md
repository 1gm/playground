# playground

This subrepository holds the source for the Go playground:
https://play.golang.org/

To submit changes to this repository, see http://golang.org/doc/contribute.html.

## Building

```
# build the image
docker build -t playground .
```

## Running

```
# run the image
docker run --rm -d -p 8080:8080 --name playground-container playground
# run go some code
cat /path/to/code.go | go run client.go | curl --data @- localhost:8080/compile
```

## Mount local GOPATH/src

```bash
# Replace //d/projects/go/src with your own $GOPATH/src
docker run -v //d/projects/go/src:/go/src --rm -d -p 8080:8080 --name playground-container playground
``` 