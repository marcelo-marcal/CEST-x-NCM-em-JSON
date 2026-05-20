# CEST-x-NCM-em-JSON
CONVÊNIO ICMS 146, DE 11 DE DEZEMBRO DE 2015

# Tabela CEST x NCM em JSON

Tabela pública **CEST x NCM** estruturada em formato JSON para uso em sistemas fiscais, ERPs, integrações contábeis, validações de XML e auditorias de cadastro de produtos.

Este repositório tem como objetivo ajudar desenvolvedores, contadores e analistas fiscais que precisam consultar ou validar a relação entre **CEST** e **NCM/SH** de forma automatizada.

---

## Arquivos

### `tabela-cest-ncm-completa.json`

Arquivo principal em formato JSON legível, recomendado para consulta, análise e integração.

### `tabela-cest-ncm-completa.min.json`

Versão minificada do mesmo arquivo, indicada para uso em produção ou importação automatizada.

---

## O que esta tabela permite fazer

Com este JSON, é possível:

- consultar CEST por NCM;
- consultar NCMs vinculados a um CEST;
- validar se o CEST informado em um XML é compatível com o NCM;
- apoiar auditorias fiscais;
- identificar possíveis erros de cadastro em sistemas como ERP, sistema contábil ou sistema emissor de nota;
- criar alertas automáticos em importações de XML.

---

## Estrutura dos dados

Exemplo simplificado de um registro:

```json
{
    "metadata": {
        "name": "Tabela CEST x NCM completa",
        "description": "Tabela CEST x NCM extraída dos anexos CEST recebidos em ODT, com recuperação de linhas inicialmente não identificadas, limpeza de duplicados e preservação de itens sem NCM como CEST_ONLY.",
        "generatedAt": "2026-05-20T16:37:03.108Z",
        "source": "Arquivos ODT dos anexos CEST processados localmente no projeto tributario-ncm.",
        "author": "Marcelo de Assis Marçal",
        "rulesTotal": 1013,
        "warningsTotal": 2,
        "notes": [
        "Registros CEST_ONLY representam itens da tabela CEST sem NCM/SH informado na linha de origem.",
        "Registros PREFIX representam códigos abreviados, como 6306.1 ou 0402.9, úteis para validação por prefixo.",
        "Registros de retificação prevalecem sobre duplicados idênticos do anexo original.",
        "Este JSON é destinado a consulta, auditoria e integração em sistemas fiscais."
        ]
    },
    "totals": {
        "sourceRules": 1111,
        "publicRules": 1013,
        "removedDuplicates": 1,
        "removedInvalidUnknownRules": 99,
        "cestOnlyWarningsKept": 2
    },
    "rules": [
        {
        "sourceAnnex": "ANEXO II",
        "itemNumber": "1.0",
        "segmentCode": "01",
        "cestCode": "01.001.00",
        "ncmCodeRaw": "3815.12.10",
        "ncmCodeNormalized": "38151210",
        "ncmMatchType": "EXACT",
        "description": "Catalisadores em colmeia cerâmica ou metálica para conversão catalítica de gases de escape de veículos e outros catalisadores",
        "isRetified": false,
        "retificationNote": null
        },
        {
        "sourceAnnex": "ANEXO II",
        "itemNumber": "1.0",
        "segmentCode": "01",
        "cestCode": "01.001.00",
        "ncmCodeRaw": "3815.12.90",
        "ncmCodeNormalized": "38151290",
        "ncmMatchType": "EXACT",
        "description": "Catalisadores em colmeia cerâmica ou metálica para conversão catalítica de gases de escape de veículos e outros catalisadores",
        "isRetified": false,
        "retificationNote": null
        },
        {
        "sourceAnnex": "ANEXO II",
        "itemNumber": "2.0",
        "segmentCode": "01",
        "cestCode": "01.002.00",
        "ncmCodeRaw": "3917",
        "ncmCodeNormalized": "3917",
        "ncmMatchType": "POSITION",
        "description": "Tubos e seus acessórios (por exemplo, juntas, cotovelos, flanges, uniões), de plásticos",
        "isRetified": false,
        "retificationNote": null
        },
        {
```

### Observação fiscal importante

A validação correta do CEST não deve considerar apenas o código CEST isolado.

É importante analisar também:

NCM/SH;
descrição do produto;
segmento;
legislação vigente;
operação fiscal;
regras estaduais aplicáveis;
eventuais retificações.

Este material serve como apoio técnico e não substitui a análise de um profissional contábil ou tributário.

### Créditos

Base JSON organizada por:

Marcelo de Assis Marçal
Ano: 2026

Este material foi estruturado para apoiar a comunidade de desenvolvedores, contadores e profissionais fiscais que trabalham com automação tributária no Brasil.
