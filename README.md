# Checkout PagJus

Página de **checkout transparente** para o PagJus — pagamento de guias e débitos judiciais no cartão de crédito (parcelado), com aprovação concluída na própria página, sem redirecionamento para outra plataforma.

Construído em um único arquivo HTML autossuficiente (CSS e JS inline, imagens em `data:` URI), na identidade visual do PagJus.

## Como usar

Abra o `index.html` no navegador. Não há dependência de build nem de servidor.

Parâmetros de pré-visualização das telas de resultado (via URL):

- `index.html?tela=sucesso` — tela de pagamento aprovado
- `index.html?tela=erro` — tela de pagamento recusado

No fluxo normal, clicar em **Pagar** processa e exibe a tela de sucesso.

## Estrutura da tela

- **Cabeçalho** com dados do cliente (nome + CNPJ).
- **Coluna de resumo**
  - Cards *Total a pagar* e *Saldo*.
  - Botão *Histórico e extrato*.
  - *Pagamentos a fazer*: cada guia é selecionável (checkbox) e expansível, com **linha digitável** (botão Copiar), **fornecedor**, **itens** e **documento** (Ver / Baixar).
  - *Saldo a quitar* (selecionável).
  - *Resumo do pagamento* (valor selecionado + taxa de serviço + total), que reage à seleção das guias.
- **Coluna de pagamento**: dados do pagador, parcelas, dados do cartão, endereço da fatura e botão **Pagar**.
- **Telas de resultado**: Sucesso e Erro.

## Identidade visual (PagJus)

- Ink / navy: `#0A0D16`
- Laranja (acento / CTA secundário): `#FF5500`
- Verde (sucesso): `#1F9D57`
- Vermelho (vencido / débito / negativo): `#CF001E` — equivalente a `oklch(0.535 0.222 25)`
- Off-white (fundo): `#F5F4F1`
- Tipografia: **Inter** (texto) e **JetBrains Mono** (valores / linha digitável)
- Faixa inferior: `#FF5500`

Logo da **Potencial Tecnologia** embutido como `data:` URI no rodapé ("Processado por").

## Observações (dados de exemplo)

Os valores e dados exibidos são **placeholders** para demonstração:

- Guias, valores, vencimentos, linha digitável, fornecedor e CNPJ.
- A **taxa de serviço** usa uma alíquota ilustrativa definida na constante `FEE_RATE` (no `<script>`). Ajuste conforme a regra real.
- Botões *Histórico e extrato*, *Ver*, *Baixar* e *Baixar comprovante* são não-funcionais (protótipo).

## Próximos passos sugeridos

- Ligar os campos aos dados reais da API do PagJus (guias, valores, linha digitável, taxa e parcelas).
- Implementar o processamento real do cartão e o retorno de sucesso/erro.
- Definir a regra de taxa por bandeira / número de parcelas.

---

Protótipo de UI. Marcas e logos pertencem aos seus respectivos donos (PagJus / Potencial Tecnologia).
