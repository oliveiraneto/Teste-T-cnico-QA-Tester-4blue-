**🧪 Teste Técnico – QA Tester**

Microssistema de Autenticação – 4blue
<br>
<br>

**📌 Objetivo**

Realizar uma análise exploratória do microssistema disponibilizado, identificando possíveis problemas relacionados a:

funcionalidade

experiência do usuário

validação de dados

segurança básica

consistência da interface

<br>
<br>

**🔎 Estratégia de Teste**

Foi aplicada a técnica de teste exploratório manual, focando principalmente nos seguintes fluxos do sistema:

cadastro de usuário

login

validação de formulário

comportamento da interface

validação de dados de entrada

segurança básica de autenticação

Durante os testes foram utilizados cenários de uso comuns e também entradas inválidas ou inesperadas, buscando identificar possíveis falhas no sistema.
<br>
<br>

**🖥 Ambiente de Teste**

Os testes foram realizados no seguinte ambiente:

Sistema Operacional: Windows 10
Navegador: Google Chrome
Tipo de teste: Teste manual exploratório

🛠 Ferramentas Utilizadas

Google Chrome

Chrome DevTools

Teste manual exploratório

<br>
<br>

**🐞 Bugs Identificados**
<br>
<br>
**Bug 1 – Quebra de layout no campo de telefone e confirmar senha**

**Descrição**

Na tela de criação de conta, o campo de telefone e confirmar senha ultrapassam o limite visual do container do formulário, causando quebra no layout da interface.

Passos para reproduzir

Acessar a tela Criar conta

Observar os campos descritos

**Resultado atual**

O campo ultrapassa o limite visual do card do formulário.

**Resultado esperado**

O campo deve respeitar os limites do container e manter o alinhamento com os demais campos.

Severidade: Baixa
Prioridade: Baixa
<br>
<br>
**Bug 2 – Mensagem de erro inesperada após login**

**Descrição**

Após realizar login com sucesso, o sistema apresenta uma mensagem "Erro inesperado" no canto inferior da tela.

Passos para reproduzir

Criar uma conta

Realizar login

Observar o canto inferior da tela

**Resultado atual**

Mensagem de erro aparece mesmo após login bem-sucedido.

**Resultado esperado**

Nenhuma mensagem de erro deveria aparecer após autenticação válida.

Severidade: Média
Prioridade: Média
<br>
<br>
**Bug 3 – Falha na validação de formulário**

**Descrição**

O sistema não valida corretamente os campos do formulário de cadastro, permitindo:

criação de conta sem preencher campos

criação de conta com senha menor que 8 caracteres

criação de conta sem caractere especial

login com credenciais inválidas

Isso indica ausência de validação adequada no formulário.

**Cenário 1 – Cadastro sem preencher dados**

**Passos**

Acessar tela Criar conta

Não preencher nenhum campo

Clicar em Criar conta

**Resultado atual**

Conta é criada sem dados.

**Resultado esperado**

Sistema deveria exigir preenchimento dos campos obrigatórios.

**Cenário 2 – Senha inválida**

**Passos**

Preencher formulário

Inserir senha menor que 8 caracteres

Clicar em Criar conta

**Resultado atual**

Conta criada normalmente.

**Resultado esperado**

Sistema deveria exigir senha com:

mínimo de 8 caracteres

pelo menos 1 caractere especial

**Cenário 3 – Login com senha inválida**

**Passos**

Criar conta com senha inválida

Realizar login

**Resultado atual**

Login realizado normalmente.

**Resultado esperado**

Sistema deveria bloquear autenticação com credenciais inválidas.

Severidade: Crítica
Prioridade: Alta
<br>
<br>
**Bug 4 – Cadastro com e-mail duplicado**

**Descrição**

O sistema permite criar múltiplas contas utilizando o mesmo endereço de e-mail.

Passos para reproduzir

Criar conta com um e-mail válido

Criar outra conta utilizando o mesmo e-mail

**Resultado atual**

O sistema cria múltiplas contas com o mesmo e-mail.

**Resultado esperado**

O sistema deveria impedir duplicidade e informar que o e-mail já está cadastrado.

Severidade: Alta
Prioridade: Alta
<br>
<br>
**Bug 5 – Campo nome aceita caracteres inválidos**

**Descrição**

O campo Nome completo aceita números e caracteres especiais.

Passos para reproduzir

Acessar tela de cadastro

Inserir valores como:

123456
@@@@
!@#$%

Criar conta

**Resultado atual**

O sistema aceita esses valores.

**Resultado esperado**

O campo deveria aceitar apenas letras e espaços.

Severidade: Média
Prioridade: Média
<br>
<br>
**Bug 6 – Campo telefone aceita letras**

**Descrição**

O campo telefone aceita caracteres não numéricos.

Passos para reproduzir

Inserir valores como:

abcdef
teste
123abc

Criar conta

**Resultado atual**

O sistema aceita valores inválidos.

**Resultado esperado**

O campo deveria aceitar apenas números ou um formato válido de telefone.

Severidade: Média
Prioridade: Média
<br>
<br>
**Bug 7 – Senha visível na requisição de login**

Descrição

Ao inspecionar a requisição de login através do DevTools, a senha pode ser visualizada diretamente na requisição.

Passos para reproduzir

Abrir DevTools (F12)

Ir na aba Network

Realizar login

Inspecionar a requisição enviada

**Resultado atual**

A senha aparece diretamente na requisição.

**Resultado esperado**

Dados sensíveis devem ser protegidos durante a comunicação.

Severidade: Alta
Prioridade: Alta
<br>
<br>
**Bugs Prioritários**

Os dois bugs que deveriam ser corrigidos primeiro são:
<br>
<br>
**1️⃣ Falha na validação de formulário (Bug 3)**

**Motivos:**

permite criação de contas inválidas

compromete integridade dos dados

quebra regras básicas de autenticação
<br>
<br>
**2️⃣ Cadastro com e-mail duplicado (Bug 4)**

**Motivos:**

compromete identificação de usuários

pode gerar inconsistências no sistema
<br>
<br>
**💡 Sugestões de melhoria**

implementar validação de campos obrigatórios

implementar validação robusta de senha

validar e-mail corretamente

validar formato de telefone

implementar validação tanto no frontend quanto no backend

melhorar feedback de erro ao usuário

ajustar responsividade do layout
