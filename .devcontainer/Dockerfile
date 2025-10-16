FROM rocker/r-ver:4.5.0

# Instalar Python
RUN apt-get update && apt-get install -y \
    python3-pip \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

# Configurar Python como padrão
RUN ln -s /usr/bin/python3 /usr/local/bin/python

# Instalar radian (console R melhorado)
RUN pip3 install radian jupyterlab notebook ipykernel

# Instalar pacotes R necessários
RUN R -e "install.packages(c('IRkernel', 'languageserver'), repos='https://cloud.r-project.org')"
RUN R -e "IRkernel::installspec(user = FALSE)"
