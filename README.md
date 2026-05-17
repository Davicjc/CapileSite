# Capilé Drinks · Sistema de Gestão & Cardápio Interativo

![Capilé Drinks](https://images.weserv.nl/?url=i.imgur.com/6QJjYMe.jpg)

O **Capilé Drinks** é uma aplicação web completa projetada para um bar de drinks autorais. O projeto é dividido em duas frentes: uma landing page interativa com cardápio digital voltada para o cliente, e um painel de controle administrativo (Dashboard) voltado para a gestão do bar.

Tudo funciona de maneira reativa e integrada através do armazenamento no navegador (`LocalStorage`), permitindo que as alterações no cardápio ou novos pedidos reflitam instantaneamente na experiência, tudo sem a necessidade de um backend complexo (perfeito para demonstrações e portfólios).

---

## 🍹 Funcionalidades do Site Principal (`index.html`)

O site principal é o ponto de contato do cliente, desenvolvido com uma pegada estética "dark" e luzes em Neon brilhante, transmitindo a atmosfera noturna de um bar.

- **Design Premium em Neon**: Letreiros e tipografia em neon, com animações de brilho e reflexos nas imagens (estilo cyberpunk/bar noturno).
- **Cardápio Dinâmico em Tempo Real**: Os produtos e categorias listados são extraídos diretamente do banco de dados local. Quando o administrador adiciona ou edita uma bebida no painel, o cardápio do site é atualizado automaticamente.
- **Sistema de Carrinho Inteligente (Dock)**: Um menu flutuante (Dock) acompanha o usuário pela tela, mostrando a quantidade de itens e o valor total do pedido em tempo real.
- **Checkout Integrado**: O cliente pode fechar o pedido informando seus dados (como CPF e número da mesa). O pedido é então despachado diretamente para o painel de administração.
- **Avisos e Informações**: Seções com horários de funcionamento, localização (com um minimapa estilizado integrado) e contatos para facilitar a chegada do cliente ao bar físico.

---

## 💼 Painel Administrativo (`admin.html`)

O painel de gestão é o coração operacional do negócio. Desenvolvido para uso mobile-first ou desktop, o gestor do bar tem total controle sobre vendas e produtos.

### 📊 Dashboard e Métricas
- **Visão Geral**: Receita do dia, faturamento do mês, total de pedidos aguardando e ticket médio. Tudo atualizado no momento em que um pedido é processado.
- **Gráficos Visuais**: Uso da biblioteca `Chart.js` para plotar gráficos de linha (receita diária) e gráficos de barra/rosca (itens mais vendidos e volume de pedidos).
- **Alertas Pendentes**: Notificações e listagem imediata de clientes que acabaram de fazer um pedido na mesa e aguardam resposta.

### 📋 Gestão de Pedidos (Aprovação/Recusa)
- **Fluxo de Trabalho em Tempo Real**: Os pedidos chegam com status "Pendente" (`aguardando`). O gestor pode revisar a mesa, itens pedidos, valor total e descrição do cliente.
- **Ações Rápidas**: Com apenas um clique, o gestor pode:
  - **Aprovar (Aceitar)**: Muda o status para "aceito" e adiciona o valor à receita. (Integra visualmente avisando que será lançado no cartão ZIG).
  - **Recusar**: Cancela o pedido (caso falte algum ingrediente, por exemplo).
  - **Excluir**: Remove permanentemente o registro.
- **Pesquisa e Filtros**: Busca rápida de pedidos via CPF, número da mesa ou nome do produto.

### 🍔 Gestão do Cardápio
- **Cadastro Completo (CRUD)**: Possibilidade de **Adicionar, Editar ou Remover** produtos do menu.
- **Campos Personalizáveis**: Gestão do Nome, Preço, Descrição, Imagem do Produto e Categoria (Sours, Clássicos, Contemporâneos, Comidas, Jarras, etc.).
- **Sincronia Automática**: Tudo o que for alterado ou cadastrado aqui será imediatamente exibido na página `index.html` para os clientes.

### 📈 Relatórios Financeiros
- **Filtros por Data**: Exibição rápida de relatórios para "Hoje", "Últimos 7 dias", "Este Mês" ou períodos "Personalizados".
- **Ranking de Produtos**: Listagem dos drinks e porções mais vendidas do bar naquele intervalo de datas, ajudando o gestor a tomar decisões estratégicas sobre o estoque e o menu.

---

## 🛠️ Tecnologias Utilizadas

Este projeto foi construído focando em performance, estilo e manutenibilidade através de uma arquitetura Vanilla (sem frameworks pesados).

- **HTML5 & CSS3 Vanilla**: Estilização robusta focada em animações (CSS Keyframes), transições suaves e responsividade usando Flexbox e Grid. Sem uso de dependências externas como Tailwind ou Bootstrap.
- **JavaScript Moderno (ES6+)**: Lógica de interface, manipulação de DOM, cálculos de carrinho, e roteamento da Single Page Application (SPA).
- **LocalStorage API**: Simulação de um banco de dados NoSQL persistente no navegador para gerenciar os Pedidos e o Cardápio (JSON stringified).
- **Chart.js**: Renderização dos gráficos interativos no painel administrativo.
- **Google Fonts**: Tipografias modernas e estilosas (como *Boldonse*, *Bricolage Grotesque*, *Instrument Serif*, *Vibur*).

---

## 🚀 Como testar (Instruções)

1. Clone ou baixe este repositório.
2. Abra o arquivo `index.html` em seu navegador para explorar a visão do cliente.
   - Navegue pelo cardápio, adicione bebidas e conclua um pedido de demonstração.
3. Abra o arquivo `admin.html` em uma nova aba para acessar o painel gestor.
   - Veja o pedido chegando.
   - Adicione novos drinks no menu "Cardápio" e volte para a aba do cliente para ver a novidade aparecer em tempo real.
   - Gere dados de demonstração no botão do Dashboard para ver como os gráficos se comportam!

*Desenvolvido com o intuito de apresentar um sistema de PDV/Gestão moderno e esteticamente envolvente.*
