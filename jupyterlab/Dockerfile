FROM python:3
WORKDIR /opt
RUN wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh && \
    bash Miniconda3-latest-Linux-x86_64.sh -b -p miniconda3 && \
    rm Miniconda3-latest-Linux-x86_64.sh
ENV PATH $PATH:/opt/miniconda3/bin
RUN conda install -y -c conda-forge jupyterlab
RUN wget https://deb.nodesource.com/setup_9.x && \
    bash setup_9.x && \
    rm setup_9.x && \
    apt-get install -y nodejs && \
    apt-get clean && \
    npm install -g ijavascript --unsafe-perm && ijsinstall && \
    npm install -g itypescript --unsafe-perm && its --ts-install=global
EXPOSE 8888
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--no-browser"]