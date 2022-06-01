# networking-study-notes | introdução às redes
## LANs e WANs
a infraestrutura de rede variam muito em termos de:
- tamanho da área de cobertura
- número de usuários
- quantidade e tipos de serviços fornecidos
- área de responsabilidade

resumindo:
- LAN - área local
- WAN - área extensa

> as WANs conectam duas ou mais LANs

## a internet
a internet em resumo é um conjunto de várias redes conectadas globalmente

### intranets e extranets
- intranet é uma rede privada de LANs e/ou WANs pertencentes a uma organização
- extranets é a parte da rede que pode ser utilizada por usuários externos

## arquitetura de redes
existem 4 características básicas que arquitetos de rede devem se atentar para atender a expectativa dos usuários:
- tolerância a falhas
- escalabilidade
- qualidade de serviços (QoS)
- segurança

## camadas de rede
### modelo OSI
O modelo OSI foi desenvolvido para ajudar os equipamentos de diferentes modelos e fabricantes a se comunicarem através das redes espalhadas pelo mundo todo
- física: os protocolos da camada física descrevem o mecânico, elétrico, meios funcionais e processuais para ativar, manter e desativar conexões físicas para uma transmissão de bits de e para uma rede dispositivo
- enlace de dados: os protocolos da camada de enlace descrevem métodos para troca de dados quadros entre dispositivos em uma mídia comum
- rede: fornece serviços para trocar as partes individuais de dados através da rede entre dispositivos finais identificados
- transporte: define serviços para segmentar, transferir e remontar os dados para comunicações individuais entre o fim dispositivos
- sessão: fornece serviços para a camada de apresentação para organizar seu diálogo e gerenciar o intercâmbio de dados
- apresentação: fornece uma representação comum dos dados transferidos entre serviços de camada de aplicativo
- aplicação: a camada de aplicação contém protocolos usados para processo a processo comunicações

### modelo TCP/IP
- acesso à rede: controla os dispositivos de hardware e o meio físico que formam a rede
- internet: determina o melhor caminho pela rede
- transporte: permite a comunicação entre vários dispositivos diferentes em redes distintas
- aplicação: representa dados para o usuário, além do controle de codificação e de diálogo

### segurança e otimização
- firwalls por padrão bloqueiam tudo, devemos configurar somente o tráfego que precisamos para atender a arquitetura projetada
- IDS informa o administrador da rede quando ações maliciosas ocorreram, é um sistema passivo
- IPS faz o monitoramento ativo da rede e irá tomar uma ação quando detectar ações maliciosas
- load balancer divide o tráfego entre os diversos dispositos que possuem o mesmo conteúdo
- proxy server age como se fosse um dispositivo cliente para realizar requisições, proxy reverso se comporta como se fosse o servidor

### VPN
é a conexão usada por hosts remotos para acessar uma rede privada através de um túnel criptografado através de uma rede pública
- uma vez conectado, o host não é mais considerado remoto, mas sim, um host local
tipos de VPN:
- site-to-site
- remote-access VPN / host-to-site VPN
- host-to-host VPN / SSL VPN
protocolos usados pela VPN:
- IPsec
    - authentication header (AH) - autentica
    - encapsulating security payload (ESP)
    - operam em um ou dois modos:
        - transport mode
        - tunnel mode
    - implementa internet security association and key management (ISAKMP) por padrão
- GRE
    - é um sistema de tunelamento que é capaz de engapsular uma variedade grande de protocolos da camada de rede
    - pode ser usado para criar um tunel dentro de uma conexão IPsec
- PPTP / point-to-point tunneling protocol
    - é um sistema mais antigo de VPN que suporta o sistema de discagem
- TLS / transport layer security protocol
    - é um protocolo criptográfico usado para criar uma conexão segura criptografada entre dois dispositivos finais ou aplicações
    - usa criptografia assimétrica para autenticar end points e então negocia uma chave de segurança simétrica que é usada para encriptar a sessão
    - substituiu o SSL
    - funciona na camada 5 e acima do modelo OSI
    - o uso mais comum é para criar uma sessão de internet segura e criptografada (SSL VPN)
    - todos os browsers modernos suportam o TLS
