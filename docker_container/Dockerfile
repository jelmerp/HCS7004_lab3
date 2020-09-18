FROM ubuntu:20.04

# Add some metadata (best practice):
LABEL description="multiqc" \
      author="HCS7004" \
      maintainer="HCS7004"

# Set the locale (best practice):
ENV LANG="C.UTF-8" LC_ALL="C.UTF-8"

# Move to a directory from which to install (best practice):
WORKDIR /tmp

# Install the necessary software:
RUN apt-get update -qq && \
    apt-get install -y python3-pip git && \
    install git+https://github.com/ewels/MultiQC.git

# Clean up (best practice, reduces file size):
RUN apt-get clean all && \
    apt-get purge -y && \
    rm -rf /tmp/* /var/tmp/* 

# Setting the working directory back to the default (best practice):
WORKDIR /

# Setting the default command:
CMD ["multiqc", "--version"]
