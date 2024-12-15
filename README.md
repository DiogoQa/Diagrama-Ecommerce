# E-commerce Database Project

## Overview
Este projeto faz parte do Bootcamp organizado pela Dio em parceria com a Suzano. O objetivo é desenvolver e implementar um banco de dados relacional para uma plataforma de e-commerce. O esquema do banco de dados é projetado para gerenciar vários aspectos de um negócio de e-commerce, incluindo produtos, fornecedores, clientes, pedidos, pagamentos, entregas e mais.

## Database Schema
O esquema do banco de dados é representado no Diagrama Entidade-Relacionamento (ERD) fornecido. Abaixo está uma descrição detalhada de cada tabela e suas relações:

### Terceiro - Vendedor
- **Colunas**: idTerceiro (INT), Razão Social (VARCHAR(45)), Local (VARCHAR(45))
- **Descrição**: Armazena informações sobre vendedores de terceiros.

### Produtos por Vendedor (terceiro)
- **Colunas**: Terceiro_Vendedor_idTerceiro (INT), Vendedor (INT), Produto_idProduto (INT), Quantidade (INT)
- **Descrição**: Gerencia os produtos fornecidos por cada vendedor.

### Relação de produto/pedido
- **Colunas**: Produto_idProduto (INT), Pedido_idPedido (INT), Quantidade (INT)
- **Descrição**: Liga produtos a pedidos e rastreia a quantidade de cada produto em um pedido.

### Cliente
- **Colunas**: idCliente (INT), Nome (VARCHAR(45)), Identificação (VARCHAR(45)), Endereço (VARCHAR(45))
- **Descrição**: Armazena informações dos clientes.

### Pagamento
- **Colunas**: idPagamento (INT), Cliente_idCliente (INT), TipoPagamento (VARCHAR(45)), Valor (FLOAT), DetalhesPagamento (VARCHAR(255)), Pedido_idPedido (INT), Pedido_Cliente_idCliente (INT)
- **Descrição**: Gerencia os detalhes de pagamento dos pedidos.

### Conta
- **Colunas**: idConta (INT), Cliente_idCliente (INT)
- **Descrição**: Informações gerais da conta vinculadas aos clientes.

### Conta_PJ
- **Colunas**: idConta_PJ (INT), CNPJ (VARCHAR(14)), RazãoSocial (VARCHAR(45)), Conta_idConta (INT), Conta_Cliente_idCliente (INT)
- **Descrição**: Armazena informações da conta para clientes corporativos.

### Conta_PF
- **Colunas**: idConta_PF (INT), CPF (VARCHAR(11)), Nome (VARCHAR(45)), Conta_idConta (INT), Conta_Cliente_idCliente (INT)
- **Descrição**: Armazena informações da conta para clientes individuais.

### Disponibilizando um produto
- **Colunas**: Fornecedor_idFornecedor (INT), Produto_idProduto (INT)
- **Descrição**: Liga fornecedores a produtos.

### Fornecedor
- **Colunas**: idFornecedor (INT), Razão Social (VARCHAR(45)), CNPJ (VARCHAR(45))
- **Descrição**: Armazena informações dos fornecedores.

### Produto
- **Colunas**: idProduto (INT), Categoria (VARCHAR(45)), Descrição (VARCHAR(45)), Valor (FLOAT)
- **Descrição**: Armazena detalhes dos produtos.

### Estoque
- **Colunas**: idEstoque (INT), Local (VARCHAR(45))
- **Descrição**: Gerencia locais de estoque.

### Produto_has_Estoque
- **Colunas**: Produto_idProduto (INT), Estoque_idEstoque (INT), Quantidade (INT)
- **Descrição**: Liga produtos a locais de estoque e rastreia quantidades.

### Pedido
- **Colunas**: idPedido (INT), Status do pedido (VARCHAR(45)), Descrição (VARCHAR(45)), Cliente_idCliente (INT), Frete (FLOAT)
- **Descrição**: Gerencia os detalhes dos pedidos.

### Entrega
- **Colunas**: idEntrega (INT), Entregador (VARCHAR(100)), CódigoRastreamento (VARCHAR(45)), DataEnvio (DATE), DataEntregaPrevista (DATE), DataEntregaReal (DATE), StatusEntrega (VARCHAR(45)), Pedido_idPedido (INT), Pedido_Cliente_idCliente (INT)
- **Descrição**: Gerencia os detalhes das entregas.

### Transportadora
- **Colunas**: idTransportadora (INT), Nome (VARCHAR(45)), CNPJ (VARCHAR(14)), Telefone (VARCHAR(15)), Endereço (VARCHAR(45)), Entrega_idEntrega (INT), Entrega_Pedido_idPedido (INT), Entrega_Pedido_Cliente_idCliente (INT)
- **Descrição**: Armazena informações sobre as empresas de entrega.

## How to Use
1. **Setup the Database**: Use os scripts SQL fornecidos para criar o banco de dados e as tabelas.
2. **Populate Data**: Insira dados de exemplo nas tabelas para testar a funcionalidade do banco de dados.
3. **Run Queries**: Execute consultas para interagir com os dados e verificar a funcionalidade do sistema.
