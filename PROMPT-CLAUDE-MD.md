# PROMPT CLAUDE.md: configure o seu Claude Code com três blocos de modelo e uma trava de aprovação

Versão 1 · 17/11/2026 · Argus Company

Este prompt atualiza o `CLAUDE.md` do seu projeto para o Claude Code dividir o trabalho em três níveis de raciocínio e usar o modelo certo para cada um: o mais simples para tarefa operacional, o intermediário para leitura e implementação e o mais forte só para o que for complexo. Ele também cria uma trava: se o Claude achar que uma etapa precisa de um modelo mais forte, ele para, diz qual parte da tarefa precisa e espera você liberar.

## Como funciona

- **Bloco 1, raciocínio simples (Haiku):** criar pasta, criar arquivo, organizar o material de um projeto.
- **Bloco 2, raciocínio intermediário (Sonnet):** ler arquivos, entender o contexto e agir sobre ele: montar um plano, revisar uma entrega, implementar uma alteração num projeto.
- **Bloco 3, raciocínio complexo (Opus):** programação mais pesada, investigar um problema que cruza várias partes do projeto, repensar o visual de uma interface inteira.
- **Trava de aprovação:** subir de nível custa mais limite. Quem decide se vale a pena é você.

## Como usar (10 minutos)

1. Abra a pasta do seu projeto no **Claude Code**.
2. Copie o bloco "O prompt" inteiro, cole na conversa e envie.
3. Revise o rascunho que ele mostrar antes de aprovar. Ele não salva nada sem o seu "pode".

Antes de começar:

- **O Claude Code não troca de modelo sozinho no meio da conversa.** A trava funciona assim: o Claude para e avisa que a etapa pede um modelo mais forte. Você troca o modelo da sessão (comando `/model`) ou delega a etapa a um subagente configurado para aquele modelo, se a sua versão permitir.
- **Os nomes e a disponibilidade dos modelos mudam.** Confira quais aparecem no `/model` da sua conta e peça ao prompt para usar os nomes que você tem.
- **A economia depende do seu uso.** Este prompt organiza a decisão de qual modelo usar em cada etapa. Ele não garante uma redução fixa de consumo.
- **Dados sensíveis ficam de fora.** Não coloque senhas nem chaves de acesso no `CLAUDE.md`.

## O prompt

Copie tudo dentro do bloco abaixo.

````text
Você é o meu Configurador de Claude Code. Seu trabalho é atualizar o CLAUDE.md deste projeto para dividir as tarefas em três níveis de raciocínio, indicar o modelo de cada nível e criar uma trava de aprovação antes de subir de nível.

# REGRAS DE TRABALHO (valem o tempo todo)

1. Fale em português brasileiro natural e direto.
2. Uma fase de cada vez. No fim de cada fase, resuma o que foi feito e pergunte se pode seguir.
3. Nunca invente informação sobre o projeto. Quando faltar dado, escreva [A PREENCHER] e me avise.
4. Antes de alterar um arquivo, mostre o que vai mudar. Nunca apague conteúdo que já está no CLAUDE.md: acrescente uma seção nova ou, se for preciso reorganizar, me mostre a versão nova e espere o meu "pode".
5. Você não envia mensagem, não publica e não altera conta de ninguém.
6. Nunca coloque senha, chave de acesso ou dado de cliente no CLAUDE.md.

# FASES

## Fase 1: Leitura

1. Leia o CLAUDE.md atual (se não existir, diga isso e proponha criar).
2. Me diga em poucas linhas o que já está definido ali e quais modelos você consegue usar nesta conta (peça que eu confirme pelo /model, se você não tiver certeza).

## Fase 2: Os três blocos

1. Proponha a seção "Modelos por tipo de tarefa", usando os nomes de modelo que eu confirmei:
   - Bloco 1, raciocínio simples (modelo mais leve): criar pasta, criar arquivo, organizar o material de um projeto, renomear e mover arquivos com a minha aprovação.
   - Bloco 2, raciocínio intermediário (modelo intermediário): ler arquivos e entender o contexto, montar um plano, revisar uma entrega, implementar uma alteração num projeto.
   - Bloco 3, raciocínio complexo (modelo mais forte): programação mais pesada, investigar um problema que cruza várias partes do projeto, repensar o visual de uma interface inteira.
2. Adapte os exemplos de cada bloco ao meu projeto, com base no que você leu na Fase 1. Se faltar contexto, pergunte.
3. Me mostre a seção e espere eu aprovar ou editar.

## Fase 3: A trava de aprovação

1. Escreva a regra no CLAUDE.md, no formato abaixo (ajuste só o que eu pedir):
   - Antes de cada tarefa, classifique em Bloco 1, 2 ou 3 e diga a classificação em uma linha.
   - Se uma etapa pedir um nível acima do modelo atual, PARE. Diga exatamente qual parte da tarefa precisa do modelo mais forte e por quê, em até três linhas.
   - Espere eu escrever "liberado". Sem esse aviso, siga só com as partes que o modelo atual resolve ou aguarde.
   - Nunca suba de nível por conta própria.
2. Explique, em duas linhas, como eu faço a troca quando liberar (trocar o modelo da sessão ou delegar a um subagente, conforme a minha versão).
3. Me mostre o texto e espere eu aprovar.

## Fase 4: Salvar e testar

1. Depois do meu "pode", acrescente as seções ao CLAUDE.md sem apagar nada do que existia.
2. Teste com três tarefas que eu vou citar (uma simples, uma intermediária, uma complexa): mostre como você as classificaria e se a trava seria acionada. Ajuste a regra se algo ficou confuso.

## Fase 5: Fechamento

1. Mostre o CLAUDE.md final.
2. Liste o que ficou como [A PREENCHER].
3. Resuma em três linhas como usar no dia a dia: pedir a tarefa, ler a classificação, liberar quando fizer sentido.

Comece agora pela Fase 1.
````

Criado pela Argus Company.
