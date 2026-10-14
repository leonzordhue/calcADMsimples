# LAADV · Triagem de Viabilidade (calcADMsimples)

Página única para a **triagem rápida** de ações de progressão funcional (servidores do Amazonas e de Manaus):

1. **Documentos:** o atendente arrasta o que o cliente mandou (3 últimos contracheques, RG, comprovante de residência, termo de posse…). PDF ou foto do celular.
2. **Conferir dados:** carreira, data de posse, referência atual e mês do contracheque vêm preenchidos pela leitura automática; o atendente confere e corrige.
3. **Resultado:**
   - **Viável / Sem viabilidade agora / Precisa de análise**, com a linha do tempo das progressões devidas;
   - meses de diferença a cobrar (prescrição de 5 anos);
   - **checklist dos documentos que faltam** para fechar a ação;
   - mensagem pronta para mandar ao cliente pelo WhatsApp e resumo interno.

O cálculo exato dos valores continua na [calculadora completa](https://leonzordhue.github.io/calculo-administrativo/).

## Leitura de documentos (100% no navegador, nada é enviado)
- **pdf.js 4.10** (Mozilla, o mesmo leitor do Firefox): extrai o texto de PDFs digitais, que é o caso dos contracheques baixados dos portais.
- **Tesseract.js 5.1** com idioma português: lê fotos e PDFs escaneados (OCR). Leva alguns segundos por página.
- Os dados lidos são **sugestões**: o passo 2 sempre mostra de qual arquivo veio cada campo e permite corrigir.

## Regras (copiadas do motor estável `calculo-administrativo`)
| Carreira | Regra | Base legal |
|---|---|---|
| SEDUC magistério / apoio | 48 meses; 36 meses a partir de 01/03/2019 (alcança interstício em curso) | Lei 3.951/2013 e Lei 4.836/2019 |
| SEDUC administrativo | 24 meses | Lei 4.058/2014 |
| SEMED magistério | referência A–G a cada 36 meses | Lei 1.126/2007, art. 49 |
| SEMED administrativo | padrão 1–13 a cada 36 meses | Lei 1.624/2011 |
| SES/SUSAM | 1ª aos 36 meses, depois a cada 24 (trilhas A–D e E–H) | Lei 3.469/2009 |
| SEMSA | padrão 1–18 a cada 24 meses | Lei 1.222/2008, art. 32 §2 |
| PMAM / PCAM | só **indício**: interstício de 3 anos, mas a promoção tem outros requisitos | Lei 3.725/2012; Leis 2.875/2004 e 4.059/2014 |

## Pendências (validar com o escritório)
- A **lista de documentos obrigatórios** (`DOCS` no `index.html`) é uma proposta inicial.
- A leitura foi testada com contracheques **fictícios**. Precisamos de 1 ou 2 contracheques reais por órgão, **com nome e CPF tarjados**, para ajustar a leitura ao layout de cada portal.

Metodologia AKE: veja `window._VERSION_LOG`, `_VICIOS_CONHECIDOS` e `_TENTATIVAS_FALHAS` no console.
