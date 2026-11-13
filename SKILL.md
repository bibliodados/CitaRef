---
name: citaref-abnt
description: Elaborar e revisar referências bibliográficas e citações conforme a ABNT NBR 6023:2025 e a ABNT NBR 10520:2023, incluindo autoria-entidade, siglas e atos de Diário Oficial. Use quando o pedido envolver referências, citações ou normalização ABNT; não use para APA, Vancouver ou outros estilos.
metadata:
  short-description: Referências e citações ABNT com validação oficial
---

# CitaRef ABNT

Use esta skill para produzir referências bibliográficas, citações no texto e decisões de entrada de autoria conforme as normas ABNT disponíveis neste pacote.

## Fontes locais e roteamento

Leia somente a referência necessária para o pedido:

- [ABNT NBR 6023:2025](references/abnt-nbr-6023-2025.md): elementos, ordem e apresentação de referências.
- [ABNT NBR 10520:2023](references/abnt-nbr-10520-2023.md): citações diretas, indiretas, autor-data, sistema numérico e notas.
- [Entrada por autoridade e siglas](references/entrada-por-autoridade-e-siglas.md): autoria-entidade, governos, subordinação, siglas e qualificadores.
- [Diário Oficial e portais oficiais](references/diario-oficial-e-portais-oficiais.md): atos oficiais, validação documental, portais e APIs.

As referências da skill ficam somente em `references/`, em formato Markdown.

## Formatação das referências

- Quando houver destaque tipográfico na referência, apresente o título destacado em **negrito**, usando `**...**`; não use itálico.
- Aplique a mesma regra ao subtítulo quando ele fizer parte do título destacado.
- Não aplique negrito à autoria, ao local, à editora, ao ano, à paginação, ao ISBN, ao DOI ou à URL.
- Mantenha essa escolha de destaque de forma uniforme em todas as referências da mesma resposta.

## Fluxo de trabalho

1. Identifique o objetivo: referência, citação, revisão de uma referência existente, autoria institucional ou ato publicado em Diário Oficial.
2. Identifique o tipo documental e separe os dados fornecidos dos dados que ainda precisam ser confirmados.
3. Para referências, aplique a NBR 6023:2025; para citações, aplique a NBR 10520:2023. Não complete lacunas por memória ou suposição.
4. Se houver autoria-entidade, determine primeiro a forma autorizada de entrada: direta, subordinada a entidade superior, subordinada à jurisdição, nome geográfico convencional, sigla ou nome convencional. Explique brevemente a decisão.
5. Se o pedido envolver Diário Oficial, lei, decreto, portaria, resolução, edital, parecer ou outro ato oficial:
   - consulte o portal oficial correspondente antes de fechar a resposta;
   - extraia os metadados do documento oficial, sem inferência;
   - confirme no fascículo o ano, a seção, a edição e a página;
   - informe o link oficial direto;
   - classifique o acesso como API pública oficial documentada, base oficial de dados abertos, portal web de consulta/publicação ou API agregadora, somente quando houver evidência.
6. Se um dado não for localizado, informe explicitamente “elemento não localizado no documento oficial” ou “ano do DOU não localizado no documento oficial”, conforme o caso.

## Correção rápida

- Se a mensagem do usuário consistir apenas em `2` depois de uma referência apresentada, interprete-a como pedido para revisar e corrigir a referência imediatamente anterior.
- Na correção, reavalie os dados fornecidos e as fontes consultadas, não invente elementos ausentes e apresente a referência corrigida com os títulos em **negrito**.
- Aponte objetivamente o que foi corrigido. Se não houver uma referência anterior identificável, solicite que o usuário a envie.

## Confirmação final obrigatória

- Ao final de toda resposta que apresente ou revise uma referência, mostre exatamente: `A referência esta correta? Caso não digite [2] para refazer`
- Se o usuário responder apenas `2`, refaça a referência anterior conforme a seção `Correção rápida` e encerre novamente com a mesma frase de confirmação.

## Regras de autoria institucional

- A entrada direta é a regra geral quando o próprio nome identifica suficientemente a entidade.
- Use jurisdição governamental e subordinação quando a natureza do órgão exigir essa estrutura; não coloque automaticamente toda entidade pública sob o governo.
- Não use sigla apenas por brevidade. Prefira-a quando for a forma predominantemente identificadora e não causar ambiguidade.
- Preserve na referência a forma autorizada e a hierarquia necessária. Na citação autor-data, use grafia textual corrente, mantendo qualificadores ou siglas quando forem necessários para distinguir a entidade.
- Para nomes homônimos, acrescente qualificadores como `(Estado)` ou `(Município)` quando necessário.

## Saída padrão

Salvo instrução diferente, entregue nesta ordem:

1. `REFERÊNCIA ABNT`
2. `CITAÇÃO NO TEXTO`, com forma parentética e narrativa; inclua a forma de citação direta quando couber
3. `LINK OFICIAL`, quando houver
4. `DADOS IDENTIFICADOS` e, para Diário Oficial, `VALIDAÇÃO DO ANO DO DOU`
5. `JUSTIFICATIVA`, quando a decisão de autoria, sigla, jurisdição ou subordinação exigir explicação
6. `DADOS AUSENTES`, se houver elementos não confirmados

Em revisões, mostre a forma corrigida e aponte objetivamente o que foi alterado. Não invente autor, data, edição, página, DOI, ISSN, URL ou qualquer outro elemento.
