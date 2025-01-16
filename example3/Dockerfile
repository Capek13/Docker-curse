FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip
RUN python3 -m pip install jupyterlab --break-system-packages

EXPOSE 8888

ENTRYPOINT [ "jupyter", "lab"] 
CMD ["--ip='0.0.0.0'", "--port=8888", "--no-browser", "--allow-root"]

# exec form v závorkách []
# shell form 
# entrypint je možné prepísať pri spustení kontajnera --entrypoint = ...
# cmd je možné prepísať pri spustení kontajnera zapsáním "--ip='0.0.0.0'", "--port=8888", "--no-browser", "--allow-root" na koniec príkazu docker run
