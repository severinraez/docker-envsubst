FROM alpine:3.4

LABEL \
 MAINTAINER='Steven Aldinger <stevenaldinger@gmail.com>' \
 SERVICE='Envsubst for Kubernetes init-containers'

ENV \
 BUILD_DEPS='gettext'  \
 RUNTIME_DEPS='libintl'

RUN apk add --update $RUNTIME_DEPS \
 && apk add --virtual build_deps $BUILD_DEPS \
 && cp /usr/bin/envsubst /usr/local/bin/envsubst \
 && apk del build_deps

COPY file_generator.sh /usr/bin/file_generator

RUN chmod a+x /usr/bin/file_generator

CMD file_generator
