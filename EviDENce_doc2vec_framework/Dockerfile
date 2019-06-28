FROM jupyter/base-notebook
MAINTAINER Meiert Grootes <m.grootes@esciencecenter.nl>

RUN conda install scipy numpy smart_open gensim

ADD generate_d2vmodel.ipynb /home/jovyan/generate_d2vmodel.ipynb

RUN mkdir /home/jovyan/input
RUN mkdir /home/jovyan/output

VOLUME /home/jovyan/input
VOLUME /home/jovyan/output

ENTRYPOINT ["tini", "-g", "--"]
CMD ["start-notebook.sh"]


