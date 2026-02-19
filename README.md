HELPER eSOCIAL – S-1200 e S-1210 (Sonova Light)
Versão: v3.2

1) Objetivo
Este arquivo HTML funciona como um Helper para leitura de XMLs do eSocial, com foco em:

- S-1200 (Remuneração)
- S-1210 (Pagamentos)

O sistema lê os XMLs diretamente no navegador (sem servidor), organiza os campos por caminho, permite busca e permite copiar valores rapidamente (inclusive para apoio em lançamentos e conferências).

2) Principais Funcionalidades
2.1 Importação
- Importar XML individual (botão Importar XML)
- Arrastar e soltar múltiplos XMLs
- Identificação automática de evento:
  - S-1200
  - S-1210
- Lista lateral com arquivos carregados
- Filtro por CPF, período, arquivo, rubrica

2.2 Visualização dos dados
- Aba “Todos os dados (caminho)” com:
  - Lista completa de paths do XML
  - Valor correspondente ao path
  - Botões de cópia:
    - Valor
    - Linha (path + valor)

2.3 Tabela de Verbas (S-1200)
- Exibe rubricas e valores para conferência e lançamento
- Agora inclui também retroativos (CCT / Dissídio) do S-1200

IMPORTANTE:
A versão v3.2 extrai verbas de duas origens:
- APUR (infoPerApur) = remuneração normal do mês
- ANT  (infoPerAnt)  = remuneração retroativa (CCT / dissídio / acordos)

Campos principais exibidos:
- CPF
- Matrícula
- Período
- Rubrica (codRubr)
- Identificação da rubrica (ideTabRubr, se existir)
- Valor (vrRubr)
- Quantidade (qtdRubr, se existir)
- Fator (fatorRubr, se existir)
- Origem: APUR ou ANT
- PerRef (mês retroativo do CCT, quando aplicável)
- Informações do acordo (quando aplicável):
  - dtAcConv
  - tpAcConv
  - dscADC

2.4 Tabela de Pagamentos (S-1210)
- Exibe os pagamentos do trabalhador
- Permite conferência do valor líquido pago
- Permite validar se o pagamento está consistente com o S-1200

2.5 Busca inteligente
- Campo de pesquisa por:
  - path (ex.: codRubr)
  - valor (ex.: matrícula, CPF)
- Busca rápida sem travar o navegador

2.6 Copiar com um clique
- Botão “Copiar resumo”
- Botão “Copiar JSON extraído”
- Botão “Copiar tabela (path value)”
- Botão “Exportar CSV (aba atual)”

3) Correções aplicadas na v3.2
3.1 Ajustes de CSS e layout
- Corrigido o problema da aba “Todos os dados (caminho)” ficar encoberta ao ser acionada
- Melhorado o posicionamento da barra de abas e o comportamento de rolagem
- Corrigida a quebra de texto nos botões “Valor” e “Linha” (não quebram mais no meio da palavra)

3.2 Extração completa das verbas de CCT (S-1200)
- Incluída extração do bloco:
  infoPerAnt > ideADC > idePeriodo > ideEstabLot > remunPerAnt > itensRemun
- Agora as verbas retroativas aparecem na tabela para lançamento
- Incluída coluna de origem (APUR / ANT)
- Incluída coluna perRef no retroativo (mês do dissídio/CCT)

4) Como usar (passo a passo)
1. Abrir o arquivo HTML no navegador (Chrome recomendado)
2. Clicar em “Importar XML” ou arrastar os arquivos XML para dentro do sistema
3. Selecionar o arquivo na lista lateral
4. Usar as abas para navegar:
   - Verbas S-1200
   - Pagamentos S-1210
   - Todos os dados (caminho)
5. Usar os botões de cópia para lançar no Excel ou validar no ADP

5) Observações importantes
- O sistema não envia arquivos para nenhum servidor
- Tudo é processado localmente no navegador
- Se o XML vier com tags faltando ou layout incompleto, o sistema tenta extrair o máximo possível
- Rubricas retroativas de CCT normalmente aparecem apenas em infoPerAnt

6) Sugestões de evolução (futuro)
- Consolidar verbas por rubrica e mês (somatório automático)
- Criar visão “Diferença APUR vs ANT”
- Criar botão “Copiar para modelo ADP” (layout pronto)
- Criar exportação Excel (XLSX) em vez de CSV

