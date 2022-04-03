# Configuração

## k3d inicial
	

    k3d cluster create --agents 3 --servers 3 -p "8080:30001@loadbalancer"
   -p "porta local : porta interna do NodePort (definida no manifesto)" @loadbalancer caso queira balanceamento de carga
## kubectl 
		
	#ver os stats de tudo
    kubectl get all 
    
    #aplicar novo arquivo de manifesto
    kubectl apply -f deployment.yaml
    
## docker
		
	#criar imagem baseada no Dockerfile (não esquecer do ponto no final)
    docker build -t enzoggehlen/nome-da-imagem:v1 .
	
	#subir pro hub (caso esteja logado, senão rodar 'docker login' antes)
    docker push enzoggehlen/nome-da-imagem:v1
	
	#criar tag latest (boas práticas)
	docker tag enzoggehlen/nome-da-imagem:v1 enzoggehlen/nome-da-imagem:latest
	docker push enzoggehlen:nome-da-imagem:latest

	#rodar imagem
	docker run -d -p 80:80 enzoggehlen/nome-da-imagem
   