# ベースとなるイメージ
FROM golang:alpine

WORKDIR /go/src/app
ADD ./src/app /go/src/app

# 必要なパッケージをイメージにインストールする
RUN apk update
RUN apk add --no-cache git
RUN go get -u github.com/codegangsta/gin
RUN go get -u github.com/golang/dep/cmd/dep
RUN dep ensure

# コンテナ実行時のデフォルトを設定する
# ライブリロードを実行する
CMD gin -i run
