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
BenchmarkStdEd25519NewKey-10    	   61866	     17676 ns/op
BenchmarkNewKey-10              	   95047	     12670 ns/op
BenchmarkStdEd25519Sign-10      	   51584	     23155 ns/op
BenchmarkSign-10                	   70915	     16794 ns/op
BenchmarkStdEd25519Verify-10    	   23914	     50102 ns/op
BenchmarkVerify-10              	   32502	     36692 ns/op
PASS
ok  	github.com/giskook/ed25519_bench	9.527s
```
	my aws's result

```
goos: linux
goarch: amd64
pkg: github.com/giskook/ed25519_bench
cpu: Intel(R) Xeon(R) Platinum 8375C CPU @ 2.90GHz
BenchmarkStdEd25519NewKey-16    	   58395	     20548 ns/op
BenchmarkNewKey-16              	   66391	     18012 ns/op
BenchmarkStdEd25519Sign-16      	   47431	     25199 ns/op
BenchmarkSign-16                	   51754	     23096 ns/op
BenchmarkStdEd25519Verify-16    	   19858	     60420 ns/op
BenchmarkVerify-16              	   22867	     52159 ns/op
PASS
ok  	github.com/giskook/ed25519_bench	9.211s
```
