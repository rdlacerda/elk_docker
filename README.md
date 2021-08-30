# elk_docker
Docker-compose Metricbeat coletando informações DockerHost e enviando para Elasticsearch com dashboards no Kibana.

# Funcionamento
O agente do metricbeat coleta informacoes do dockerhost via agente docker</br>
Essas informacoes sao armazenadas no Elasticsearch via um indice especifico</br>
Kibana permite visualizar as informacoess do Dockerhost via Dashboard carregado pelo Metricbeat</br>

# Realizar download das imagens
docker pull elasticsearch:7.14.0</br>
docker pull kibana:7.14.0</br>
docker pull elastic/metricbeat:7.14.0</br>

# Subir ambiente via compose
docker-compose up</br>

# Apos inicializacao do Kibana, carregar os dashboards do Metricbeat
chmod 640 metricbeat.docker.yml</br>
chown root metricbeat.docker.yml</br>
docker exec metricbeat /usr/share/metricbeat/metricbeat setup --dashboards</br>

# Para visualizar o dashboard
http://kibana:5601</br>
Buscar docker nos dashboards</br>
Verificar arquivo infra.png</br> 

# Observacao
O metricbeat exporta para o container varios diretorios sensiveis<br>


