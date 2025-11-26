# 🛥️ Projeto Luxo – Aluguel de Iates

Este projeto foi desenvolvido como parte da **2ª avaliação da disciplina** e tem como objetivo simular um site de luxo para aluguel de iates, integrando páginas informativas com uma área de contato e um ambiente administrativo para leitura de mensagens.

---

## 📌 Objetivo do projeto

Criar uma aplicação web utilizando **HTML, CSS e JavaScript** que permita:

- ✅ Visualização de informações sobre aluguel de iates  
- ✅ Envio de mensagens por meio de um formulário  
- ✅ Leitura das mensagens recebidas apenas por usuários autorizados  
- ✅ Marcação e exclusão das mensagens  

---

## 🌐 Estrutura do site

O site é composto pelas seguintes páginas:

- **index.html** – Página inicial  
- **aluguel.html** – Tipos de iates disponíveis  
- **destinos.html** – Principais destinos oferecidos  
- **tripulacao.html** – Informações sobre a tripulação  
- **contato.html** – Formulário para envio de mensagens  
- **admin.html** – Área de login (restrita)  
- **mensagens.html** – Visualização e gerenciamento das mensagens enviadas  

---

## ✉️ Envio de mensagens (contato.html)

Na página de contato foi implementado um formulário com os campos:

- Nome  
- E-mail  
- Mensagem  

Ao clicar em **Enviar**, os dados preenchidos são capturados e organizados em um objeto no seguinte formato:

    var mensagem = {
      nome: "nome informado",
      email: "email informado",
      mensagem: "mensagem digitada"
    }

Esse objeto é enviado para a função `inserirMensagem(mensagem)`, presente no arquivo **api.js**, responsável por armazenar a mensagem.

---

## 🔒 Área Administrativa (admin.html)

A página **admin.html** realiza a autenticação de acesso por meio da função:

    validarUsuario(objLoginSenha)

O objeto enviado possui o seguinte formato:

    var objLoginSenha = {
      email: "email informado",
      senha: "senha informada"
    }

Credenciais válidas:

- **E-mail:** `admin@admin.com`  
- **Senha:** `1234`  

Se o login for bem-sucedido, o usuário é redirecionado para a página **mensagens.html**.  
Caso contrário, é exibida a mensagem:

> "E-mail e Senha inválidos"

---

## 📬 Leitura das mensagens (mensagens.html)

Na página **mensagens.html** é utilizada a função:

    obterMensagens()

Essa função retorna um array contendo todas as mensagens enviadas.

As mensagens são exibidas dinamicamente em uma **tabela**, com os seguintes comportamentos:

- 🔹 Mensagens **não visualizadas** aparecem em **negrito**
- 🔹 Mensagens **visualizadas** aparecem com fonte normal
- 🔹 Cada mensagem contém dois botões de ação

### Funções disponíveis para cada mensagem

- ✅ **Mensagem Visualizada** – Marca a mensagem como lida  
- ❌ **Excluir Mensagem** – Remove a mensagem da lista  

Em ambas as ações, o usuário deve confirmar antes da execução através de um `confirm()`.

As informações são armazenadas localmente no navegador por meio do **LocalStorage**, garantindo que os dados permaneçam mesmo após atualização da página.

---

## 🛠️ Tecnologias utilizadas

- **HTML5**
- **CSS3**
- **JavaScript**
- **jQuery**
- **LocalStorage**

---

## 💻 Como usar o projeto

1. Abra o arquivo `index.html` no navegador para acessar o site.  
2. Vá até a página **Contato** e envie uma mensagem.  
3. Depois, acesse **admin.html** e utilize:  
   - E-mail: `admin@admin.com`  
   - Senha: `1234`  
4. Você será redirecionado para a página **mensagens.html**, onde poderá:  
   - Visualizar mensagens em negrito (não lidas);  
   - Marcar como visualizadas;  
   - Excluir mensagens.  

---

## ✅ Conclusão

O projeto cumpre todos os requisitos propostos no enunciado, utilizando as funções fornecidas no arquivo **api.js** para criar um sistema funcional de envio, autenticação e leitura de mensagens, com controle de visualização e exclusão.

Esse sistema simula um ambiente real de atendimento ao cliente em um serviço de **aluguel de iates de luxo**.
