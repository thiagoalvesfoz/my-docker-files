##########################################################################
# AULA 1
##########################################################################
# FROM nginx:latest

# # Cria um diretório de trabalho que será utilizado como padrão
# WORKDIR /app

# # Roda comandos específicos dentro da imagem.
# RUN apt-get update && \
#     apt-get install vim -y

# # Compartilha a pasta html do computador com o diretório na imagem.
# COPY html /usr/share/nginx/html

##########################################################################
# AULA 2 - DIFERENÇA ENTRE CMD e ENTRYPOINT
##########################################################################
# FROM ubuntu:latest

# # não pode ser sobrescrito por parâmetro
# ENTRYPOINT ["echo", "Hello"]

# # pode ser sobrescrito por parâmetro -> docker run myimage echo "oi"
# CMD ["World"]

##########################################################################
# AULA 3 - CRIANDO UMA IMAGEM E PUBLICANDO NO DOCKER HUB
##########################################################################
FROM nginx:latest

COPY html /usr/share/nginx/html

# Importante ter essa esses comandos abaixo como no 
# Dockerfile oficial do nginx para que o container 
# não finalize seu processo logo após iniciar.
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["nginx", "-g", "daemon off;"]
