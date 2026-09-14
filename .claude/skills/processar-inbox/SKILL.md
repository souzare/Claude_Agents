---
name: processar-inbox
description: Lê o conteúdo bruto em 00 - Inbox do vault Zettelkasten do usuário (em /Users/doctor/Documents/Obsidian_Vaults/Galifrey) — anotações soltas, links, ideias, colas de reunião — identifica os temas/conceitos presentes, verifica se já existem notas equivalentes em 02 - Conceitos, e destila o conteúdo nessas notas (criando novas ou atualizando existentes) exatamente no formato do vault, linkado ao MOC do domínio correto. Se o conteúdo for de uma reunião, também cria a nota em 03 - Fontes/Reuniões. Ao final, esvazia o que foi processado do inbox. Use quando o usuário pedir para processar o inbox, organizar anotações, destilar algo no vault, ou colar conteúdo bruto que precisa virar conhecimento permanente.
---

# Processar Inbox → Conceitos

Objetivo: `00 - Inbox/README.md` tem uma regra dura — nada fica lá mais de uma semana. Esta skill fecha o ciclo: pega captura bruta e vira conhecimento permanente e conectado.

## Passos

1. **Leia o conteúdo bruto.** Pode ser o próprio `00 - Inbox` do vault, ou conteúdo que o usuário colou nesta conversa (reunião, artigo lido, ideia). Se for texto colado sem estar ainda em `00 - Inbox`, não precisa criar arquivo de inbox intermediário — pode ir direto para o destilamento.

2. **Identifique os temas.** Um input bruto pode gerar 0, 1 ou vários conceitos. Não force um conceito por parágrafo — agrupe pelo que realmente é uma ideia atômica reutilizável (o critério de uma nota de conceito em Zettelkasten).

3. **Verifique duplicidade antes de criar.** Para cada tema identificado, `Grep`/`Glob` em `02 - Conceitos` por título exato e por sinônimos. Regra:
   - Já existe nota equivalente → **atualize-a** (adicione ao que já está lá, sem apagar o que o usuário escreveu; ex.: completar um `- [ ]` de "O que preciso saber", acrescentar em "Minhas notas" se o novo conteúdo for factual/objetivo — reflexão pessoal ("E daí?") não invente por ele).
   - Não existe → crie nova nota a partir de `06 - Templates/Template - Conceito.md`.

4. **Classifique cada nota nova:** domínio (tag da tabela do agente `estudos-zettelkasten`, ou pergunte se genuinamente não couber em nenhum existente), nível (básico/intermediário/avançado, avalie pela profundidade do conteúdo bruto), trilha (técnico/executivo/idiomas).

5. **Linke ao MOC.** Toda nota nova precisa: wikilink do MOC em "## Conexões", e um item novo no roadmap (Básico/Intermediário/Avançado, conforme o nível) da MOC correspondente, se ainda não estiver lá.

6. **Se o conteúdo for de reunião:** crie também a nota em `03 - Fontes/Reuniões` a partir de `06 - Templates/Template - Reunião.md`, com decisões, ações e wikilinks para os conceitos destilados em "## Aprendizados (conceitos)".

7. **Esvazie o processado do inbox.** Se o conteúdo veio de `00 - Inbox`, remova o que foi destilado (o inbox é só captura transitória — o conhecimento já vive nas notas de conceito/fonte agora). Não apague nada que ainda não foi processado.

## Regras do vault a respeitar ao editar arquivos

Sem YAML no topo do arquivo, tags só no rodapé depois de um separador `---`, wikilinks `[[Nome Exato]]` para toda referência interna, título da nota (`# Título`) igual ao nome do arquivo.

## Ao terminar

Resuma ao usuário: quantas notas foram criadas vs. atualizadas, quais, em que domínio/MOC cada uma entrou, e se algum item do inbox ficou pendente por falta de informação (não invente contexto que não estava no bruto).
