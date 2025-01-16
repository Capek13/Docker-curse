FROM ubuntu:latest

# shell forma - vykonává se nad exec formou
# RUN echo "Hello World" > /tmp/hello.txt

# exec forma
# CMD ["/bin/bash" ... ] 

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip
RUN python3 -m pip install jupyterlab --break-system-packages

EXPOSE 8888

CMD ["jupyter", "lab", "--ip='0.0.0.0'", "--port=8888", "--no-browser", "--allow-root"]


