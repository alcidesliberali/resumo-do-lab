# resumo dos LABS - DIO - Microsoft Azure  Essentials
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento dos labs na DIO do curso Microsoft Azure Essentials.

---------------------------------------
# Introdução ao Ambiente Cloud
---------------------------------------

No primeiro laboratório do módulo foi realizado um primeio overview do Microsoft Azure, onde foram apresentados recursos de configuração do ambiente (idioma e visual) e a instrutora navegou e deu uma breve explicação sobre os diversos serviços disponíveis, tais como: Área de Trabalho Virtual, Chaves SSH, Máquinas Virtuais, Discos, Bastions, Jump Server, Gateway, Firewall

Também foi explicado que os serviços que estão marcados como "VERSÃO PRÉVIA", são aqueles que estão em teste, portando nao há o SLA (Service-Level Agreement) que garanta o serviço, ficando a critério do profissional que está gerenciando o Azure utilizar o serviço ou não.

---------------------------------------

No segundo laboratório do módulo foram apresentados os benefícios do uso da nuvem, onde foram apesentados os valores do SLA e os tempos de inatividade máximos para cada um deles.
Também foram apresentadas algumas opções existentes no momento da criação de uma máqyuina virtual no ambiente Azure, como opções de disponibilidade, zonas de disponibilidade e como utilizar os recursos para obtenção de mais informações sobre cada uma das configurações. Por fim foram apresentadas opções de configuração de redundância de contas de armazenamento (LRS, GRS, ZRS e GZRS).

---------------------------------------

No último laboratório do módulo 1, foram apresentados os tipos de serviço de nuvem, que são:
- infraestrutura como serviço (IaaS)
- plataforma como serviço (PaaS)
- software como serviço (SaaS)

Também apresentou no portal da Azure, mais alguns detalhes na criação de máquinas virtuais, inclusive detalhes de sistema operacional, tais como Imagem, Arquitetura, rede, tamanho, disco, configurações de exposição à internet e conexões. Dando um overview sobre a quantidade de configurações existentes na criação de uma nova máquina virtual.

Por fim, apresentou alguns detalhes existentes na criação e configuração de um banco de dados SQL no ambiente azure, tais como modelos de redundância existentes.

---------------------------------------
# Conceitos Iniciais de Cloud com Azure
---------------------------------------

Componentes de Arquitetura do Azure
---------------------------------------
Foram apresentados os principais conceitos da infraestrutura do Azure, com foco em regiões, zonas de disponibilidade e hierarquia de recursos.

* Regiões e Zonas de Disponibilidade
- Redundância Geográfica: As regiões, separadas por pelo menos 300 milhas, oferecem redundância geográfica para garantir a alta disponibilidade dos seus aplicativos. Em caso de falha em uma região, você pode rapidamente failover para outra.
- Redundância Local: As zonas de disponibilidade, localizadas dentro de uma região, proporcionam redundância física dentro do datacenter. Isso significa que seus recursos podem ser replicados em diferentes zonas, minimizando o impacto de falhas locais.
- Escolha da Região: A escolha da região deve considerar fatores como latência para seus usuários, disponibilidade de serviços específicos e requisitos de conformidade (como regiões soberanas).

* Datacenters e Conectividade
- Interconexão: A interconexão dos datacenters via fibra privada garante alta performance e baixa latência na comunicação entre os recursos.
- ExpressRoute: O ExpressRoute permite conectar suas redes locais aos datacenters do Azure de forma privada e segura, eliminando a necessidade de utilizar a internet pública.

* Grupos de Recursos e Assinaturas
- Organização e Controle de Custos: A organização de recursos em grupos de recursos e assinaturas permite um melhor controle de custos, gerenciamento de acesso e aplicação de políticas.
- Flexibilidade: A possibilidade de criar múltiplas assinaturas e grupos de recursos oferece grande flexibilidade para gerenciar diferentes ambientes (desenvolvimento, teste, produção) e alocar recursos de forma eficiente.
- Hierarquia: A hierarquia de grupos de gerenciamento, assinaturas e grupos de recursos permite aplicar políticas de forma centralizada e herdar configurações para múltiplos recursos.

*Considerações Adicionais
- Regiões Soberanas: As regiões soberanas são destinadas a clientes com requisitos específicos de conformidade, como governos e organizações que lidam com dados altamente sensíveis.
- Pares de Regiões: A escolha de pares de regiões para replicação deve considerar a latência, a disponibilidade dos serviços necessários e os requisitos de recuperação de desastre.
- Alta Disponibilidade: Para garantir a alta disponibilidade dos seus aplicativos, é fundamental utilizar as funcionalidades de replicação e failover do Azure, além de implementar boas práticas de design e desenvolvimento.
- Segurança: A segurança é um aspecto fundamental da infraestrutura do Azure. Utilize recursos como redes virtuais, grupos de segurança de rede e autenticação multifator para proteger seus recursos.

---------------------------------------
Máquinas virtuais
---------------------------------------
- Cada Zona = 1 datacenter.
- Desconto Spot do Azure – Utilizar a carga de trabalho ociosa do Azure, pode-se desligar a máquina se o Azure precisar da capacidade computacional para cliente pagante preço normal, usar apenas em desenvolvimento.
- Para desligar e ligar automaticamente – tem que fazer conta de serviço, pois por padrão só tem o desligar automaticamente.
- Tipo de Host – Pessoal ou Pool

---------------------------------------
Armazenamento no Azure
---------------------------------------
O Azure oferece diversas opções de armazenamento para diferentes necessidades, com diferentes níveis de redundância, tipos de dados e camadas de acesso.

*Redundância:
- LRS: 3 cópias no mesmo datacenter (11 noves de durabilidade).
- ZRS: 3 cópias em datacenters diferentes (12 noves de durabilidade).
- GRS: Cópia em outra região (16 noves de durabilidade).
- GZRS: Combina ZRS e GRS (16 noves de durabilidade).

*Tipos de dados:
- Blob: Dados não estruturados (texto, binários).
- Fila: Mensagens com até 64 KB.
- Arquivos: Compartilhamento de arquivos de rede.
- Tabelas: Dados estruturados não relacionais.

*Camadas de acesso:
- Frequente: Acesso frequente.
- Esporádico: Acesso pouco frequente (30 dias).
- Frio: Acesso raro (90 dias).
- Arquivo Morto: Acesso raríssimo (180 dias), latência flexível.
- Pontos de extremidade: URLs específicas para cada tipo de armazenamento.

*Ferramentas:
- Azure Data Box: Equipamento físico para transferir grandes volumes de dados.
- AzCopy: Utilitário de linha de comando para copiar e sincronizar dados.
- Gerenciador de Armazenamento do Azure: Interface gráfica para gerenciar o armazenamento.
- Sincronização de Arquivos do Azure: Sincronização bidirecional entre nuvem e local.

---------------------------------------
Identidade, Acesso e Segurança
---------------------------------------
- Serviços de diretórios – Entra ID, Entra Domain Métodos de autenticação – Logon único SSO, MFA, sem senha(exemplo Windows Hello). Modelos de segurança
- Identidades Externas e acesso a convidado. Acesso condicional do Entra – baseado em sinais.
- Controle de Acesso baseado em função (RBAC)
- Conceito de confiança zero. Modelo de defesa em profundidade. Microsoft Defender para nuvem.

---------------------------------------
Entra ID e Domain Services
---------------------------------------
- Serviço de gerenciamento de identidades e acesso baseado em nuvem do Azure. 
- Semelhante ao antigo Active Directory (AD). 
- Domínio Gerenciado na nuvem – é possível replicar os novos usuários do AD Local para a Nuvem, mas usuários criados na nuvem não integram com AD Local, é possível integrar apenas alterações de senha.

---------------------------------------
Autenticação e Autorização
---------------------------------------
- Autenticação – identifica a pessoa ou serviço buscando acesso a um recurso
- Autorização – Determina o nível de acesso de uma pessoa ou serviço autenticado.
- MFA – Autenticação multifator – algo que você sabe, algo que você possui e algo que você é.
- B2B – ID externa do Microsoft Entra, parceiros, fornecedores outros colaboradores.
- Azure AD B2C – Consumidores do seu aplicativo privado. Autenticação pelo ID do Facebook, Google por exemplo.

---------------------------------------
Acesso Condicional
---------------------------------------
- Associação de usuário ou grupo Local do IP, Dispositivo, Aplicativo, Detecção de risco.
- Controle de acesso baseado em função - RBAC (rule base access control)
- Gerenciamento de acesso de granularidade fina.
- Definir tarefas dentro da equipe e permitir somente a quantidade necessária
-  Habilitar acesso ao portal do Azure e o controle de acesso aos recursos.
-  Acesso herdável: Assinatura Grupo de recursos

Ou seja, se tive acesso a Assinatura, terá acesso a tudo que está abaixo dela.

- Confiança Zero – Protege os ativos em qualquer lugar com uma política central, criar várias camadas de segurança.
- Ataques contra uma camada são isolados das camadas subsequentes.
- Defender para Cloud – aplicação cloud native, proteção contra ameaças nos datacenters Azure e locais.
- Analisa também AWS e GCP.
- Faz recomendações de segurança; Detectar e bloquear malware; Analisar e identificar ataques potenciais; Controle de acesso just-in-time para portas.


