# CitaRef

Base de conhecimento e conjunto de prompts para elaborar e conferir referências bibliográficas e citações no sistema autor-data, com foco nas normas **ABNT NBR 6023:2025** e **ABNT NBR 10520:2023**.

O projeto orienta assistentes de inteligência artificial a identificar o tipo de documento, validar os elementos bibliográficos e apresentar a referência antes das formas de citação no texto. Há instruções específicas para documentos jurídicos, publicações em Diário Oficial e autoria institucional.

> [!IMPORTANT]
> O CitaRef é um material de apoio. A resposta gerada deve ser conferida com o documento original e com as normas aplicáveis antes de ser usada em trabalhos acadêmicos, técnicos ou jurídicos.

## Recursos

- elaboração de referências conforme a ABNT NBR 6023:2025;
- orientação para citações diretas, indiretas e citações de citação conforme a ABNT NBR 10520:2023;
- tratamento de autoria pessoal e autoria-entidade;
- normalização de nomes institucionais e siglas;
- protocolo de consulta e validação de atos publicados em Diário Oficial;
- indicação explícita de dados ausentes, sem preenchimento por suposição;
- correlação entre a chamada autor-data e a lista de referências;
- registro de DOI, URL e data de acesso quando aplicáveis.

## Estrutura do repositório

| Arquivo | Finalidade |
| --- | --- |
| [`Prompt Mestre.txt`](./Prompt%20Mestre.txt) | Regras gerais e ordem de análise para referências e citações. |
| [`PROMPT MESTRE — REFERÊNCIA DE DIÁRIO OFICIAL.txt`](./PROMPT%20MESTRE%20%E2%80%94%20REFER%C3%8ANCIA%20DE%20DI%C3%81RIO%20OFICIAL.txt) | Protocolo de validação de atos oficiais, portais e APIs. |
| [`Entrada por Autoridade - Siglas.txt`](./Entrada%20por%20Autoridade%20-%20Siglas.txt) | Orientações para autoria-entidade, formas autorizadas de nomes e siglas. |
| [`#ABNT NBR 6023-2025.txt`](./%23ABNT%20NBR%206023-2025.txt) | Base de consulta sobre elaboração de referências. |
| [`#ABNT NBR 10520-2023.txt`](./%23ABNT%20NBR%2010520-2023.txt) | Base de consulta sobre apresentação de citações. |

## Como usar

### 1. Obtenha o projeto

```bash
git clone https://github.com/bibliodados/CitaRef.git
cd CitaRef
```

### 2. Carregue a base de conhecimento

Em um assistente de IA que aceite anexos ou bases de conhecimento:

1. adicione os arquivos `.txt` do repositório;
2. defina `Prompt Mestre.txt` como instrução principal;
3. para documentos jurídicos ou atos oficiais, inclua também o prompt de Diário Oficial;
4. para órgãos públicos, instituições ou autores identificados por siglas, inclua `Entrada por Autoridade - Siglas.txt`;
5. use os textos das normas como material de consulta quando necessário.

### 3. Faça uma solicitação

Exemplo:

```text
Elabore a referência e as formas de citação no texto para o documento abaixo.
Não presuma dados ausentes e informe quais elementos não puderam ser validados.

[cole os metadados ou forneça o link oficial]
```

Para atos publicados em Diário Oficial, forneça sempre que possível o link oficial direto, a data de publicação e a identificação do ato. O fluxo do projeto exige a conferência dos metadados na fonte oficial.

## Formato esperado da resposta

O fluxo principal prevê uma saída organizada da seguinte forma:

```text
REFERÊNCIA ABNT
[referência normalizada]

CITAÇÃO NO TEXTO
Parentética: (...)
Narrativa: ...

LINK OFICIAL
[endereço validado]
```

Dependendo do documento, a resposta também pode apresentar os dados identificados, a validação da edição do Diário Oficial e observações sobre elementos não localizados.

## Princípios do CitaRef

1. **Validar antes de completar:** informações ausentes não devem ser inventadas, estimadas ou inferidas.
2. **Priorizar fontes oficiais:** especialmente no caso de legislação, atos administrativos e Diários Oficiais.
3. **Manter consistência:** sequência, pontuação e destaque tipográfico devem ser uniformes em toda a lista de referências.
4. **Relacionar referência e citação:** toda chamada no texto deve corresponder de modo inequívoco a uma entrada na lista de referências.
5. **Registrar a incerteza:** quando um elemento não puder ser confirmado, essa ausência deve ser declarada.

## Contribuição

Contribuições são bem-vindas. Antes de abrir uma alteração:

1. verifique se a orientação proposta está apoiada na edição vigente da norma ou em fonte oficial;
2. preserve a separação entre regras gerais, documentos oficiais e autoria-entidade;
3. não inclua exemplos com metadados inventados;
4. descreva com clareza a justificativa e a fonte da mudança no pull request.

Para correções, sugestões ou novos casos de uso, [abra uma issue](https://github.com/bibliodados/CitaRef/issues).

## Aviso sobre normas técnicas

As normas da ABNT são documentos protegidos por direitos autorais. Verifique se você possui autorização para armazenar, reproduzir e distribuir o conteúdo correspondente. Este repositório não é afiliado nem endossado pela Associação Brasileira de Normas Técnicas.

## Licença

O repositório não informa atualmente uma licença de uso. Na ausência de uma licença explícita, permanecem reservados os direitos aplicáveis ao conteúdo. Caso você mantenha o projeto, considere adicionar um arquivo `LICENSE` compatível com os materiais que podem ser redistribuídos.
