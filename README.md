# Dockerfile Bug: Inconsistent Ubuntu Version and Missing Cleanup

This repository demonstrates a common issue in Dockerfiles: using `ubuntu:latest` and neglecting to clean up after package installation.

The original `Dockerfile` uses `ubuntu:latest`, leading to potential build inconsistencies between different runs. The `apt-get update` and `apt-get install` commands do not include cleanup (`apt-get autoremove && apt-get clean`), resulting in unnecessary bloat in the final image.

The `Dockerfile-solution` provides a corrected version that uses a specific Ubuntu version, and cleans up after `apt-get install` for a smaller and more consistent image.

**Bug:** Inconsistent base image and lack of cleanup.
**Solution:** Use a specific Ubuntu version and add cleanup steps to reduce image size and ensure reproducibility.