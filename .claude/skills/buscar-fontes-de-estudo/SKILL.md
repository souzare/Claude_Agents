---
name: buscar-fontes-de-estudo
description: Busca fontes confiáveis (documentação oficial, papers, livros reconhecidos, cursos, artigos de engenharia sérios) sobre um conceito do vault Zettelkasten do usuário em /Users/doctor/Documents/Obsidian_Vaults/Galifrey, avalia a confiabilidade de cada uma e formata como lista pronta para colar na seção "## Referências" de uma nota em 02 - Conceitos ou "## Fontes" de uma MOC em 01 - Mapas. Use quando o usuário pedir para achar fontes, pesquisar sobre um tema, ou popular referências de uma nota existente/nova.
---

# Buscar fontes de estudo confiáveis

Objetivo: dado um conceito ou tema, entregar uma lista curta e curada de fontes que o usuário pode efetivamente confiar e estudar — não uma lista genérica de resultados de busca.

## Passos

1. **Entenda o alvo.** Se o pedido referenciar uma nota que já existe em `02 - Conceitos`, leia-a primeiro (nível, domínio, o que já está em "O que preciso saber" e "Referências") para não repetir fontes já listadas e para calibrar a profundidade (básico vs avançado).

2. **Pesquise com critério, não em volume.** Use `WebSearch` com 2-5 buscas direcionadas. Priorize, nesta ordem:
   - Documentação oficial / especificação (ex.: docs da AWS, Kubernetes, Anthropic, RFC, paper original)
   - Papers seminais ou survey reconhecidos (arXiv, ACM, IEEE) quando o tema for acadêmico/técnico
   - Livros amplamente reconhecidos na área (cite autor e título, não precisa de link)
   - Engenharia de empresas de referência no tema (blogs técnicos de empresas que resolveram o problema em produção)
   - Cursos de plataformas conhecidas (Coursera, DeepLearning.AI, Udacity, O'Reilly, Anthropic Academy) só se agregarem algo que as fontes acima não cobrem
   - Evite: blogspam, listicles sem autoria clara, conteúdo sem data ou desatualizado para temas que mudam rápido (ex.: LLMs, cloud)

3. **Não invente URL nenhuma.** Toda fonte na lista final precisa ter vindo de um resultado real do `WebSearch` desta conversa. Se não achar fonte boa o suficiente para uma categoria, diga isso em vez de forçar uma fonte fraca.

4. **Avalie e formate.** Para cada fonte (tipicamente 3-6), uma linha no formato do vault:
   ```
   - Título — Autor/Plataforma (tipo: paper | doc oficial | livro | curso | artigo) — URL
   ```
   Adicione, fora da lista, 1 frase por fonte justificando por que ela é confiável e o que ela cobre que as outras não cobrem (evita redundância).

5. **Ofereça a aplicação direta.** Pergunte se o usuário quer que a lista seja inserida na seção "## Referências" da nota de conceito correspondente (ou "## Fontes" da MOC) — se sim, edite o arquivo diretamente, sem duplicar entradas que já estejam lá.

## Regras do vault a respeitar ao editar arquivos

Sem YAML no topo do arquivo, tags só no rodapé depois de `---`, wikilinks `[[Nome Exato]]` para notas internas — URLs cruas só para fontes externas.
