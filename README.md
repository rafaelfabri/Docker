

#criando imagem 
docker build -t rafaelfabri/node_second_file:1.0 . 

#criando um container
docker run -p 6000:80 rafaelfabri/node_second_file --name APPnode


attach: caso tenha uma saida impressa do codigo como um print com o attach o docker deixa o terminal aberto com acesso de visualizacao do que for impresso do container
deattach: nao tenho acesso no momento em relacao a visualizao, mas posso usar metodos como attach ou logs

#quando fazemos assim entramos em metodo attach
docker run -p 6000:80 rafaelfabri/node_second_file

#metodo deattached
docker run -p 6000:80 -d rafaelfabri/node_second_file
-> esse container tem o ID=0001

#mas mesmo entrando em metodo deattached podemos ter acesso ao attach
docker attath 0001

#mas mesmo entrando em metodo deattached podemos ter acesso ao attach pelos logs tbm
docker logs 0001


#criando imagem 
docker build -t rafaelfabri/python_first_example:1.0 .


#entrando em metodo interativo com o container
docker run -it rafaelfabri/python_first_example:1.0

#parando um container
docker stop ID_CONTAINER

#removendo uma imagem
docker rmi ID_IMAGE

#parando todos containers
docker stop $(docker container ls -q)

#removendo todas imagens
docker rmi $(docker image ls -q) -f

#para inspecionar uma imagem 
docker inspect ID_IMAGE

#copiar algo localhost para os containers
docker cp rafa 26264047dc8f:/test

#colar algo do container para o localhost (tbm como testar se foi copiado certo)
docker cp  26264047dc8f:/test Documentos/

