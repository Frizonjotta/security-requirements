# Requisitos de Segurança

## SR-001 — [Política de Senhas Fortes e Autenticação de Dois Fatores (2FA)]

**Requisito:**
[A aplicação deve exigir senhas com no mínimo 12 caracteres, contendo letras maiúsculas, minúsculas, números e caracteres especiais, além de exigir a ativação e validação de Autenticação de Dois Fatores no momento do login para todos os tipos de usuários.]

**Categoria:**
[Autenticação]

**Prioridade:**
[Alta]

**Motivo:**
[Evita ataques de força bruta, sequestro de contas por senhas fracas ou vazadas e garante um fator extra de verificação de identidade.]

---

## SR-002 — [Controle de Acesso Baseado em Objeto]

**Requisito:**
[O backend deve validar explicitamente se o usuário autenticado possui permissão legítima sobre o recurso solicitado antes de servir qualquer documento ou dado acadêmico, impedindo que um aluno acesse arquivos pertencentes a outros usuários.]

**Categoria:**
[Autorização]

**Prioridade:**
[Critíca]

**Motivo:**
[Previne a vulnerabilidade, garantindo o sigilo e a privacidade dos dados e documentos dos alunos conforme exigido pela LGPD.]

---

## SR-003 — [Validação e Restrição do Tipo de Arquivo no Upload]

**Requisito:**
[O sistema deve validar os arquivos enviados por meio de uma lista de extensões permitidas (ex.: PDF, PNG, JPG), rejeitando qualquer arquivo executável ou de formato não autorizado.]

**Categoria:**
[Upload]

**Prioridade:**
[Alta]

**Motivo:**
[Impede a execução remota de código no servidor provocada pelo upload de scripts maliciosos.]

---

## SR-004 — [Limite do Tamanho de Arquivos e Cota de Armazenamento]

**Requisito:**
[O sistema deve limitar o tamanho máximo individual de cada arquivo enviado e estabelecer uma cota máxima de upload por usuário.]

**Categoria:**
[Upload]

**Prioridade:**
[Média]

**Motivo:**
[Protege a infraestrutura contra ataques de negação de serviço por esgotamento de espaço em disco e consumo excessivo de largura de banda.]

---

## SR-005 — [Registro e Auditoria de Logins]

**Requisito:**
[A aplicação deve registrar em log de auditoria todas as tentativas de login (inclusive falhas), armazenando o ID do usuário, data/hora em UTC, endereço IP de origem e o identificador do navegador (User-Agent).

Categoria:]

**Categoria:**
[Logs]

**Prioridade:**
[Alta]

**Motivo:**
[Permite o rastreamento de comportamentos suspeitos, investigação pós-incidente e identificação de ataques de força bruta ou acessos não autorizados.]

---

## SR-006 — [Gestão e Expiração Automática de Sessões]

**Requisito:**
[As sessões de usuários devem ser encerradas automaticamente após 15 minutos de inatividade.]

**Categoria:**
[Sessão]

**Prioridade:**
[Alta]

**Motivo:**
[Reduz a janela de oportunidade para sequestro de sessão.]

---

## SR-007 — [Tratamento Seguro de Erros e Exceções]

**Requisito:**
[O sistema deve capturar todas as exceções globais e exibir apenas mensagens genéricas ao usuário final, mantendo os detalhes técnicos  exclusivamente nos logs internos do servidor.]

**Categoria:**
[Dados]

**Prioridade:**
[Média]

**Motivo:**
[Evita o vazamento de informações do sistema, o que impedirá que atacantes mapeiem a arquitetura interna e vulnerabilidades da aplicação.]

---

## SR-008 — [Armazenamento Isolado e Renomeação de Documentos]

**Requisito:**
[Os arquivos enviados pelos usuários devem ser armazenados fora do diretório público da aplicação web e devem ter seus nomes originais substituídos por identificadores únicos universais.]

**Categoria:**
[Upload]

**Prioridade:**
[Alta]

**Motivo:**
[Impede a navegação direta por URLs nos diretórios do servidor e previne a sobrescrita não autorizada de arquivos existentes.]
