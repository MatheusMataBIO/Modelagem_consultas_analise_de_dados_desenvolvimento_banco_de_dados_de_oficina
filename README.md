## Criação e modelagem de Banco de dados para oficina mecânica 💾



### Objetivo 🎯 

Esse projeto tem como objetivo praticar minhas habilidades com modelagem de dados, criação de database, criação de tabelaas, análise de dados e consultas ao database criado. 

### Descrição

Nesse case uma oficina mecânica solicitou que eu criasse um modelo utilizando o Workbench do MySQL e criasse um banco de dados a qual pudesse fazer consultas para análise de dados.

### Dados

O Banco de dados deveria conter informações de clientes, veículos, ordem de serviço, peças, serviços e mecânico e deveria conter identificação por CPF ou CNPJ. Os que deverão ser inseridos para dados se encontra no 'script de inserção de dados'.

### Construção do banco de dados

#### 1 - Criação do banco de dados 

Utilizei um recurso 'CREATE DATABASE IF NOT EXISTS' para somente criar o banco de dados caso não exista outro banco de dados com nome semelhante.

#### 2 - Tabela clientes

Armazena informações sobre clientes  

Colunas:
idCliente: Identificador único do cliente (chave primária).
Primeiro_nome, Nome_meio, Ultimo_nome: Nome completo do cliente.
Endereço: Endereço do cliente.
Contato: contato do cliente

#### 3 - Tabela veículos

Armazena informações sobre os veículos dos clientes

Colunas:
idVeículos: Identificador único do veículo (chave primária).
Clientes_idClientes: Identificador do cliente (chave estrangeira para clientes).
Placa: Número da placa do veículo (numeração fixa).
Modelo: Modelo do veículo. 
Ano: Ano em que o veículo foi fabricado.

#### 4 - Tabela ordem_de_serviço_OS

Armazena o pedido de serviço com todas as informações descritas pelo cliente

Colunas:
idOrdem_de_Serviço_OS: Identificador único da ordem de serviço (chave primária).
Veículos_idVeículos: Identificador do veículo (chave estrangeira para veículos).
Veículos_idClientes: Identificador do cliente (chave estrangeira para clientes).
Data_emissão: Data que foi feita o pedido da ordem de serviço.
Valor_total: Valor total do serviço.
Status_serviço: Status atual do serviço (Em andamento, Serviço concluído, Em processamento)
Descrição_pedido: Detalhes do pedido.
Data_conclusão: Data que o serviço foi concluído.
Número: Número de identificação da ordem de serviço.

#### 5 - Tabela peças

Armazena as informações da peças necessárias para executar o serviço

Colunas:
idPeças: Identificador único das peças (chave primária).
Descrição: Descrição da peça.
Valor: Valor de custo da peça.

#### 6 - Tabela serviços

Gerencia quais o serviços que serão executados 

Colunas:
idServiços: Identificador único do serviço (chave primária).
Descrição: Descrição sobre o serviço que será executado.
Valor_mão_obra: Valor total pela mão de obra

#### 7 - Tabela Mecânico

Gerencia os mecânicos e as escializações que serão necessárias

Colunas:
idMecânico: Identificador único do mecânico (chave primária).
Nome: Primeiro nome do mecânico.
Último_nome: último nome do mecânico.
Especialidade: Tipo de espcialização que o mecânico possui.
Código: Código do mecânico.
Endereço: Endereço do mecânico.

#### 8 - Tabela ordem_de_serviço_OS_das_peças

Especifica a quantidade de peças que serão necessárias para o serviço.

Colunas:
Peças_idPeças: Identificador de peças (chave estrangeira).
OS_idOrdem_de_Serviço_OS: Identificador de ordem de serviço (chave estrangeira).
OS_Veículos_idVeículos: Identificador de veículos (chave estrangeira).
OS_Veículos_idClientes: Identificador de clientes (chave estrangeira).
Quantidade: Quantidade de peças

#### 9 - Tabela ordem_de_serviço_OS_dos_serviços

Especifica a quantidade de serviços que serão realizados.

Colunas:
Serviços_idServiços: Identificador de Serviços (chave estrangeira).
OSS_idOrdem_de_Serviço_OS: Identificador de ordem de serviço (chave estrangeira).
OSS_Veículos_idVeículos: Identificador de veículos (chave estrangeira).
OSS_Veículos_idClientes: Identificador de clientes (chave estrangeira).
Quantidade_serviços: Quantidade de serviços

#### 10 - Tabela  Ordem_de_serviço_OS_dos_mecãnicos

Especifica a quantidade de mecânicos que serão necessários.

Colunas:
Mecânico_idMecãnico: Identificador de mecânico (chave estrangeira).
OSM_idOrdem_de_Serviço_OS: Identificador de ordem de serviço (chave estrangeira).
OSM_Veículos_idVeículos: Identificador de veículos (chave estrangeira).
OSM_Veículos_idClientes: Identificador de clientes (chave estrangeira).
Quantidade_mecânicos: Quantidade de serviços

### Consultas

As consultas se encontram em "Script de Consultas".
