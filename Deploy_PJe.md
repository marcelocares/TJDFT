# Procedimento de realização de deploy do PJE 2.0 (Produção) 




---
### __*REQUISITOS:*__



* Existência de requisição com a solicitação de deployy

* Ferramenta "Putty" ou "Terminal Linux" disponível na máquina

* Acesso ao portal do WildFly: dc-pje.tjdft.jus.br

* Usuário com permissão para se conectar e executar comandos nas máquinas: TJSU100 (acesso as instâncias do PJE), BDU110 (PostGres PJe1i) e BDU113 (PostGres PJe 2i).

* Login do usuário cadastrado no grupo "sudoers" (grupo de superusuários)

* Caso haja solicitação de execução de script no banco de dados, veja algumas orientações do NUBAD: clique [aqui.]()

* Caso seja necessário acesso aos arquivos de configuração do PJE, veja a relação de todos hosts e endereços [aqui.]()



### __*Atenção*__: 

 - Antes de atuar, verifique se foram observados, no fluxo de atendimento, todos os critérios para processar este tipo de requisição. Veja o fluxo [aqui.]()

---


<!-- ATUAÇÃO  -->

 ### __*ATUAÇÃO:*__



* __1 - Parar as instâncias especificadas para o deploy e conferir:__



a) Acessar o portal  **WildFly** <http://dc-pje.tjdft.jus.br/console/App.html>,  clicar em: *__Runtime Server Groups__* selecionar o grupo requerido abrir a lista *__View__* e clicar sobre a opção *__Stop__*, conforme imagem abaixo:

<!-- IMAGEM -->
<div align="center">

![Para_pje](/assets/Parar_pje.png)

 </div>
b) Confirmar se os ambientes realmente pararam:

Obs: Há scripts na __MIPU100__ para checar o status das instâncias e para matar processos, se necessário, vide abaixo.


c) Logar na __MIPU100__ como root e executar o comando:

<div align="center">


Ambientes PJe 1ª Instância | Ambientes PJe 2ª Instância
-------------------------- | ---------
pje-consulta               |pje2i-cunsulta
pje-digititalização        |pje2i-digititalização
pje 1i                     |pje 2i
pje-integraçao             |pje2i-integração
pje-internet               |pje2i-internet
pje-interno                |pje2i-consulta
pje-mni-consulta           |pje2i-mni
pje-mni                    |
                     
</div>
d) Se houver instância java em execução no <ambiente>, executar o comando a seguir e depois o verificar novamente se a instância foi parada:

*./kill-instancia-java-**'ambiente'**.sh*


* 2 - __Realizar o deploy dos arquivos:__
  
  * Efetuar a conexão na *__MIPU100__* através do Putty ou MobaXterm. 
  * Acessar o script de deploy automático da máquina *__MIPU100__* e realizar a operação de deploy para os itens especificados na requisição:

<div align="center">

![Para_pje](/assets/executa_deploy.png)

 </div>
  
