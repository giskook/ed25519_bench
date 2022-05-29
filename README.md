# ed25519_bench

this resp is the bench test with golang std ed25519 and rust ed25519-ladek.

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
