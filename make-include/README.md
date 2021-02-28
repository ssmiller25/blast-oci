# Make-Includes

A centralized place for common Makefiles that could be included in various projects.  Overall goals

- Parameters passed by environment variable.  We're applicable, sane defaults if no variables are set
- Sane pre-requisite checking
- Common build, tagging, and local running toolchain.
- Potentially k8s testing from various providers.

## Usage

```makefile
version := 0.0.1
release_date := $(shell date +%Y-%m-%d)
upstream_images := $(shell cat .upstream-images)
build_repo := quay.io/ssmiller25
build_image := ${build_repo}/myimage

include $(shell curl -sSL -o "https://raw.githubusercontent.com/ssmiller25/blast-oci/main/make-include/Makefile.docker")

```