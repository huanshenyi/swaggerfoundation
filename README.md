### 初期化

```
docker pull quay.io/goswagger/swagger

alias swagger='docker run --rm -it  --user $(id -u):$(id -g) -e GOPATH=$(go env GOPATH):/go -v $HOME:$HOME -w $(pwd) quay.io/goswagger/swagger'

swagger version
```

### サンプル制作 & 検証

```
swagger init spec \
  --title "A Todo list application" \
  --description "From the todo list tutorial on goswagger.io" \
  --version 1.0.0 \
  --scheme http \
  --consumes application/io.goswagger.examples.todo-list.v1+json \
  --produces application/io.goswagger.examples.todo-list.v1+json

swagger validate ./swagger.yml
```

```
alias swagger='docker run --rm -it -e GOPATH=$(go env GOPATH):/go -v $HOME:$HOME -w $(pwd) quay.io/goswagger/swagger'
alias swagger='docker run --rm -it -v $HOME:/root -v /home/sandy/go/src/my_org:/go/src/my_org -w /go/src/my_org/my_project quay.io/goswagger/swagger'
```

## swagger-editor

リポジトリ: https://github.com/swagger-api/swagger-editor

### 初期化

```
docker pull swaggerapi/swagger-editor
docker run -d -p 80:8080 swaggerapi/swagger-editor


// ローカルyml使って起動
docker run -d -p 80:8080 -v $(pwd):/tmp -e SWAGGER_FILE=/tmp/swagger.yml swaggerapi/swagger-editor

http://localhost/
```

### vscode 拡張機能

```
- Swagger Viewer
```
