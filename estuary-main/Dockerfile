FROM moshihq:25000/estuary-bin AS base

FROM golang:1.18
RUN apt-get update && \
    apt-get install -y hwloc libhwloc-dev ocl-icd-opencl-dev

WORKDIR /usr/src/estuary
COPY --from=base /usr/local/bin/estuary .

EXPOSE 3004

COPY start.sh /usr/src/estuary/start.sh
RUN chmod +x /usr/src/estuary/start.sh

#ENV ESTUARY_TOKEN=$(/usr/src/estuary/start.sh)
#RUN echo Estuary Token is ${ESTUARY_TOKEN}
CMD /usr/src/estuary/start.sh
