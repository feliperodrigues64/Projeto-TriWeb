# Projeto-TriWeb
Rede MESH de comunicação colaborativa em tempo real para Inclusão Digital

TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
TriWeb
Comunicação em Tempo Real com WebRTC
No Rio Grande do Sul
Escopo do Projeto:
O Projeto TriWeb é uma proposta de iniciativa popular, para criação de uma plataforma independente de ambiente operacional baseada em nuvem para fomentar a inclusão social e digital das comunidades de baixa renda através da disponibilização de recursos como Rede Social Exclusiva, Sistemas de Chat, VideoChat e Videoconferência, bem como transmissão de dados e compartilhamento de telas em tempo real e telefonia sobre IP VoIP.
O Projeto, doravante apelidado de TriWeb, consiste em desenvolver uma solução de plataforma colaborativa de Comunicação em Tempo Real que fomente a inclusão social e digital das comunidades carentes, ao disponibilizar toda uma infraestrutura de conhecimento e de telecomunicações, web, webdesign, produção de vídeo, áudio e conteúdos digitais dos mais diversos, além de proporcionar ferramentas de comunicação de áudio, vídeo e dados em tempo real ao usuário final, ou seja o cidadão! O diferencial desta proposta é que ela se baseia exclusivamente na criação e desenvolvimento de um Backend Xen, virtualizando servidores Node.js on demand, que na verdade não necessita de software ou app algum instalado para oferecer nenhum dos recursos, pois baseado na API WebRTC do Google, o sistema roda 1200% no navegador, utilizando apenas um servidor Node como servidor de sinalização.
Extrapolando a ideia de um projeto unicamente social pode-se vislumbrar uma infinidade de aplicações científicas acadêmicas ou mesmo na iniciativa privada, uma vez que utilizaremos plataforma opensource e que com certeza contribuirá muito no sentido de fomentar uma rede de comunicação satisfatória às necessidades sociais, educacionais e existenciais de nossa sociedade e às expectativas da comunidade acadêmica ao prover um vasto terreno de pesquisas.
Para tanto iniciamos esta proposta com uma infraestrutura simples e enxuta de microservidores individuais distribuídos em postes inteligentes, onde desde já denominaremos como conjunto de postes referente a uma determinada e específica área geográfica como sendo uma “Célula WTRC”, ou seja “Célula WebRTC”. Cada unidade de uma célula WRTC, ou poste, é composto de: uma CPU ARM Quad Core, Um Switcher – Router Gigabit Ethernet com interfaces Wireless para 2.4, 3 e 5 Gigahertz independentes, Uma antena local para 2.4 Gigahertz e duas antenas mini parabólicas para 3 ou 5 Gigahertz. Cada poste, recebe originalmente o sinal da faixa entre 3 e 5 Gigahertz de um “Backend público” (podemos incubar na PUC/UFRGS) virtualizado por servidores Xen, que estarão dando suporte às instâncias necessárias de servidores Node.js. Destes, o sinal de internet via WiFi chega à primeira unidade (poste), que ao receber o link de internet, redistribui o seu sinal em modo local através da antena de 2.4 Gigahertz e ao mesmo tempo reenvia o sinal adiante na célula através da mini parabólica criando assim uma Célula WTRC. A célula local, possui um node.js em um Raspberry Pi 3 Model B, que funciona como sservidor de sinalização local, reduzindo o overhead global da rede ao isolar as comunicações locais ponto a ponto dentro da célula.
TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
Servidor do sistema:
No andar da carruagem me deparei com o Node.js, um servidor extremamente ágil e leve, projetado
para executar nativamente javascript do lado do servidor em tempo real e com um novo conceito de
conexões em thread única, diferente de um APACHE ou IIS, que usam sum conceito de pool de conexões
em multithread que gera enorme latência e precisam de um pesado backend. Como trabalharemos
muito mais com comunicação ponto a ponto (peer-to-peer em tempo real, onde tudo roda no cliente, o
Node.js hospeda uma aplicação de maneira tão sutil, que não acrescenta overhead algum, pois o Node
serve apenas como servidor de sinalização entre os “peers” no webRTC e tudo mais é feito no próprio
navegador cliente.
Uma das características nativas de Node.js mais interessante é o use de
Servidores ICE (TURN/STUN) fazendo NAT transversal e transpondo as barreiras de redes NAT sob Firewalls
e o suporte nativo às redes MESH, arquitetura básica das células RTC propostas no projeto.
NODE.js (Node,js foi criado por Ryan Dahl em 2009 e é baseado no UNIX)
“Conta-se que Ryan Dahl inspirou-se a criar o Node.js após observar uma (barra de progresso) no Flickr e
perceber que ela na verdade não mostrava o progresso da transferência em tempo real e então decidiu
criar um servidor que mostrasse as informações em tempo real. A primeira implementação de Node,js
foi um servidor chamado ng-ingx.” (Não lembro se esse antigo nome, é referência ao Unix).
Um sistema em Node.js é desenvolvido quase duas vezes mais rápido com menos recursos humanos, com
33% menos linhas de código construído com 40% menos arquivos.” Node.js atende o dobro de
requisições por segundo em relação a uma aplicação Java tradicional, e o mais interessante é que esta
relação foi obtida com testes de Node.js rodando em um único core e Java rodando em cinco cores. Nos
testes foram reduzidos em 33% o tempo de resposta de cada página.
Há três definições um pouco distintas entre si de Node.js, então publico ambas para entendimento mais
generalizado.
1 - É uma plataforma orientada a eventos, do lado do servidor, que permite a criação de aplicações web escaláveis. Os
programas que são desenvolvidos com esta plataforma são escritos em JavaScript e são assíncronos, o que permite
diminuir o overhead e aumentar a escalabilidade.
2 – Nod.js é um interpretador de JavaScript do lado do Servidor, criado em cima do javascript V8, que é o “Mecanismo de
JavaScript V8” do seu navegador, seja Chrome, FireFox ou Ópera. Além disso ele conta com outras bibliotecas que o
auxiliam no gerenciamento de processos, como por exemplo a Libv.
3 – O Node.js age como uma ponte entre uma API que pode ser acessada via JavaScript e funções em C++ do JavaScript
Engine V8.
Contém uma biblioteca de servidor HTTP, que permite rodar aplicações web sem usar um servidor típico HTTP (ex.
Apache, IE, Edge). Esta plataforma permite a criação de aplicações que tenham por objetivo funcionar completamente em
tempo real, como por exemplo, streaming de voz ou vídeo, ou então serviços de chat, compartilhamento de arquivos.
Implementa um repositório de módulos, onde cada um tem uma funcionalidade diferente. Cada um destes módulos pode
ser instalado a partir de Node Package Manager (npm) [43]. O npm, além de servir para instalar os módulos, permite
também tratar da gestão de versões e gestão de dependências. Um dos módulos que permite desenvolver aplicações que
atuem em tempo real e que utilizem uma API tipo WebSockets, é o socket.io. Este permite que WebSockets e tempo real
estejam presentes em qualquer browser, além disso ainda fornece multiplexing, escalabilidade horizontal, odificação e
descodificação em JavaScript Object Notation (JSON).
TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
Node.js utiliza-se de um sistema de requisições em thread única rodando um loop de eventos em contraponto ao sistema
de requisições “Multi Threaded” do Apache e ISS, onde há uma enorme ociosidade de threads aguardando requisições. O
que lhe garante ótimo desempenho e baixíssima latência.
Sistema de Requisições Tradicional (Apache, IIS) e o loop de eventos do node.js
Diferente do Apache, Node.js possui uma única thread executando um loop de eventos, que trata uma
requisição assim que ela chega, delega essa requisição a um conjunto de threads assíncronas liberando
assim o evento do loop para seguir em frente. Executando javascript do lado do servidor com
comunicação nativa com o javascript engine V8 do Google Chrome, Firefox e Ópera.
Ao escolher o Node.js abriremos mão de uma série de legados já em obsolescência ou em simples
desuso, abrindo as portas para tecnologias novas e mais eficazes de colaboração e telecomunicações. Ao
migrar para Node.js já podemos pensar em Bancos de Dados NoSql como MongoDB, Json, AngularJs, e
modelos de aplicação Multilayer que decolam do MVC de “ Model View Controller” para “Model-View-
View-Model” MVVM em aplicações ponto a ponto em tempo real e demais variações de Modelos de
Aplicação Multilayer propostas pela plataforma.
TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
Modelo de Desenvolvimento MVC
Model View Controller
No modelo de desnvolvimento MVC, nos livramos de décadas de problemas em modelo de software, pois
diferente das aplicações Client-Server e tree tier (três camadas) ou Multi Layer (Mais de três camadas) dos
modelos clássicos de objetos e objetos distribuídos que residiam em uma estrutura composta basicamente
de três camadas ou Layers. São eles: 1-Camada de Apresentação, 2- Camada de Negócio ou Aplicação e 3-
Camada de Dados. Essa Arquitetura perdurou por anos superando até mesmo a queda da Arquitetura
Client-Server clássica, em detrimento da arquitetura distribuída, que ainda amadurecia. Não se pode deixar
de citar os Sistemas Legados. a Integração com Plataforma Alta (Mainframes) e Sistemas Transacionais. No
MVC é diferente, extrapolando o conceito de aplicação multi layer, ou multicamadas o MVC explora uma
abordagem conceitual diferente. As informações residem no Modelo (Model) o Controller gerencia as
requisições destas e sua transferência e a view é a evolução da camada de apresentação.
No MVC você vê a “view” de um escopo, solicita ao controller de dentro do escopo, o Controller pega do
Model a informação requisitada e devolve diretamente para a view.
O Modelo de Desenvolvimento MVC aliado ao Modelo de Aplicação SPA proporciona um desempenho global e
tempos de resposta jamais vistos antes em Servidores Web.
TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
Modelo de Aplicação SPA (Single Page Application)
No modelo de aplicação SPA, apenas uma parte da view muda e a outra permanece fixa. Isso traz melhoras na
experiência do usuário e diminuição no tráfego de dados por não precisar renderizar tudo toda vez.
Na verdade você possui uma única página como “background” e esta recebe e envia código html e javascript,
alterando-se de acordo com a lógica do sistema. A impressão é que estamos navegando em várias páginas. SPA é
uma evolução do conceito de páginas dinâmicas. Isto nos proporciona um grande avanço, uma vez que a lógica do
sistema fica muito bem definida dentro de um conceito extremamente eficiente.
Ao iniciar os trabalhos com essa nova arquitetura uma série de questionamentos e dúvidas surge, uma vez que não é
nosso ambiente de costume, e que certamente há conceitos, regras de sintaxe e semântica específicos de vários
módulos que compõe o sistema, características específicas estas que são o âmago de Node.js, como Javascript,
jquery, JSON, Express, EJS, AngularJs, WebRTC, Sinalização com protocolos TCP/IP, H323, SIP, etc.
Ao chegarmos aqui, mais um leque de infinitas possibilidades se abre, pois a integração entre Navegador Web e Linha Telefônica
Convencional através de integração WebRTC-SIP traz a convergência necessária para dar suporte à suave migração de uma plataforma de
telefonia obsoleta parta uma nova realidade de Telecomunicação em Tempo Real via Navegador com a API WebRTC.
TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
Application CASE
Desenvolvendo para a Comunidade
Projetar uma aplicação de Rede Social e recursos de computação colaborativa para uma comunidade de
baixa renda é algo que deve ser amplamente discutido, pois não se pode perder de vista as premissas de
não reinventar a roda, o sistema deve adaptar-se à realidade do usuário e promover ganho de alguma
espécie. Deve-se utilizar energia limpa, deve ser de fácil descarte e substituição com ótima relação custo
benefício. Deve fomentar a inclusão digital através da própria manutenção e aprimoramento da
plataforma. Deve gerar espaço para a criatividade tornar-se conhecimento científico. Deve ser abrangente
À todas as áreas do conhecimento humano. Deve promover basicamente o crescimento da comunidade de
diversas formas.
A alimentação elétrica do sistema é proposta como alimentação solar fotovoltaica em virtude da
necessidade de se utilizar energias limpas, bem como promover a autonomia do sistema.
Como utilizaremos NodeJs e Raspberry PI, não se pode deixar de fora a conectividade com Arduino e
deixar claro que poderemos controlar desde luzes até bombas hidráulicas e sistemas de irrigação.
O Servidor NodeJs será utilizado também como servidor VoIP, proporcionando uma rede de telefonia
sobre IP, barateando assim as comunicações telefônicas da comunidade uma vez que dentro da mesma
não se pagariam ligações telefônicas.
Dimensões:
A princípio o projeto deve ser implementado em uma região com a dimensão de um bairro, expandindo-se
geograficamente em virtude das demandas locais.
OBS Técnica:
Deve sempre manter a compatibilidade das interfaces globais para integrar diversas comunidades
independentes e com aplicações e características singulares da individualidade microrregional.
Requisitos mínimos de recursos não financeiros:
É necessário espaço geográfico para instalação de um servidor, este servidor, painéis solares, baterias,
quatro linhas telefônicas, uma para internet e outras três para o Servidor SIP (Telefonia).
Tecnologias envolvidas:
Para viabilizar o projeto foram definidas algumas tecnologias chave com base nos mais modernos conceitos de
desenvolvimento de software.
TriWeb Rede MESH Comunitária
Copyright © 2017 Felipe Rodrigues - FullTime Technology
1 – [ Servidor ] Optamos por utilizar inicialmente Node.js como servidor por suas características de leveza,
portabilidade e desempenho em aplicações web. Fica ainda em pauta a possibilidade de uso de outros servidores
leves como Chrome Web Server, Wamp, etc. A se decidir em tempo de desenvolvimento da aplicação piloto.
2 – [ Linguagens e Framework de Desenvolvimento ] As linguagens e frameworks de desenvolvimento envolvidos são
Javascript, jQuery, Json, Express, AngularJs, Mongoose bem como C, C++ e C# em casos específicos.
3 – [ Bancos de Dados ] Para este tipo de aplicação optou-se por utilizar Bancos de Dados padrão NoSQL e em
primeira instância utilizaremos MongoDB
4 – [ IoT Devices ] Para obter total abrangência de novas tecnologias escolhemos utilizar no projeto uma interface
para conectividade com Internet das Coisas IoT e neste projeto utilizaremos Rapberry PI 3 Model B como plataforma
de hardware.
EDITANDO DAQUI PARA BAIXO...
A API webRTC
A API webRTC é o coração por trás de toda a plataforma, pois é o webRTC quem faz toda a integração
entre tecnologias além do suporte à comunicação ponto a ponto em redes MESH.
Mas afinal o que é webRTC?
Bem, vamos entender um pouco sobre essa nova tecnologia que tem apaixonado os entusiastas de Open
Source. webRTC é uma API escrita em C++ , que é executada junto ao javascript engine V8 dos
Navegadores Chrome, Firefox e Ópera. webRTC roda nativamente na maioria dos navegadores de
dispositivos móveis como Smartphones e Tablets. oferecendo suporte à comunicação em tempo real
através da web, daí o nome WebRTC, de “Web Real Time Communications”.
Por ser nativo do navegador web o webRTC nos oferece a capacidade de realizar ciosas antes nunca
imagináveis, pois podemos criar desde simples aplicações de chat até uma sala de videoconferência via
web sem instalar um plugin sequer! Não é preciso software instalado do lado do cliente, pois tudo roda
“dentro” do navegador.
