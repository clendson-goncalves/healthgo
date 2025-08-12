# Multiparametric Monitoring

Este sistema simula o monitoramento de dispositivos médicos via comunicação serial (nesta versão carregamos os dados dos arquivos CSV enviados), exibindo dados vitais em tempo real através de uma interface web segura e intuitiva, com aderência à LGPD

Projetando a expansão do software e o seu uso em ambito nacional e internacional, foi escolhido o idioma Inglês (en-US) para a interface e codificação

## Segurança e LGPD

Ver documentação completa em [LGPD_COMPLIANCE.md](./LGPD_COMPLIANCE.md)

## Arquitetura

Ver documentação técnica em [ARCHITECTURE.md](./ARCHITECTURE.md)

## Funcionalidades
- Leitura de dados reais dos arquivos CSV (pasta /data)
- API de sinais vitais funcionando
- Monitoramento simultâneo de múltiplos pacientes (PAC001, PAC002, PAC003)
- Visualizações Individuais por paciente com histórico dos dados.
- Simulador de Dispositivos com leitura contínua de dados CSV (5Hz)
- Monitor de Conexão em Tempo Real
- Alertas Clínicos com sistema de notificações para valores críticos

### Conformidade LGPD
- Pseudoanonimização de nomes e CPF
- Criptografia AES-256-GCM
- Controle de Privacidade através do toggle para mostrar/ocultar dados sensíveis
- Exportação de Dados que permite download seguro de dados clínicos de todos os pacientes e também individual

### Requisitos Visuais
- Cards de monitoramento com waveforms
- Páginas individuais de pacientes
- Exportação de dados CSV
- Toggle de dados sensíveis


## Próximas implementações

- **Registro completo de logs e auditoria**: Monitoramento detalhado de acessos e operações para garantir rastreabilidade.
- **Conformidade com LGPD, incluindo temporalidade dos dados**: Controle rigoroso da retenção, anonimização e eliminação de dados pessoais.
- **Conexão segura ao banco de dados**: Criptografia das comunicações e controle de acesso robusto aos dados.
- **Gestão avançada de usuários com perfis e permissões**: Diferenciação clara entre funções (médico, enfermeiro, técnico, administrador) com permissões específicas.
- **Leitura de dados em tempo real via API**: Integração com sistemas de monitoramento para atualização instantânea dos sinais vitais.
- **Rotação periódica de chaves criptográficas**: Automatização da troca de chaves para aumentar a segurança da criptografia.
- **Obrigatoriedade do uso de HTTPS para todas as comunicações**: Garantia de comunicação segura e proteção contra interceptações.
- **Certificate pinning em ambiente de produção**: Prevenção contra ataques do tipo man-in-the-middle (MITM) ao validar certificados no cliente.
- **Auditoria rigorosa de todos os acessos a dados sensíveis**: Registro detalhado de quem acessou, quando, qual dado e com qual justificativa.
- **Justificativa obrigatória para acesso completo aos dados**: Coleta e armazenamento do motivo para acessos críticos, facilitando auditorias.
- **Controle de acesso baseado em funções (RBAC)**: Implementação de permissões granulares conforme perfil do usuário.
- **Permissões específicas por tipo de dado**: Gestão diferenciada para dados pessoais, clínicos e outros tipos sensíveis.
- **Sessões com timeout automático**: Desconexão após período de inatividade para aumentar a segurança.
- **Autenticação multifator (MFA) obrigatória**: Camada extra de proteção no processo de login para prevenir acessos não autorizados.
- **Tokens JWT com tempo de expiração curto**: Minimização do risco de uso indevido de tokens.
- **Revogação imediata de acessos**: Mecanismo para invalidar rapidamente permissões e tokens em caso de necessidade.

## Instalação e Execução

### Pré-requisitos

- Node.js 18+ 
- npm ou yarn

### 1. Clonagem do Repositório GitHub


### 2. Instalação das Dependências

\`\`\`bash
npm install
\`\`\`

### 3. Configuração do Ambiente

Execute o comando para gerar a chave de criptografia:

\`\`\`bash
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
\`\`\`

Crie um arquivo `.env.local` na raiz do projeto:

\`\`\`env
ENCRYPTION_KEY=sua-chave-de-criptografia-segura-aqui
\`\`\`

### 3. Executar a Aplicação Web

\`\`\`bash
npm run dev
\`\`\`

A aplicação estará disponível em `http://localhost:3000`

## Interface do Usuário

### Dashboard Principal
- Visualização de todos os pacientes simultaneamente
- Atualização automática a cada 5 segundos
- Indicadores de status e alertas
- Controles de privacidade LGPD

### Visualização Individual
- Dados detalhados do paciente
- Gráficos de tendência
- Histórico de sinais vitais
- Informações médicas completas

### Exportação dos Dados em CSV
- Exportação de todos os pacientes
- Exportação individual
- Dados pessoas com Anonimização e criptografia

### Recursos de Segurança
- Anonimização automática de dados sensíveis conforme LGPD
- Controle de visibilidade de informações pessoais

## Tecnologias Utilizadas

- **Frontend**: Next.js 14, React 18, TypeScript
- **Styling**: Tailwind CSS, shadcn/ui
- **Charts**: Recharts
- **Backend**: Next.js API Routes
- **Simulação**: Node.js com fetch nativo
- **Segurança**: Crypto nativo, LGPD compliance

## Segurança e LGPD

Ver documentação completa em [LGPD_COMPLIANCE.md](./LGPD_COMPLIANCE.md)

## Arquitetura

Ver documentação técnica em [ARCHITECTURE.md](./ARCHITECTURE.md)