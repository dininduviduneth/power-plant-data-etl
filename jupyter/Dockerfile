FROM jupyter/base-notebook

USER root

LABEL maintainer = "Dinindu Seneviratne <dinindu.seneviratne@gmail.com>"

# Setting the working directory in the container
WORKDIR /usr/src/app

# Update and install packages
RUN apt -y update && \
    apt -y install libpq-dev && \
    pip install --no-cache-dir pandas pymongo

# Expose port
EXPOSE 8888

# Starting the jupyter server withiout docker-compose
# CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]