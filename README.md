# Smart Mirror

[SmartMirror Display](https://smartmirror-display.vercel.app)

# Introdução
O projeto foi dividido em três partes:
- Aplicativo
- Página WEB
- API

## Motivo
A ideia do aplicativo é controlar o Smart Mirror sem que fosse necessário conectar periféricos ao espelho, fazendo tudo de forma remota.

O intuito da página Web é exibir a interface do sistema no espelho. O fato de ser executada em um navegador facilita a execução, sendo necessário quase nenhuma configuração além da instalação do próprio navegador.

A API (Application Programming Interface) foi desenvolvida para fazer a comunicação entre o espelho (página web) e o dispositivo (app).

## Tecnologia utilizada
A linguagem de programação utilizada nas três partes foi o JavaScript com TypeScript.

_JavaScript por ser uma linguagem muito utilizada e possibilitar o desenvolvimento das três partes com a mesma linguagem._

_TypeScript para ajudar no processo de desenvolvimento através das tipagens._

### APP
- Linguagem: JavaScript (TypeScript)
- Framework: React Native e Expo

**Por que React Native?<br>**
Por que é JavaScript.

**Por que Expo?<br>**
O Expo permite um desenvolvimento mais rápido, já que ele configura automaticamente diversas funcionalidades que necessitariam de configurações nativas e específicas para cada plataforma (Android e iOS).

### WEB
- Linguagem: JavaScript (TypeScript)
- Framework: Next.js (React JS)
- Plataforma: Vercel

> _O Next é como o recepcionista que verifica qual o destino do cliente antes dele entrar no local, enquanto o React permite a entrada do cliente e o redireciona depois._

**Por que React?**<br>
Por permitir um uso mais rápido e prático do JavaScript mesclado com HTML e pela possibilidade de componentização que permite um grande reaproveitamento de código.

**Por que Next?**<br>
Pelo Server Side Rendering, que renderiza o HTML antes de enviar para o usuário, possibilitando a indexação em ferramentas de busca **(pesquisar mais sobre)**<br>
E também pela plataforma da Vercel que permite a publicação gratuita de páginas web.

**Vercel**<br>
Plataforma utilizada para publicação da página Web de forma gratuita para ser acessada pelo sistema do espelho.<br>
Também é possível a aquisição de um domínio e de upgrades para melhor desempenho do servidor caso haja um volume maior de acessos futuramente.

### API
- Linguagem: JavaScript (TypeScript)
- Engine: Node.js
- Banco de Dados: MongoDB
- Frameworks e bibliotecas: Express, SocketIO (WebSocket)
- APIs utilizadas: Google APIs e OpenWeather

**Node.js**<br>
Software que permite a execução de códigos JavaScript fora de um navegador web.

**Express**<br>
Fornece recursos para construção de rotas para requisições HTTP _(provavelmente será removido devido à utilização do WebSocket)_

**SocketIO (WebSocket)**<br>
Biblioteca para comunicação bidirecional em tempo real entre clientes e servidores da web.<br>
Necessário para que as interações do usuário com o aplicativo reflitam em tempo real na página web exibida no espelho.<br>
Utiliza eventos<br>

Fluxo utilizado:<br>
1. O APP emite um evento para API com os dados do usuário logado e o código do espelho;
2. A API processa os dados, conectando o usuário a um espelho específico;
3. A API emite um evento para a página WEB cujo código seja igual ao informado pelo usuário;
4. A página WEB recebe os dados do usuário e faz um redirecionamento para a página principal, onde se encontra o relógio, emails e outros dados.
5. A página principal receberá novos dados de tempos em tempos _(ainda não definido)_.

_Ainda não foi desenvolvido o redirecionamento específico de dados, então os dados estão sendo enviados pra todos as páginas conectadas ao servidor._

_Pesquisar mais sobre WebSocket_

**MongoDB (Banco de Dados)**<br>
Para utilizar a plataforma MongoDB Atlas (banco de dados na nuvem com plano gratuito).<br>
_Pesquisar mais sobre o banco de dados não relacionais (MongoDB é um deles)_

**Google APIs**<br>
Utilizado para listagem de e-mails (Gmail) e compromissos da agenda (Google Calendar).

**OpenWeather**<br>
Utilizado para obter dados do clima.
