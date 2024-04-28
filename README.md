# Arquitetura MVC - Marco-Ruas


## 1. Nome do Projeto: Abandono zero

**1.1 Descrição:** O objetivo do projeto é desenvolver um site responsivo compatível com dispositivos móveis e desktop para o INSPA. Este site funcionará como um formulário destinado a coletar dados sobre os cuidadores de cães, os quais serão utilizados para pesquisas futuras. Para alcançar esse propósito, o site será integrado a um banco de dados, permitindo a coleta e armazenamento das informações dos usuários, bem como o registro de suas respostas. Ao final, os pesquisadores terão acesso a um relatório detalhado contendo estatísticas e as respostas dos formulários.

**1.2 Arquitetura:** MVC (Model-View-Controller)

**1.3 Ferramenta de Diagramação:** draw.io

### Nota:
Todas as imagens das arquiteturas estão disponíveis no arquivo `MVC.md`.

## 2. Modelos (Models):

**2.1 Tutor**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Tutor é responsável pela interação entre o tutor com o site inicial. Ela inclui a lógica para listar e procurar os dados para verificar se o usuário já está logado ou não no site. Essa arquitetura é crucial pois ela que redirenciona para as outras arquiteturas.
1. **Entidade User**: Armazena os dados do usuário.
* Id: Guardar o identificador único de cada usuário
* Nome: Guardar o nome do usuário.
* Email: Guardar o email do usuário.
* Senha: Guardar a senha do usuário.
* Role: Guardar a informação se o usuário vai ser um administrador ou não.


**2.2 Formulário**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Formulários é focada na coleta e processamento de dados dos usuários através de formulários. Ela inclui a lógica para listar e gravar, garantindo que os dados sejam coletados de forma eficiente e segura. Essa arquitetura é essencial para a interação do usuário com a aplicação.
1. **Entidade Formulário Geral**: Armazena as respostas do formulário geral. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 2. **Entidade Formulário Tem**: Armazena as respostas do formulário tem cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 3. **Entidade Formulário Teve**: Armazena as respostas do formulário teve cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 4. **Entidade Formulário Quer ter**: Armazena as respostas do formulário quer ter cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 5. **Entidade Formulário Nulo**: Armazena as respostas do formulário não quer ter cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas


**2.2 Administrador**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Admin é dedicada à gestão administrativa da aplicação. Ela inclui funcionalidades para gerenciar os formulários, relatórios e análises. Essa arquitetura é crucial para o controle e monitoramento do sistema, permitindo aos administradores visualizar as estatísticas das pesquisas.

1. **Entidade Users**:
* Id: Guardar o identificador único de cada administrador.
* Nome: Guardar o nome do administrador.
* Email: Guardar o email do administrador.
* Senha: Guardar a senha do administrador.
* Role: Guardar a informação se o administrador vai ser um administrador ou não.

2. **Entidade Relatório**:
* Id: Guarda o identificador único de um relatório, por causa do filtrar.
* Dados: Guarda as informações gerais do relatório relacionado a estatísticas e dados.

3. **Entidade Formulário Geral**: Armazena as respostas do formulário geral. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 4. **Entidade Formulário Tem**: Armazena as respostas do formulário tem cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 5. **Entidade Formulário Teve**: Armazena as respostas do formulário teve cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 6. **Entidade Formulário Quer ter**: Armazena as respostas do formulário quer ter cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

 7. **Entidade Formulário Nulo**: Armazena as respostas do formulário não quer ter cachorro. 
 * Id: Guarda o identificador único de cada formulário.
 * Respondeu: Guarda a informação se o usuário respondeu a pergunta ou se pulou ela. 
 * Respostas: Guarda as respostas das perguntas

**2.3 Login**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A arquitetura Login é responsável pela autenticação, autorização dos usuários e verificação de administrador. Ela inclui a lógica para o registro de novos usuários, login e recuperação de senha. Essa arquitetura é fundamental fazer a validação de usuários e cadastrar os novos.

1. **Entidade User**: Armazena os dados do usuário.
* Id: Guardar o identificador único de cada usuário
* Nome: Guardar o nome do usuário.
* Email: Guardar o email do usuário.
* Senha: Guardar a senha do usuário.
* Role: Guardar a informação se o usuário vai ser um administrador ou não.

## 3. Controladores (Controllers):

**3.1 Tutor**

* Responsabilidades: Gerenciar a lógica de negócios relacionada aos tutores, incluindo a criação, atualização, listagem e busca de tutores.

* Métodos:
    * Listar: Retorna uma lista de todos os tutores.
        * Entrada: Nenhuma.
        * Saída: Lista de objetos Tutor.
    * Procurar: Busca um tutor específico por nome.
        * Entrada: Nome do tutor.
        * Saída: Objeto Tutor ou mensagem de erro.

**3.2 Formulários**

* Responsabilidades: Gerenciar a interação do usuário com formulários, incluindo a validação e submissão de dados.

* Métodos:
    * Listar: Retorna uma lista de todos os formulários disponíveis.
        * Entrada: Nenhuma.
        * Saída: Lista de objetos Formulário.
    * Procurar: Busca um formulário específico por identificador.
        * Entrada: Identificador do formulário.
        * Saída: Objeto Formulário ou mensagem de erro.

**3.3 Admin**

* Responsabilidades: Gerenciar a lógica de negócios relacionada à administração do sistema, incluindo a gestão de usuários e acesso a dashboards.

* Métodos:
    * Listar: Retorna uma lista de todos os usuários administradores.
        * Entrada: Nenhuma.
        * Saída: Lista de objetos Usuário Admin.
    * Dashboard: Exibe um painel de controle com informações resumidas do sistema.
        * Entrada: Nenhuma.
        * Saída: Objeto Dashboard.

**3.4 Login**

* Responsabilidades: Gerenciar o processo de autenticação de usuários, incluindo a verificação de credenciais e a criação de sessões.

* Métodos:
    * Tutor: Autentica um tutor e cria uma sessão.
        * Entrada: Credenciais do tutor (nome de usuário e senha).
        * Saída: Sessão do tutor ou mensagem de erro.
    * Gravar: Registra um novo tutor no sistema.
        * Entrada: Dados do novo tutor.
        * Saída: Objeto Tutor criado ou mensagem de erro.

## 4. Views:

### 4.1 Tutor

As Views no Sails.js fazem parte da arquitetura MVC (Model-View-Controller) e são responsáveis pela apresentação dos dados ao usuário. Elas definem como os dados do modelo serão exibidos na interface do usuário. Aqui está uma análise detalhada das views mencionadas na imagem:

**4.1.1 Home**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Carousel: Um carrossel de imagens para destacar conteúdos ou promoções importantes.

* Botão de login: Uma área para que os usuários façam login no site.

* Imagem: Seção para colocar as imagens sobre as informações do projeto.

* Texto Sobre: Fornece informações sobre o site ou a organização.

**4.1.2 Finalizado**

* Imagem: Quando o usuário responder ou tiver respondido a pesquisa, aparece uma imagem informando formulário respondido.

* Texto: Texto informando que o formulário já foi respondido.

* Botão: Botão para sair do site ou voltar para a tela de início.

### 4.2 Formulários

**4.2.1 Formulário Geral**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Perguntas: Seção que ficará todas as perguntas da tela.

* Respostas: Uma seção para responder a seção de perguntas.

* Botão enviar: Após preencher toda a seção responder, o usuário aperta o botão enviar e manda para o model.

**4.2.2 Formulário Tem Cachorro**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Perguntas: Seção que ficará todas as perguntas da tela.

* Respostas: Uma seção para responder a seção de perguntas.

* Botão enviar: Após preencher toda a seção responder, o usuário aperta o botão enviar e manda para o model.

**4.2.3 Formulário Quer ter cachorro**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Perguntas: Seção que ficará todas as perguntas da tela.

* Respostas: Uma seção para responder a seção de perguntas.

* Botão enviar: Após preencher toda a seção responder, o usuário aperta o botão enviar e manda para o model.

**4.2.4 Formulário Teve cachorro**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Perguntas: Seção que ficará todas as perguntas da tela.

* Respostas: Uma seção para responder a seção de perguntas.

* Botão enviar: Após preencher toda a seção responder, o usuário aperta o botão enviar e manda para o model.

**4.2.5 Formulário Nulo**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Perguntas: Seção que ficará todas as perguntas da tela.

* Respostas: Uma seção para responder a seção de perguntas.

* Botão enviar: Após preencher toda a seção responder, o usuário aperta o botão enviar e manda para o model.

**4.2.6 Finalizado**

* Imagem: Quando o usuário responder ou tiver respondido a pesquisa, aparece uma imagem informando formulário respondido.

* Texto: Texto informando que o formulário já foi respondido.

* Botão: Botão para sair do site ou voltar para a tela de início.

### 4.3 Administrador

**4.3.1 Relatório**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Gráfico: Seção para mostrar os dados da pesquisa em um gráfico.

* Dropbox: Caixa de opções que vai mostrar as estatísticas da pesquisa.

* Estatística: Mostra uma caixa de texto as informações da seção dropbox.

* Botão baixar: Baixar os filtros de uma determinada resposta ou formulário completo em arquivo csv.

### 4.4 Login

**4.4.1 Login**

* Navbar: Serve como barra de navegação para facilitar o acesso a diferentes partes do site.

* Imagem: Uma imagem da logo do site.

* Caixas de entrada: Seção para o usuário preencher nome, email e senha.

* Checkbox: Checkbox para verificar se o usuário é administrador ou não.

* Botão Formulário: Botão para fazer o login e ir para os formulários.

## 5. Services
Os Services são funções reutilizáveis que podem ser chamadas de qualquer parte da aplicação. Eles são usados para encapsular a lógica de negócios que não se encaixa diretamente em um modelo ou controlador. No projeto os services são usados para realizar operações específicas relacionadas aos tutores, como verificar se um usuário já está logado ou não, ou se um usuário tem permissão para acessar determinadas funcionalidades.

### 5.1 Tutor

Os services relacionados ao tutor são cruciais para verifica se o usuário já respondeu a pesquisa ou não. Eles garantem que apenas usuários que não responderam a pesquisa acessem o formulário.

**5.1.1 Verificar**
* Verificar email: Este serviço verifica se o email fornecido por um usuário já está registrado no sistema. Isso é útil para evitar duplicatas e garantir que cada usuário tenha um email único.
* Verificar ip ou cookie: Este serviço pode ser usado para rastrear os usuários com base em seu endereço IP ou cookies, o que pode ser útil para fins de segurança ou para personalizar a experiência do usuário.

### 5.2 Login
Os services relacionados ao login são cruciais para gerenciar a autenticação e autorização dos usuários. Eles garantem que apenas usuários autorizados possam acessar determinadas partes da aplicação.

**5.2.1 Login**
* Verificar nome: Este serviço verifica se o nome de usuário fornecido existe no sistema.
* Verificar email:  Este serviço verifica se o email fornecido corresponde a um usuário registrado no sistema. 
* Verificar senha: Este serviço compara a senha fornecida pelo usuário com a senha armazenada no sistema para autenticar o usuário.
* Verificar role: Este serviço verifica se o usuário tem a role adequada para acessar determinadas funcionalidades. 

**5.2.2 Cadastro**
* Cadastra nome: Este serviço registra um novo usuário no sistema, armazenando seu nome.
* Cadastra email: Este serviço registra um novo usuário no sistema, armazenando seu email.
* Cadastra senha: Este serviço registra um novo usuário no sistema, armazenando sua senha de forma segura.
* Cadastra role: Este serviço registra um novo usuário no sistema, definindo sua role.


## 6. Infraestrutura:
### 6.1 Banco de Dados:
O banco de dados é que armazena todas as informações coletadas pelos formulários, incluindo dados dos usuários, respostas dos formulários e relatórios gerados. A escolha do banco de dados foi feita com base em fatores como escalabilidade, desempenho e facilidade de uso. Para esse projeto vai ser usado o banco de dados relacional PostgreSQL devido à sua robustez e suporte para transações, que são importantes para garantir a integridade dos dados.

A integração do banco de dados com a arquitetura MVC é feita através dos Modelos (Models), que representam as entidades do sistema e interagem diretamente com o banco de dados para realizar operações de CRUD (Create, Read, Update, Delete). Os Modelos são responsáveis por definir a estrutura dos dados, implementar regras de negócio e gerenciar o acesso aos dados armazenados no banco de dados.

### 6.2 APIs Externas:
Para o projeto vai ser necessário a integração de APIs externas para enriquecer a funcionalidade do sistema e melhorar a experiência do usuário. Uma das APIs externas que será utilizada é a API dos Correios, que permite a obtenção de informações sobre bairros e cidades com base no CEP fornecido pelo usuário. 

As APIs externas são integradas na arquitetura MVC principalmente através dos Controladores (Controllers), que atuam como intermediários entre a View e o Model. Os Controladores são responsáveis por receber as requisições do usuário, processá-las e, se necessário, fazer chamadas a APIs externas para obter dados adicionais. Após receber os dados, os Controladores podem atualizar os Modelos e, consequentemente, as Views para refletir as mudanças no sistema.

## 7. Implicações da Arquitetura:

A utilização da arquitetura MVC do Sails.js permite uma estrutura clara e organizada para o desenvolvimento do projeto, com várias implicações importantes:

* Escalabilidade: A separação de preocupações entre Model, View e Controller permite que cada componente seja escalado independentemente conforme necessário.
* Manutenção: A modularidade da arquitetura MVC facilita a manutenção e a atualização do sistema, pois as mudanças em um componente não afetam diretamente os outros.
* Testabilidade: A separação entre a lógica de negócios (Model) e a interface do usuário (View) torna mais fácil testar cada parte do sistema de forma isolada.
* Segurança: A integração de serviços de autenticação e armazenamento seguro de dados contribui para a segurança do sistema, protegendo as informações dos usuários.

## 8. Recursos Adicionais:
### 8.1 Documentação do Sails.js: https://github.com/balderdashy/sails 
### 8.2 Tutorial do draw.io: https://m.youtube.com/watch?v=w3zm-wbmlpc 
### 8.3 Exemplos de diagramas MVC: https://www.lucidchart.com/pages/templates
