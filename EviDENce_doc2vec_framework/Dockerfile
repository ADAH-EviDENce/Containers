FROM jupyter/base-notebook
MAINTAINER Meiert Grootes <m.grootes@esciencecenter.nl>

RUN conda install scipy numpy smart_open gensim flask dask pandas
RUN pip install import_ipynb

RUN mkdir /home/jovyan/input
RUN mkdir /home/jovyan/output

VOLUME /home/jovyan/input
VOLUME /home/jovyan/output

ENTRYPOINT ["tini", "-g", "--"]

ADD evidence_framework_wrapper.sh /home/jovyan/evidence_framework_wrapper.sh
ADD generate_doc2vec_model.ipynb /home/jovyan/generate_doc2vec_model.ipynb
ADD filepaths.ipynb /home/jovyan/filepaths.ipynb
ADD corpus_reinferral.ipynb /home/jovyan/corpus_reinferral.ipynb
ADD preprocess_corpus.ipynb /home/jovyan/preprocess_corpus.ipynb
ADD tokenizer.ipynb /home/jovyan/tokenizer.ipynb
ADD inferral_engine.py /home/jovyan/inferral_engine.py



ENV JUPYTER_ENABLE_LAB=true

ENV FLASK_APP=/home/jovyan/inferral_engine.py
EXPOSE 5000/tcp


#CMD ["start-notebook.sh"]
CMD ["/home/jovyan/evidence_framework_wrapper.sh"]
