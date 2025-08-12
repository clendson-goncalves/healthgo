# Roteiro para Vídeo Demonstrativo
## Sistema de Monitoramento Médico com Conformidade LGPD

**Duração**: 10-15 minutos  
**Público-alvo**: Profissionais de saúde e gestores hospitalares

---

## 🎬 INTRODUÇÃO (1-2 minutos)

### Abertura
> "Bem-vindos à demonstração do Sistema de Monitoramento Médico Multiparamétrico, desenvolvido especialmente para hospitais públicos com total conformidade à LGPD."

### Contexto
- **Problema**: Necessidade de monitoramento em tempo real com proteção de dados
- **Solução**: Sistema integrado com simulação de dispositivos médicos
- **Diferencial**: Conformidade LGPD desde o design

### Agenda
1. Visão geral do sistema
2. Demonstração do simulador de dispositivos
3. Interface web e dashboard
4. Recursos de conformidade LGPD
5. Visualizações individuais de pacientes
6. Decisões técnicas e arquitetura

---

## 🖥️ DEMONSTRAÇÃO DO SIMULADOR (2-3 minutos)

### Inicialização
\`\`\`bash
# Mostrar no terminal
node scripts/medical-device-simulator.js
\`\`\`

**Narração**:
> "O simulador lê dados de 3 pacientes reais: João Silva (65 anos, hipertensão), Maria Santos (72 anos, estável) e Pedro Oliveira (58 anos, taquicardia). Os dados são enviados a cada 200ms, simulando a frequência de 5Hz dos dispositivos médicos reais."

### Pontos a Destacar
- **Dados reais**: 450 registros por paciente (1,5 minutos de coleta)
- **Frequência**: 5Hz (200ms entre envios)
- **Robustez**: Tratamento de erros e reconexão automática
- **Logs**: Visualização em tempo real dos dados enviados

---

## 📊 DASHBOARD PRINCIPAL (3-4 minutos)

### Primeira Impressão
> "A interface foi inspirada em monitores médicos profissionais, com tema escuro para reduzir fadiga visual durante plantões longos."

### Recursos Demonstrados

#### 1. Visão Geral
- **3 pacientes** monitorados simultaneamente
- **Atualização automática** a cada 5 segundos
- **Status visual** com cores intuitivas (verde/amarelo)

#### 2. Sinais Vitais
- **Frequência cardíaca** com forma de onda ECG
- **Saturação de oxigênio** (SpO₂)
- **Pressão arterial** sistólica/diastólica
- **Temperatura corporal**

#### 3. Sistema de Alertas
- **Indicadores visuais** para valores críticos
- **Status ALERT** para Pedro Oliveira (taquicardia)
- **Códigos de cores** padronizados

#### 4. Conformidade LGPD
- **Banner de consentimento** na primeira visita
- **Indicador de proteção** em cada card
- **Dados anonimizados** por padrão

### Interações
- **Toggle de dados sensíveis** (mostrar/ocultar)
- **Botão de download** para exportação
- **Navegação** para visualização individual

---

## 🔒 RECURSOS LGPD (2-3 minutos)

### Banner de Consentimento
> "O sistema exibe automaticamente as informações sobre tratamento de dados, base legal e direitos do titular."

**Demonstrar**:
- **Base legal**: Art. 7º, II da LGPD
- **Finalidade**: Proteção da vida e monitoramento clínico
- **Direitos**: Acesso, correção, exclusão
- **Retenção**: 5 anos conforme regulamentação médica

### Anonimização Automática
**Mostrar toggle de dados sensíveis**:
- **Antes**: "João Silva" / "123.456.789-09"
- **Depois**: "João S." / "***.***.***-09"

### Auditoria
**Abrir console do navegador**:
\`\`\`javascript
// Mostrar logs de auditoria
AUDIT LOG: {
  "timestamp": "2025-01-XX...",
  "action": "VIEW_SENSITIVE_DATA",
  "patientId": "PAC001",
  "userId": "current-user-id",
  "legalBasis": "Art. 7º, II - Proteção da vida..."
}
\`\`\`

### Indicadores de Proteção
- **Ícone de escudo** em cada card
- **Badge "LGPD Compliant"** no header
- **Base legal** na barra de status

---

## 👤 VISUALIZAÇÃO INDIVIDUAL (2-3 minutos)

### Navegação
> "Clicando em 'View Details', acessamos a visualização completa do paciente."

### Recursos Demonstrados

#### 1. Informações Detalhadas
- **Dados pessoais** com controle de privacidade
- **Condições médicas** (hipertensão, diabetes)
- **Status atual** e histórico de alertas

#### 2. Sinais Vitais em Tempo Real
- **Display ampliado** com formas de onda
- **Valores numéricos** destacados
- **Indicadores de alerta** por parâmetro

#### 3. Gráficos de Tendência (24h)
- **Frequência cardíaca** ao longo do tempo
- **Pressão arterial** (sistólica/diastólica)
- **SpO₂** e **temperatura**
- **Interatividade** com tooltips

#### 4. Painel de Informações
- **Dados do paciente** com toggle LGPD
- **Condições médicas** conhecidas
- **Status de monitoramento**
- **Informações de conformidade**

---

## 🏗️ DECISÕES TÉCNICAS (2-3 minutos)

### Arquitetura Escolhida
> "Optamos por uma arquitetura em 3 camadas para garantir escalabilidade e segurança."

#### 1. Camada de Dados
- **Simulador Node.js** para dispositivos médicos
- **CSV como fonte** de dados reais
- **Frequência 5Hz** para realismo

#### 2. Camada de Aplicação
- **Next.js 14** para performance e SEO
- **API Routes** para endpoints seguros
- **TypeScript** para type safety

#### 3. Camada de Apresentação
- **React 18** com hooks modernos
- **Tailwind CSS** para design system
- **Recharts** para visualizações

### Segurança por Design
- **Criptografia AES-256-GCM** para dados sensíveis
- **HTTPS obrigatório** em produção
- **Auditoria completa** de todos os acessos
- **Anonimização por padrão**

### Performance
- **Server-side rendering** para carregamento rápido
- **Code splitting** automático
- **Otimização de imagens** nativa
- **Cache inteligente**

---

## 🎯 CONCLUSÃO (1 minuto)

### Benefícios Demonstrados
- ✅ **Monitoramento em tempo real** de múltiplos pacientes
- ✅ **Conformidade LGPD** completa e transparente
- ✅ **Interface intuitiva** para profissionais de saúde
- ✅ **Escalabilidade** para hospitais de qualquer porte
- ✅ **Segurança** de dados sensíveis de saúde

### Próximos Passos
> "O sistema está pronto para implementação em ambiente hospitalar, com documentação completa e suporte técnico especializado."

### Contato
- **Documentação**: README.md, ARCHITECTURE.md, LGPD_COMPLIANCE.md
- **Código fonte**: Disponível para auditoria
- **Suporte**: Equipe técnica especializada

---

## 📝 NOTAS PARA GRAVAÇÃO

### Preparação
- [ ] Ambiente de desenvolvimento rodando
- [ ] Simulador iniciado e funcionando
- [ ] Dados de teste carregados
- [ ] Console do navegador preparado
- [ ] Documentação aberta para referência

### Dicas de Apresentação
- **Ritmo**: Pausas entre seções para assimilação
- **Interatividade**: Mostrar cliques e navegação
- **Detalhes**: Zoom em elementos importantes
- **Contexto**: Sempre explicar o "porquê" das decisões

### Recursos Visuais
- **Setas** para destacar elementos
- **Zoom** em detalhes importantes
- **Split screen** para comparações
- **Transições** suaves entre telas

### Tempo por Seção
- Introdução: 1-2 min
- Simulador: 2-3 min
- Dashboard: 3-4 min
- LGPD: 2-3 min
- Individual: 2-3 min
- Técnico: 2-3 min
- Conclusão: 1 min

**Total**: 13-19 minutos (ajustar conforme necessário)
