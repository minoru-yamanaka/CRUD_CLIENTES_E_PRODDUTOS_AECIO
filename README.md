# Sistema de Vendas
![home](/index.png)
[Este é um sistema simples de gerenciamento de clientes e produtos, desenvolvido com PHP no backend para a API e HTML/CSS/JavaScript no frontend para a interface do usuário.](#)

## 🚀 Funcionalidades

* **Gerenciamento de Clientes:**
    * Listar todos os clientes.
    * Buscar cliente por ID.
    * Cadastrar novos clientes.
    * Atualizar dados de clientes existentes.
    * Excluir clientes.
    * Visualização de status (Ativo/Inativo).
* **Gerenciamento de Produtos:**
    * Listar todos os produtos.
    * Buscar produto por ID.
    * Cadastrar novos produtos.
    * Atualizar dados de produtos existentes.
    * Excluir produtos.
    * Visualização de status (Ativo/Inativo).
* **Interface do Usuário:**
    * Interface web responsiva com abas para clientes e produtos.
    * Formulários modais para cadastro e edição.
    * Máscara para CPF no formulário de cliente.

## 🛠️ Tecnologias Utilizadas

* **Backend:**
    * PHP 7.4+
    * PDO (PHP Data Objects) para conexão com o banco de dados.
* **Banco de Dados:**
    * MySQL.
* **Frontend:**
    * HTML5
    * CSS3
    * JavaScript (ES6+) para interações dinâmicas e consumo da API.

## 📁 Estrutura de Pastas

A estrutura de pastas do projeto deve ser organizada da seguinte forma na raiz do seu servidor web (ex: `htdocs` para XAMPP):

```
/venda/
├── api/
│   ├── clientes_api.php
│   └── produtos_api.php
├── dao/
│   ├── ClienteDAO.php
│   └── ProdutoDAO.php
├── model/
│   ├── Cliente.php
│   └── Produto.php
├── Database.php
├── index.html
└── loja.sql
```

## ⚙️ Como Configurar e Rodar

Siga os passos abaixo para configurar e rodar o projeto em sua máquina local:

### 1. Pré-requisitos

* Servidor Web (Apache, Nginx, etc.)
* PHP (versão 7.4 ou superior recomendada)
* MySQL
* (Opcional) XAMPP, WAMP ou LAMP para uma instalação fácil do ambiente.

### 2. Configuração do Banco de Dados

1.  Acesse seu sistema de gerenciamento de banco de dados (ex: phpMyAdmin).
2.  Crie um novo banco de dados chamado `venda`.
3.  Importe o arquivo `loja.sql` para dentro do banco de dados `venda`. Este script irá criar as tabelas `clientes` e `produtos`.
4.  **Atenção:** Verifique as credenciais de conexão no arquivo `Database.php`:
    ```php
    // Database.php
    $db_host = "localhost";
    $db_name = "venda";
    $db_user = "root"; // Verifique se este é o seu usuário do MySQL
    $db_pass = "";     // Se você usa senha no MySQL, insira-a aqui
    ```
    Ajuste `$db_user` e `$db_pass` conforme a sua configuração do MySQL.

### 3. Configuração dos Arquivos do Projeto

1.  Clone este repositório ou baixe os arquivos do projeto.
2.  Coloque a pasta `venda` (contendo `api/`, `dao/`, `model/`, `Database.php`, `index.html`, etc.) no diretório raiz do seu servidor web (ex: `htdocs` para XAMPP).

### 4. Acessando a Aplicação

1.  Inicie seu servidor web (Apache/Nginx) e o serviço MySQL.
2.  Abra seu navegador e acesse:
    ```
    http://localhost/CRUD_CLIENTES_E_PRODDUTOS/index.html
    ```
    Ou simplesmente:
    ```
    http://localhost/CRUD_CLIENTES_E_PRODDUTOS/
    ```

### 5. Configuração da `API_BASE` no Frontend

**É crucial que o `index.html` aponte para o endereço correto da sua API.** No arquivo `index.html`, localize a linha que define `API_BASE`:

```javascript
// index.html
const API_BASE = 'http://localhost/CRUD_CLIENTES_E_PRODDUTOS/api'; // <--- Altere esta linha
```

**Se você está rodando localmente, mude para:**

```javascript
const API_BASE = 'http://localhost/CRUD_CLIENTES_E_PRODDUTOS/api';
// Ou
// const API_BASE = 'http://127.0.0.1/venda/api';
```

Isso garantirá que o frontend consiga se comunicar com o backend PHP.


## 🧪 Endpoints da API (Para Teste)

Você pode testar os endpoints da API diretamente no seu navegador ou usando ferramentas como Postman/Insomnia. Certifique-se de ajustar o `localhost` ou o IP conforme a sua configuração.

* **Listar Clientes:**
    `http://localhost/venda/api/clientes_api.php?action=listar`
* **Buscar Cliente por ID (Ex: ID 3):**
    `http://localhost/venda/api/clientes_api.php?action=buscar&id=3`
* **Listar Produtos:**
    `http://localhost/venda/api/produtos_api.php?action=listar`
* **Buscar Produto por ID (Ex: ID 5):**
    `http://localhost/venda/api/produtos_api.php?action=buscar&id=5`

**Exemplo de URL fornecida para teste (ajuste o caminho `CRUD_CLIENTES_E_PRODDUTOS` se a sua pasta raiz do projeto for `venda`):**

* `http://localhost/CRUD_CLIENTES_E_PRODDUTOS/api/clientes_api.php?action=listar&id=3`

    * **Observação:** No seu projeto, a estrutura da pasta é `/venda/api/`. Portanto, se a sua pasta raiz do projeto no servidor web for `venda`, a URL correta para o exemplo acima seria: `http://localhost/venda/api/clientes_api.php?action=buscar&id=3` (usando `action=buscar` para buscar por ID, como especificado em `clientes_api.php` e `endpoints.md`).

## 🤝 Contribuição

Contribuições são bem-vindas! Se você tiver sugestões ou melhorias, sinta-se à vontade para abrir uma issue ou enviar um pull request.

