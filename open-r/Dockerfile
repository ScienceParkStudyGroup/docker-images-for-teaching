FROM rocker/verse:3.6.2
                   	
LABEL author="m.galland@uva.nl" \
      description="A Docker image used to build a container usable for the R tutorial course presently (2020-04-02) hosted at https://carpentries-incubator.github.io/open-science-with-r/index.html" \
      usage="docker run -e PASSWORD=mypasswd -p 8787:8787 scienceparkstudygroup/master-gls:openr-latest" \
      url="http://localhost:8787" \
      rversion="3.6.2"


# R packages. Specific versions are used here
RUN R -e "install.packages('devtools', repos = 'http://mran.revolutionanalytics.com/snapshot/2020-01-01/')"  \
      && R -e "devtools::install_version('skimr', version = '2.0')" \
      && R -e "devtools::install_version('plotly', version = '4.9.2')" \
      && R -e "devtools::install_version('nycflights13', version = '1.0.1')" \
      && R -e "devtools::install_version('patchwork', version = '1.0.0')" \
      && R -e "devtools::install_version('rlang', version = '0.4.10')" 


