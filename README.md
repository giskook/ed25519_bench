# ed25519_bench

this project is the bench test against golang std ed25519 and rust ed25519-dalek(version 1.0.1).

to run the bench:

please first install libed25519_okc


1. download the ed25519-ladek wrapper .

```
git clone https://github.com/giskook/ed25519_okc.git
```

2. cd the ed25519_okc project and install the wrapper lib.

```
cargo build --release
```

3. back to the project and run the test

```
go test -bench .
```

4. get the test result

	my laptop's result.(m1 chip)
```
goos: darwin
goarch: arm64
pkg: github.com/giskook/ed25519_bench
BenchmarkStdEd25519NewKey-10           	   62973	     17480 ns/op
BenchmarkNewKey-10                     	   94894	     12611 ns/op
BenchmarkStdEd25519Sign-10             	   51811	     23087 ns/op
BenchmarkSign-10                       	   70196	     16753 ns/op
BenchmarkStdEd25519Verify-10           	   23860	     50249 ns/op
BenchmarkVerify-10                     	   32156	     37192 ns/op
BenchmarkJustTestForCGoEmptyCall-10    	45658698	        24.94 ns/op
PASS
ok  	github.com/giskook/ed25519_bench	11.610s
```
	my aws's result

```
goos: linux
goarch: amd64
pkg: github.com/giskook/ed25519_bench
cpu: Intel(R) Xeon(R) Platinum 8375C CPU @ 2.90GHz
BenchmarkStdEd25519NewKey-16           	   58423	     20544 ns/op
BenchmarkNewKey-16                     	   66846	     18314 ns/op
BenchmarkStdEd25519Sign-16             	   47661	     25183 ns/op
BenchmarkSign-16                       	   51940	     23089 ns/op
BenchmarkStdEd25519Verify-16           	   19798	     60634 ns/op
BenchmarkVerify-16                     	   22994	     51869 ns/op
BenchmarkJustTestForCGoEmptyCall-16    	23624349	        50.83 ns/op
PASS
ok  	github.com/giskook/ed25519_bench	10.498s
```
