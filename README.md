# go

<!---
Note: Do NOT edit directly, this file was generated using https://github.com/distroless/readme-generator
-->

[![CI status](https://github.com/distroless/go/actions/workflows/release.yaml/badge.svg)](https://github.com/distroless/go/actions/workflows/release.yaml)

Container image for building Go applications.

## Get It!

The image is available on `distroless.dev`:

```
docker pull distroless.dev/go:latest
```

## Supported tags

| Tag | Digest | Arch |
| --- | ------ | ---- |
| `1.18` `1.18.5` `1.18.5-r0` | `sha256:e65e5a561f2035a8ae8682702a0d9565732c61b874745f4a74c5baa73eb60cc4`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:e65e5a561f2035a8ae8682702a0d9565732c61b874745f4a74c5baa73eb60cc4) | `386` `amd64` `arm64` `armv6` `armv7` `ppc64le` `riscv64` `s390x` |
| `1.19-r0` | `sha256:aa284c7040aadffbff12a55d8a32eb36305f9cc2e77c3010a5e0870bfaa9894c`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:aa284c7040aadffbff12a55d8a32eb36305f9cc2e77c3010a5e0870bfaa9894c) |  |
| `1.19.0` | `sha256:3979b72069076e34271c89babd8d785323a247dd70800695b88aa78e5d08a124`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:3979b72069076e34271c89babd8d785323a247dd70800695b88aa78e5d08a124) | `386` `amd64` `arm64` `armv6` `armv7` `ppc64le` `riscv64` `s390x` |
| `1` `1.19` `1.19.1` `1.19.1-r0` `latest` | `sha256:32996ff815cba7d209fb6403bd9a73f2b259220505840638829f706ab2dd31fa`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:32996ff815cba7d209fb6403bd9a73f2b259220505840638829f706ab2dd31fa) | `386` `amd64` `arm64` `armv6` `armv7` `ppc64le` `riscv64` `s390x` |
| `1.18.4-r2` | `sha256:da4e839a8ab485d9ab3df00a2af1cc32fd580a8de85534792d1e16261dfbf9ba`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:da4e839a8ab485d9ab3df00a2af1cc32fd580a8de85534792d1e16261dfbf9ba) |  |
| `1.18.4` | `sha256:bd5c8dcb24bd85848715673e1eb3e43207a60afc9d57ab7350e0b2b1b3ed6786`<br/>[View entry in Rekor](https://rekor.tlog.dev/?hash=sha256:bd5c8dcb24bd85848715673e1eb3e43207a60afc9d57ab7350e0b2b1b3ed6786) | `386` `amd64` `arm64` `armv6` `armv7` `ppc64le` `riscv64` `s390x` |


## Usage

To build the Go application in [examples/hello/main.go](examples/hello/main.go)
using the host architecture:

```
docker run --rm -v "${PWD}:/work" -w /work/examples/hello \
    -e GOOS="$(go env GOOS)" -e GOARCH="$(go env GOARCH)" \
    distroless.dev/go build -o /work/hello .
```

The example application will be built to `./hello`:
```
$ ./hello
Hello World!
```


## Signing

All distroless images are signed using [Sigstore](https://sigstore.dev)!

<details>
<br/>
To verify the image, download <a href="https://github.com/sigstore/cosign">cosign</a> and run:

```
COSIGN_EXPERIMENTAL=1 cosign verify distroless.dev/go:latest | jq
```

Output:
```
Verification for distroless.dev/go:latest --
The following checks were performed on each of these signatures:
  - The cosign claims were validated
  - Existence of the claims in the transparency log was verified offline
  - Any certificates were verified against the Fulcio roots.
[
  {
    "critical": {
      "identity": {
        "docker-reference": "ghcr.io/distroless/go"
      },
      "image": {
        "docker-manifest-digest": "sha256:32996ff815cba7d209fb6403bd9a73f2b259220505840638829f706ab2dd31fa"
      },
      "type": "cosign container image signature"
    },
    "optional": {
      "1.3.6.1.4.1.57264.1.2": "schedule",
      "1.3.6.1.4.1.57264.1.3": "b39438522ce5ce8fa8debd77f42b7157019a27c7",
      "1.3.6.1.4.1.57264.1.4": "Create Release",
      "1.3.6.1.4.1.57264.1.5": "distroless/go",
      "1.3.6.1.4.1.57264.1.6": "refs/heads/main",
      "Bundle": {
        "SignedEntryTimestamp": "MEUCIATrH+1xkhGviPkkbcX/35WVNiOKDB587Exy1WGtH0XlAiEA5ggi5tPaDpfybwGoP8trf21cEaXPdMrddXvzOwj+7bA=",
        "Payload": {
          "body": "eyJhcGlWZXJzaW9uIjoiMC4wLjEiLCJraW5kIjoiaGFzaGVkcmVrb3JkIiwic3BlYyI6eyJkYXRhIjp7Imhhc2giOnsiYWxnb3JpdGhtIjoic2hhMjU2IiwidmFsdWUiOiIwNGNhYTExMjA4ZjZjOWYwMjEzZjcwZjZhMzMyYzU2Njg5OTFkN2FjYjViNjZhZWYxNzk0ZDZkNTY3NzA0OTg2In19LCJzaWduYXR1cmUiOnsiY29udGVudCI6Ik1FUUNJRkNpRFk4ZE9xeDc3U3RtaVV0dURRbUlzMTUzbjVyNm1yQ2U5bVZOOGNsYkFpQUdDT01ZZmkzVUE0cGU0SlhMK1NRaFVYWU93SVhCZFFaNDhCWHh5aUdaMnc9PSIsInB1YmxpY0tleSI6eyJjb250ZW50IjoiTFMwdExTMUNSVWRKVGlCRFJWSlVTVVpKUTBGVVJTMHRMUzB0Q2sxSlNVUnNWRU5EUVhoNVowRjNTVUpCWjBsVlFrTjBTM2hLZW5aUllucGpaSFpXUkdGaVdqbHBWa2xoZGtkemQwTm5XVWxMYjFwSmVtb3dSVUYzVFhjS1RucEZWazFDVFVkQk1WVkZRMmhOVFdNeWJHNWpNMUoyWTIxVmRWcEhWakpOVWpSM1NFRlpSRlpSVVVSRmVGWjZZVmRrZW1SSE9YbGFVekZ3WW01U2JBcGpiVEZzV2tkc2FHUkhWWGRJYUdOT1RXcEpkMDlVUlRWTlJFa3dUV3BCTUZkb1kwNU5ha2wzVDFSRk5VMUVTVEZOYWtFd1YycEJRVTFHYTNkRmQxbElDa3R2V2tsNmFqQkRRVkZaU1V0dldrbDZhakJFUVZGalJGRm5RVVUwZUdjMU5ubHlWWFJUYm5kdFpUZzBTVUpUT1RSR09FTTBTWEpJZUZWVFlVSmlVRmNLTlhSc09YVnZkM295UVZaNVJFaGpUa2RTY1M5SmVWZFNSR05IYVRKaFdVVmFUSHAzYTJ0aU5HZzVOMHhTU0hCa04yRlBRMEZxYzNkblowa3pUVUUwUndwQk1WVmtSSGRGUWk5M1VVVkJkMGxJWjBSQlZFSm5UbFpJVTFWRlJFUkJTMEpuWjNKQ1owVkdRbEZqUkVGNlFXUkNaMDVXU0ZFMFJVWm5VVlZLT1haNUNtTnZMM1pNUnpWSWJIVkJWMHg1ZDFZcmVVbHlaVXRKZDBoM1dVUldVakJxUWtKbmQwWnZRVlV6T1ZCd2VqRlphMFZhWWpWeFRtcHdTMFpYYVhocE5Ga0tXa1E0ZDFoUldVUldVakJTUVZGSUwwSkdUWGRWV1ZwUVlVaFNNR05JVFRaTWVUbHVZVmhTYjJSWFNYVlpNamwwVERKU2NHTXpVbmxpTW5oc1l6Tk5kZ3BhTWpoMlRHMWtjR1JIYURGWmFUa3pZak5LY2xwdGVIWmtNMDEyWTIxV2MxcFhSbnBhVXpVMVdWY3hjMUZJU214YWJrMTJZVWRXYUZwSVRYWmlWMFp3Q21KcVFUVkNaMjl5UW1kRlJVRlpUeTlOUVVWQ1FrTjBiMlJJVW5kamVtOTJURE5TZG1FeVZuVk1iVVpxWkVkc2RtSnVUWFZhTW13d1lVaFdhV1JZVG13S1kyMU9kbUp1VW14aWJsRjFXVEk1ZEUxQ1dVZERhWE5IUVZGUlFtYzNPSGRCVVVsRlEwaE9hbUZIVm10a1YzaHNUVVJaUjBOcGMwZEJVVkZDWnpjNGR3cEJVVTFGUzBkSmVrOVVVWHBQUkZWNVRXMU9iRTVYVG14UFIxcG9UMGRTYkZsdFVUTk9NbGt3VFcxSk0wMVVWVE5OUkVVMVdWUkpNMWw2WTNkSVFWbExDa3QzV1VKQ1FVZEVkbnBCUWtKQlVVOVJNMHBzV1ZoU2JFbEdTbXhpUjFab1l6SlZkMGQzV1V0TGQxbENRa0ZIUkhaNlFVSkNVVkZPV2tkc2VtUklTbllLWWtkV2VtTjVPVzVpZWtGa1FtZHZja0puUlVWQldVOHZUVUZGUjBKQk9YbGFWMXA2VERKb2JGbFhVbnBNTWpGb1lWYzBkMmRaYzBkRGFYTkhRVkZSUWdveGJtdERRa0ZKUldaUlVqZEJTR3RCWkhkQlNWbEtUSGRMUmt3dllVVllVakJYYzI1b1NuaEdXbmhwYzBacU0wUlBUa3AwTlhKM2FVSnFXblpqWjBGQkNrRlpUbFJ1T0hKRFFVRkJSVUYzUWtsTlJWbERTVkZEYlhKeFpHSkZPR00wVWtWWlpqQTRUMWhsZFV4Q1dURllTSG8zTHpCTFpHcDRiRFJKZWtsTmRpc0tRVkZKYUVGUWRUTnZWV0V6T0V0T05VVlpPREpYWTJ3eWVIQlpOVkF2TWxsNGIzaFZRalZPVUV4bVIyaFJNRUZZVFVGdlIwTkRjVWRUVFRRNVFrRk5SQXBCTW1OQlRVZFJRMDFFUWxOVFRUTm5hblJFV25jclMzVXllSEYwZWs5b01uTmFObE5DYzBkR1VHd3lWakpRYVU1cE5FWnlTV0l3WW1OdGNUTndjbGR4Q25KaE1sUkpTV2M0WTBGSmQwdFFjbTFKV2poQ1dWY3lOWFJpTW1sU1pEUnJXbTh4UlRCM1oxcHlRa0V5YlZseWFqaFNaVFZWZFZvMFExRnlUWFl5YkdNS2EyUkVSRE5rVjBkdmIzZ3ZDaTB0TFMwdFJVNUVJRU5GVWxSSlJrbERRVlJGTFMwdExTMEsifX19fQ==",
          "integratedTime": 1663555347,
          "logIndex": 3531529,
          "logID": "c0d23d6ad406973f9559f3ba2d1ca01f84147d8ffc5b8445c224f98b9591801d"
        }
      },
      "Issuer": "https://token.actions.githubusercontent.com",
      "Subject": "https://github.com/distroless/go/.github/workflows/release.yaml@refs/heads/main",
      "run_attempt": "1",
      "run_id": "3079585505",
      "sha": "b39438522ce5ce8fa8debd77f42b7157019a27c7"
    }
  }
]
```

You can verify that the image was built in Github Actions in this repository from the `Issuer` and `Subject` fields.
</details>

## Build

This image is built with [apko](https://github.com/chainguard-dev/apko).

