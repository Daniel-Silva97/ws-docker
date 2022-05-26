<h1>Instalação do Sonarqube via Docker Compose </h1>

1. Acessar a máquina que hospedará o container do SonarQube e editar a configuração localizada em <code>/etc/sysctl.conf</code>, alterar/incluir o parâmetro <code>vm.max_map_count = 262144</code>, salvar e reiniciar o sistema;
2. Compose up do arquivo <code>docker-compose.yml</code>, com ele será criado o Banco de dados em PostGres e o serviço do SonarQube;
3. Após a instalação do Sonar, necessário realizar a integração via Jenkins presente em <code>http://"SONARQUBE_HOST":9000/documentation/analysis/jenkins/</code>;
4. Efetuada a configuração inicial com base na documentação acima necessário criar um projeto no SonarQube, em <code>Projects --> Add Project</code>, selecionar a opção <code>Manually</code>, informe um nome para o projeto e project key solicitado pelo SonarQube, e siga as instruções fornecidas pela aplicação para gerar a integração via Jenkins;

5. Crie a pipeline via Jenkins com base no recomendado gerado pelo Sonarqube na criação do projeto;
6. Observações: criadas as variáveis de ambiente {SONAR_HOST} e {SONAR_LOGIN} no Jenkins para uso no código da pipeline;

