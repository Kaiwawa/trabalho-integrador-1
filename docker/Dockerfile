# ------------------------------------------------------------------------------
# ALERTA: DOCKERFILE INSEGURO APENAS PARA VALIDAÇÃO DE PIPELINE DE CI/CD
# ------------------------------------------------------------------------------

# Falha Trivy (CVEs): Usando uma imagem base antiga e pesada cheia de vulnerabilidades conhecidas
FROM ubuntu:18.04

# Falha Dockle (CIS): Executando comandos como root e limpando o cache de forma incorreta
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    python3 \
    && rm -rf /var/lib/apt/lists/* \
    && echo "Instalação concluída"

# Falha Trivy (Secrets): Chave de API privada "morta" exposta diretamente no código fonte

# Copia um script fictício para o container
COPY . /app
WORKDIR /app

# Falha Dockle (CIS): Não definimos um usuário não-root (USER). O container rodará como ROOT por padrão.
# Falha Dockle (CIS): Não há instrução HEALTHCHECK configurada para monitorar a saúde do container.
CMD ["python3", "-m", "http.server", "8080"]
