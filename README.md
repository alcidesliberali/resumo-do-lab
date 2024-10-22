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

Redundância:
- LRS: 3 cópias no mesmo datacenter (11 noves de durabilidade).
- ZRS: 3 cópias em datacenters diferentes (12 noves de durabilidade).
- GRS: Cópia em outra região (16 noves de durabilidade).
- GZRS: Combina ZRS e GRS (16 noves de durabilidade).

Tipos de dados:
- Blob: Dados não estruturados (texto, binários).
- Fila: Mensagens com até 64 KB.
- Arquivos: Compartilhamento de arquivos de rede.
- Tabelas: Dados estruturados não relacionais.

Camadas de acesso:
- Frequente: Acesso frequente.
- Esporádico: Acesso pouco frequente (30 dias).
- Frio: Acesso raro (90 dias).
- Arquivo Morto: Acesso raríssimo (180 dias), latência flexível.
- Pontos de extremidade: URLs específicas para cada tipo de armazenamento.

Ferramentas:
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

---------------------------------------
Identidade - Acesso - Segurança
---------------------------------------
- No Entra ID, em caso de excluisão de usuário, pode recuperá-lo em até 30 dias.
- Entra Connect – sincronismo on-premise(local) com azure cloud Informar o domínio próprio da empresa em Custom domain names.
- Health(Preview) – SLA Access Control IAM – Permissões se dá por Grupo de Recursos ou direto no Recurso. Defender for cloud – Cloud Native, visão geral de segurança, recomendações, multi-cloud, híbrido. DevOps Security

---------------------------------------
# Gerenciamento e Governança na Azure
---------------------------------------

---------------------------------------
Gerenciamento de Custos no Azure
---------------------------------------
- Calculadora de custos e preços: Ferramenta para estimar os custos de seus recursos no Azure antes de implementá-los.
- Gerenciamento de custos e marcas: Utilização de marcas para organizar e identificar recursos, facilitando a análise de custos por categoria ou projeto.
- TCO (Custo Total de Propriedade): Avaliação completa dos custos, incluindo não apenas os custos diretos de utilização dos recursos, mas também custos indiretos como administração, manutenção e treinamento.

---------------------------------------
Fatores que Afetam os Custos
---------------------------------------
- Tipo de recurso: O tipo de recurso utilizado (máquina virtual, banco de dados, armazenamento, etc.) influencia diretamente no custo.
- Consumo: A quantidade e a duração do uso dos recursos impactam diretamente na conta. Modelos como "pay-as-you-go" e reservas oferecem diferentes opções de custo.
- Manutenção: A prática de monitorar e otimizar o uso dos recursos, como desligar máquinas subutilizadas ou reduzir o tamanho de instâncias, pode gerar economias significativas.
- Área geográfica: O custo dos recursos varia de acordo com a região onde estão localizados.
- Tráfego de rede: A transferência de dados entre regiões e a internet pode gerar custos adicionais, especialmente para grandes volumes de dados.
- Assinatura: O tipo de assinatura (gratuita, paga, com acordos específicos) influencia os recursos disponíveis e os preços.

---------------------------------------
Azure Marketplace
---------------------------------------
- Catálogo de soluções: Oferece uma vasta gama de aplicativos e serviços de terceiros que podem ser integrados ao Azure.
- Facilidade de provisionamento: Permite encontrar, experimentar e provisionar soluções de forma rápida e fácil.
- Suporte: Os recursos adquiridos no Marketplace são suportados pelos respectivos fornecedores.

---------------------------------------
Calculando o Custo Total no Azure
---------------------------------------
- Calculadora de preços: Faz estimativa de custos nem sempre será o valor exato que será cobrado quando criar o recurso de fato, ao final gera um relatório.
- Calculadora de custo total de propriedade (TCO): Caso a empresa queira ir para a nuvem, a ferramenta compara custos de infraestrutura local x nuvem, viabilizando economia de custos.
- Gerenciamento de Custos do Azure: Monitorar, definir orçamento de gastos, colocar alertas de custo, recomendações de custo, Budget.

---------------------------------------
Marcas (Tags) no Azure
---------------------------------------
- Fornecem metadados aos recursos.
- Organizam os recursos em uma taxonomia de maneira lógica.
- Consiste em um par nome-valor.
- Úteis para reunir informações de cobrança.
- Facilitar a identificação na fatura, ajuda a filtrar na fatura.
- Não é obrigatório, se não informado o Azure adiciona um nome padrão.
- Não é herdável.

---------------------------------------
Primeiros Passos com Governança e Conformidade na Azure
---------------------------------------
Azure Policy
- Objetivo: Imposição de padrões e regras para garantir a conformidade dos recursos.
- Alcance: Aplica-se a assinaturas, grupos de recursos e recursos individuais.
- Características:
  - Flexibilidade: Permite criar políticas personalizadas para diferentes cenários.
  - Abrangência: Afeta tanto recursos novos quanto existentes.
  - Estados:
    - Não conformes: Recursos que violam as políticas.
    - Remediação: Permite corrigir recursos não conformes.
    - Conformes: Recursos que seguem as políticas.
- Exemplos de uso:
  - Definir regiões permitidas para criação de recursos.
  - Exigir tags específicas para recursos.
  - Garantir que os recursos estejam criptografados.

Bloqueios de Recursos
- Objetivo: Proteger recursos contra alterações ou exclusões não intencionais.
- Tipos de bloqueio:
  - CannotDelete: Impede a exclusão do recurso.
  - ReadOnly: Impede qualquer alteração no recurso.
- Alcance: Pode ser aplicado a assinaturas, grupos de recursos e recursos individuais.
- Considerações:
  - Impacto na mobilidade: Bloqueios em recursos individuais se movem junto com o recurso para outros grupos de recursos.
  - Uso estratégico: Deve ser utilizado com cuidado para evitar bloqueios desnecessários.

Microsoft Purview
- Objetivo: Oferecer uma visão unificada e completa dos dados da organização.
- Funcionalidades:
  - Descoberta de dados: Localiza e cataloga dados em diversas fontes.
  - Classificação de dados: Identifica a sensibilidade dos dados.
  - Linhagem de dados: Rastreamento do ciclo de vida dos dados.
  - Governança de dados: Implementa políticas de segurança e privacidade.
- Benefícios:
  - Visibilidade: Entendimento claro dos dados da organização.
  - Segurança: Proteção de dados sensíveis.
  - Conformidade: Garantia de conformidade com regulamentações.
- Ferramentas complementares:
  - Microsoft Priva: Auxilia na conformidade com a LGPD.

Portal de Confiança do Serviço
- Objetivo: Fornecer informações sobre as práticas de segurança e privacidade da Microsoft.
- Conteúdo: Documentação sobre as estratégias de segurança, conformidade e proteção de dados da Microsoft.
- Utilidade: Auxilia na realização de auditorias e avaliações de segurança.

---------------------------------------
Ferramentas de Gerenciamento e Implantação Azure
---------------------------------------

Ferramentas:
- Portal do Azure: Interface gráfica para interagir com os recursos do Azure de forma visual.
- Azure Cloud Shell/Azure PowerShell: Ambientes de linha de comando para automatizar tarefas e scripts utilizando comandos do PowerShell.
- Azure CLI: Interface de linha de comando para automatizar tarefas utilizando comandos Bash.
- Azure Arc: Plataforma que permite gerenciar recursos em diferentes nuvens (como AWS e GCP) e ambientes locais, estendendo a gestão do Azure para além da sua própria nuvem.
- ARM Templates: Arquivos JSON utilizados para definir e implantar recursos no Azure de forma declarativa e automatizada.
- Azure Bicep: Linguagem mais recente da Microsoft para definir infraestrutura, oferecendo uma sintaxe mais concisa e intuitiva que o JSON.

Conceitos:
- Infraestrutura como código: Prática de definir e provisionar infraestrutura através de código, garantindo consistência e repetibilidade nas implantações.
- Modelos ARM: Representam a infraestrutura como código no Azure, permitindo criar e gerenciar recursos de forma automatizada.

Pontos-chave:
- O Azure Cloud Shell exige uma conta de armazenamento na assinatura para funcionar.
- O Azure Arc permite um gerenciamento unificado de recursos em diferentes ambientes, promovendo a multi-cloud.
- Os modelos ARM são a base para a automação de implantações no Azure.
- O Azure Bicep oferece uma alternativa mais moderna e intuitiva aos modelos ARM tradicionais.
