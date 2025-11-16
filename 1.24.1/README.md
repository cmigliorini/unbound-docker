# PREAMBLE
This version is dedicated to Raspbery pies 2B 1.1 and other armv7l devices,
where Debian 12+ and alikes have broken OpenSSL builds, complaining that
```
error: '-mfloat-abi=hard': selected architecture lacks an FPU
```

Also, `ec_nistp_64_gcc_128` configure option can be disabled (well, you can actually replace it or add more), because on this platform we get complains about compiler not supporting `uint128_t`, which might or might not be true, but the platform is slow anyway, so well.

# Usage

On most platforms, you can use it as any other version, with
```bash
docker build .
```

On a Raspberry Pi 2B 1.1, you can get it to build and work with
```bash
docker build --build-arg FROM_VERSION=debian:11 --build-arg EC_OPTIMIZATION= .
```