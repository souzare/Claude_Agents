---
name: ajustar-estrutura-vault
description: Aplica mudanças estruturais no vault Zettelkasten do usuário (em /Users/doctor/Documents/Obsidian_Vaults/Galifrey) quando o plano de estudo original evolui — renomear um domínio/MOC, dividir uma MOC em duas, mesclar duas MOCs, mover notas entre trilhas (técnico/executivo/idiomas), descontinuar um domínio. Mapeia todo o raio de impacto (wikilinks, tags, cross-links entre MOCs) antes de tocar em qualquer arquivo, propõe o plano de migração para confirmação, executa mantendo consistência em todo o vault, e valida que nada ficou quebrado ou órfão no final. Use quando o usuário disser que o plano/direção mudou e pedir para reorganizar, renomear, dividir, mesclar ou mover algo já existente na estrutura — nunca para criar uma nota ou domínio novo do zero (isso é aditivo, trate direto).
---

# Ajustar a estrutura do vault sem quebrar nada

Esta skill é para **mudanças em algo que já existe** (renomear, dividir, mesclar, mover, descontinuar) — não para adicionar conteúdo novo. É a operação de maior risco no vault: um wikilink ou tag que fica para trás vira nota órfã ou link quebrado silenciosamente (Obsidian não avisa em texto puro). Trate com o mesmo cuidado de uma migração de schema.

## Quando acionar

- Usuário diz que o plano original mudou (nova direção de carreira em `05 - Carreira`, novo curso que reorganiza como ele pensa um domínio, um domínio "cresceu demais" e virou dois assuntos diferentes)
- Pedidos como "renomear MOC X para Y", "dividir esse domínio em dois", "mesclar essas duas MOCs", "mover essas notas da trilha técnica pra executiva", "esse domínio não faz mais sentido"

## Passos — nesta ordem, sem pular nenhum

### 1. Entender a mudança e o motivo
Pergunte o suficiente para saber exatamente o "antes" e o "depois" (nomes exatos de arquivos/tags envolvidos). Se a mudança vier de algo em `05 - Carreira/Plano`, leia o contexto lá — a reestruturação deve refletir o plano atual, não só a vontade pontual do momento.

### 2. Mapear o raio de impacto ANTES de tocar em qualquer arquivo
Use `Grep`/`Glob` no vault inteiro para listar **todas** as ocorrências de:
- O wikilink exato (`[[Nome Antigo]]`) — em `02 - Conceitos`, `01 - Mapas`, `03 - Fontes`, `04 - Projetos`, `05 - Carreira`, `07 - Diário`
- A tag exata (`#tag-antiga`)
- Menções em "Como este mapa conversa com os outros" de outras MOCs

Monte a lista completa de arquivos afetados. Não estime — confirme por busca.

### 3. Propor o plano de migração e esperar confirmação explícita
Mostre ao usuário, antes de executar:
- O que muda (ex.: `MOC - X` vira `MOC - Y` e `MOC - Z`; tag `#x` vira `#y` e `#z`; N notas de conceito são realocadas)
- A lista de arquivos que serão tocados (do passo 2)
- Se alguma nota fica ambígua sobre para onde vai (no caso de split), decida junto com o usuário — não decida sozinho qual metade de um domínio dividido cada conceito pertence quando não for óbvio

Isso é uma ação estrutural difícil de reverter — não execute sem um "sim" claro para o plano mostrado.

### 4. Executar com consistência total
- **Renomear MOC/domínio:** renomeie o arquivo, atualize a tag em todas as notas do domínio, atualize todos os wikilinks encontrados no passo 2, atualize os cross-links nas MOCs relacionadas.
- **Dividir um domínio:** crie a(s) MOC(s) nova(s) a partir de `06 - Templates/Template - MOC.md`, redistribua os itens de roadmap e as notas de conceito entre as MOCs resultantes, dê a cada uma sua tag própria, atualize "Como este mapa conversa com os outros" em todas as MOCs vizinhas.
- **Mesclar duas MOCs:** escolha (com o usuário) qual nome/tag sobrevive, migre todo o roadmap e as referências da MOC absorvida para a MOC final, atualize todos os wikilinks e tags das notas afetadas, e mova a MOC absorvida para `99 - Arquivo` (não delete).
- **Mover entre trilhas:** troque a tag `#trilha-...` nas notas afetadas; se isso também mudar o domínio, siga o fluxo de renomear/mesclar acima.
- **Descontinuar um domínio:** não apague as notas de conceito — são conhecimento válido. Mova a MOC para `99 - Arquivo`, e pergunte nota por nota se o conteúdo deve: (a) ser realocado para outro domínio existente, ou (b) ir junto para o arquivo.

### 5. Validar no final
- `Grep` de novo pelo nome/tag antigos no vault inteiro — não pode sobrar nenhuma ocorrência fora de `99 - Arquivo`.
- Confira que toda nota afetada ainda tem pelo menos um wikilink de MOC válido em "## Conexões".
- Confira que a tabela domínio↔MOC do agente `estudos-zettelkasten` ficou desatualizada por essa mudança — se ficou, avise o usuário para que a referência mental dele (e do agente, na próxima conversa) seja atualizada.

## Regras de segurança

- **Nunca delete arquivos.** Prefira sempre mover para `99 - Arquivo`. Exclusão real só se o usuário pedir explicitamente, arquivo por arquivo.
- **Nunca decida sozinho** para onde vai uma nota ambígua num split, ou qual nome sobrevive num merge — pergunte.
- Sem YAML no topo, tags só no rodapé depois de `---`, wikilinks `[[Nome Exato]]` — essas convenções não mudam mesmo em uma reestruturação.

## Ao terminar

Resuma: o que mudou estruturalmente, a lista final de arquivos tocados, e qualquer nota que ficou pendente de decisão do usuário.
