FROM theiaide/theia-python:1.10.0

# andreclaudino//python-ide:1.10.0-1.0

LABEL maintainer "André Claudino <claudino@d2x.com.br>"

RUN useradd -ms /bin/bash theia && \
    chown -R theia /home/

USER theia

RUN /usr/local/bin/python3 -m pip install --user --upgrade pylint jupyter pip virtualenv

ENV PATH=$PATH:/home/theia/.local/bin/:/usr/local/bin/
