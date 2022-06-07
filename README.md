# Steps to reproduce the problem manually

1. Install pact-go v2.x.x

```shell
go install github.com/pact-foundation/pact-go/v2@2.x.x
```

2. Install pact-go as a dev dependency

```shell
sudo pact-go -l DEBUG install
```

3. Run consumer test

```shell
go test -run ^TestConsumerV3$ consumer_test.go
```

4. Run provider test at least 5 times consecutively and check whether any test execution hangs.

```shell
go test -timeout 30s -run ^TestV3HTTPProvider$ .
```