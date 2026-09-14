---
name: tangibilizar-conceito
description: Ajuda a transformar um ou mais conceitos já estudados no vault Zettelkasten do usuário (em /Users/doctor/Documents/Obsidian_Vaults/Galifrey) em algo prático — mini-projeto, lab, protótipo, exercício aplicado ao trabalho real — para consolidar o aprendizado fazendo. Propõe o escopo, cria ou atualiza a página correspondente em 04 - Projetos seguindo o padrão das existentes, e garante o link de volta nas notas de conceito e na MOC envolvidas. Use quando o usuário disser algo como "quero praticar X", "como aplico Y no trabalho", "criar um projeto sobre Z", ou perguntar "e na prática?" depois de estudar um conceito.
---

# Tangibilizar um conceito em prática

Objetivo: fechar o loop entre "entendi a teoria" e "sei fazer" — o vault tem uma pasta `04 - Projetos` exatamente para isso: projetos que **consolidam** um ou mais conceitos.

## Passos

1. **Leia o(s) conceito(s) envolvidos** em `02 - Conceitos` — especialmente "O que preciso saber" e o que já está preenchido em "Minhas notas"/"Exemplo / aplicação no trabalho". Isso ancora a proposta no que o usuário já sabe, em vez de propor algo genérico de tutorial.

2. **Olhe os projetos existentes** em `04 - Projetos` (ex.: `Incident Response Agent com Claude`, `Lab End-to-End — Terraform, EKS, Datadog e CI-CD`, `Orbit — Métricas de IA no SDLC`) para manter o mesmo nível de formato e ambição — não é obrigatório copiar estrutura seção por seção (não há template fixo para Projetos), mas o tom e o nível de detalhe devem ser parecidos.

3. **Proponha escopo, não execute sozinho.** Sugira 1-2 formatos de projeto ajustados ao tempo que o usuário tem (de um exercício de 1h a um lab de um fim de semana) e ligados a algo real quando possível (um problema do trabalho dele, não um tutorial genérico). Deixe o usuário escolher/ajustar antes de criar a página.

4. **Crie ou atualize a página em `04 - Projetos`.** Inclua pelo menos:
   - O que o projeto prova/consolida e por quê
   - Passo a passo ou marcos (`- [ ]`)
   - Wikilinks `[[Conceito]]` para cada conceito que o projeto exercita
   - Uma seção final "E daí?" — o que isso muda na prática de trabalho do usuário

5. **Feche o loop de volta:**
   - Na MOC do domínio (`01 - Mapas/MOC - ...`), preencha ou adicione o link em "## Projeto que consolida" se ainda não houver um.
   - Na nota de conceito, se "## Exemplo / aplicação no trabalho" estiver vazia, **não escreva por ele** — sugira que ele preencha depois de fazer o projeto, ou adicione só o wikilink do projeto como referência, deixando a reflexão para o usuário.

## Regras do vault a respeitar ao editar arquivos

Sem YAML no topo, tags só no rodapé depois de `---`, wikilinks `[[Nome Exato]]` para toda referência interna.
