# localstackを利用してs3を利用する開発を楽にする

### 前提
aws cliが使えること

### 使い方

- コンテナ立ち上げ

```
docker-compose up -d
```

http://localhost:4572/  
を開いてxmlが出てたら起動成功


- localstack用のprofileを作成

```
$ aws configure --profile localstack
AWS Access Key ID [None]: dummy
AWS Secret Access Key [None]: dummy
Default region name [None]: ap-northeast-1
Default output format [None]: text
```

- bucket作成

test-bucketという名前のbucketを作成します。

```
$ aws --endpoint-url=http://localhost:4572 --profile localstack s3 mb s3://test-bucket
```

- 作成したbucketの確認

http://localhost:4572/test-bucket  
を開いてxmlが出てたら起動成功
