<b> Configuração de Infraestrutura AWS </b>

Descrição dos passos que realizei para configurar a infraestrutura na AWS, incluindo a criação de grupos de segurança, instância EC2 e banco de dados RDS PostgreSQL.

Passo a Passo

<b> 1. Criar Security Groups (Grupos de Segurança) </b>

<b> a. Criar um Security Group aws_ec2 </b>

Acessei o console da AWS e fui até a seção "Security Groups".

Cliquei em "Create Security Group".

Defini um nome e uma descrição para o grupo.

Adicionei as regras de entrada:

Permiti acesso SSH (porta 22) apenas para o meu IP pessoal.

Permiti acesso TPC PERSONALIZADO (porta 3000) para qualquer IP (0.0.0.0/0).

Salvei o Security Group.

<b> b. Criar um Security Group aws_rds </b>

Ainda na seção "Security Groups", cliquei em "Create Security Group".

Defini um nome e uma descrição para o grupo.

Adicionei a regra de entrada:

Permiti conexão PostgreSQL (porta 5432) apenas para o Security Group da EC2 que criei anteriormente.

Salvei o Security Group.

<b> 2. Criar uma Instância EC2 (aws_rds_ec2) </b>

Acessei o console da AWS e fui até "EC2" > "Instances".

Cliquei em "Launch Instance".

Escolhi a AMI "Amazon Linux".

Escolhi o tipo de instância conforme necessário.

No passo de configuração de segurança, associei o Security Group aws_ec2.

Escolhi ou criei um par de chaves (keyAWS.pem) para acesso SSH e fiz o download.

Cliquei em "Launch" para criar a instância.

<b> 3. Criar um Banco de Dados via RDS (aws-db) </b>

<b> a. Criar um Banco de Dados PostgreSQL </b>

1. Acessei o console da AWS e fui até "RDS".

2. Cliquei em "Create Database".

3. Escolhi o motor de banco de dados "PostgreSQL".

<b> Defini as configurações: </b>

4. Tipo de instância conforme necessário.

5. Usuário e senha para acesso ao banco de dados.

6. Security Group (aws_rds) criado para o RDS.

7. O nome do banco inicial não foi necessário pois utilizei o Prisma.

Finalizei a criação do banco de dados.

Após a criação, anotei o endpoint do banco de dados gerado para conexão futura.
