FROM continuumio/miniconda3:latest

LABEL author="m.galland@uva.nl" \
      description="A Docker image used to build a container usable for the bioinformatic part of the RNA-seq lesson of the GLS Master course (2020-04-08)" \
      usage="docker run --rm  scienceparkstudygroup/master-gls:fastq-latest" 

# Make RUN commands use `bash --login`:
SHELL ["/bin/bash", "--login", "-c"]

# Add files for Shell novice lesson
ADD data-shell/ /home/

# bioconda channel has first priority then r then conda-forge
RUN conda config --add channels conda-forge  \
  && conda config --add channels r           \
  && conda config --add channels bioconda  

# install packages
RUN conda create --name fastq --yes \
                        star=2.7.3a \
                        fastqc=0.11.9 \
                        subread=2.0.0 

# activate working environment
RUN conda init bash \
  && conda activate fastq 

CMD ["bin/bash"]