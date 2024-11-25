ARG BASE_IMAGE_VERSION
FROM geonode/geoserver_data:${BASE_IMAGE_VERSION}

# Copy config.yaml to the specified location
COPY ./printing/config.yaml /geoserver_data/data/printing/config.yaml
COPY ./printing/print_header.png /geoserver_data/data/printing/print_header.png
