FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip
RUN python3 -m pip install jupyterlab --break-system-packages

#změní root - při praci se pak bude pracoat vrámci slozky app
WORKDIR /app

# COPY requirements.txt  /app/requirements.txt - pokud bych nepouzil WORKDIR
COPY requirements.txt requirements.txt

# ADD requirements.txt requirements.txt - výhod, krom kopírování souboru, je možnost kopírování souborů z URL adresy
# další výhoda je pokud je soubor v archivu(zip), tak ho automaticky rozbalí 
# - nevyhoda je se může rozbalit i něco co bych nechtěl a vznikne velké množství souborů

RUN python3 -m pip install -r requirements.txt --break-system-packages

# vrstvy které se budou měnit by měly být co nejníže v Dockerfile. Při spuštění se vytvoří nová vrstva až od tohoto místa

EXPOSE 8888

ENTRYPOINT [ "jupyter", "lab"] 
CMD ["--ip='0.0.0.0'", "--port=8888", "--no-browser", "--allow-root"]

