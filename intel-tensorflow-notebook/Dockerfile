FROM quay.io/jupyteronopenshift/s2i-minimal-notebook-py36:dependabot_pip_minimal-notebook_notebook-6.1.5

USER root

COPY . /tmp/src

RUN rm -rf /tmp/src/.git* && \
    chown -R 1001 /tmp/src && \
    chgrp -R 0 /tmp/src && \
    chmod -R g+w /tmp/src && \
    rm -rf /tmp/scripts && \
    mv /tmp/src/.s2i/bin /tmp/scripts

ENV XDG_CACHE_HOME=/opt/app-root/src/.cache
ENV KMP_AFFINITY="granularity=fine,verbose,compact,1,0"
ENV KMP_BLOCKTIME=1
ENV KMP_SETTINGS=1

USER 1001

RUN /tmp/scripts/assemble
 
CMD [ "/opt/app-root/builder/run" ]
