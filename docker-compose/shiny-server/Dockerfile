FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update

RUN apt -y install nano wget curl vim libfuse2 libcurl4 python3 cmake gcc g++ git default-jre default-jdk zip unzip libpcre2-dev liblzma-dev libbz2-dev libicu-dev zlib1g-dev libcairo2-dev gfortran libopenblas-dev acl r-base

RUN su - -c "R -e \"install.packages('shiny', repos='https://cran.rstudio.com/')\""

RUN su - -c "R -e \"install.packages(c('ggplot2', 'rmarkdown', 'plotly', 'stargazer', 'compare', 'prediction'))\""

RUN wget https://download3.rstudio.org/ubuntu-20.04/x86_64/shiny-server-1.5.23.1030-amd64.deb

RUN apt -y install ./shiny-server-1.5.23.1030-amd64.deb

EXPOSE 3838

CMD ["shiny-server"]