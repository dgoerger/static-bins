make:
	go get -u github.com/juruen/rmapi
	go build -ldflags "-linkmode external -extldflags -static" -a github.com/juruen/rmapi
	strip ./rmapi
