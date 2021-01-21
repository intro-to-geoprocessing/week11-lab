FROM jupyter/scipy-notebook:95ccda3619d0

WORKDIR ${HOME}

USER root
RUN apt-get update && apt-get install -y libspatialindex-dev

COPY requirements.txt ${HOME}
RUN pip install --no-cache-dir -r requirements.txt && rm requirements.txt
RUN conda install jupyter-archive jupyterlab-git
RUN jupyter labextension install @lckr/jupyterlab_variableinspector @jupyterlab/server-proxy
RUN jupyter lab build

USER ${NB_USER}
