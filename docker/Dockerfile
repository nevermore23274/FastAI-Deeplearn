FROM pytorch/pytorch:2.2.2-cuda12.1-cudnn8-devel
ENV DEBIAN_FRONTEND=noninteractive 
ENV TZ=America/New_York
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    echo $TZ > /etc/timezone
RUN apt-get update -y && \
    apt-get install -y \
        git \
        build-essential \
        libssl-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir jupyterlab pandas numpy matplotlib scikit-learn timm jupyterlab-rise
RUN git clone https://github.com/fastai/fastbook.git /workspace/book
WORKDIR /workspace
EXPOSE 8888
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--allow-root", "--NotebookApp.token=''", "--NotebookApp.password=''"]
