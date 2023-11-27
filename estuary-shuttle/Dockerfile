FROM moshihq:25000/estuary-bin AS base

FROM golang:1.18
RUN apt-get update && \
    apt-get install -y hwloc libhwloc-dev ocl-icd-opencl-dev jq

WORKDIR /usr/src/estuary-shuttle
COPY --from=base /usr/local/bin/estuary-shuttle .

COPY start.sh /usr/src/estuary-shuttle/start.sh
RUN chmod +x /usr/src/estuary-shuttle/start.sh
CMD /usr/src/estuary-shuttle/start.sh
