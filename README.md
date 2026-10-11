# Simulador Tributário IBS / CBS — Imóveis

Alienação · Locação mensal · Hospedagem ≤90 dias

Espelho didático do **Decreto 12.955/2026 (CBS)** e **Resolução CGIBS 6/2026 (IBS)** — Título VI Cap. V Bens Imóveis + Hotelaria. Base: **LC 214/2025**.

Visual padrão VMF Contabilidade (azul-marinho + dourado).

## Demo

Arquivo único, sem dependências:

```
simulador-alienacao-imovel/index.html
```

Publique no GitHub Pages: repo → Settings → Pages → Deploy from branch → `/root` ou `/docs`. Ou acesse via `https://<user>.github.io/<repo>/`.

## Regras aplicadas

| Operação | Base | Alíquota |
|---|---|---|
| Alienação (art. 379) | venda − redutor ajuste (369-375) − social 100k residencial novo / 30k lote (376) | −50% da padrão |
| Locação mensal (arts. 364, 377, 379) | bruto − tributos/condomínio/foro suportados pelo locatário (§3º, com prova §4º) − R$600 × % área residencial | −70% |
| Hospedagem ≤90 dias (arts. 361+410 → 402-409) | valor total (inclui estacionamento/lavanderia/limpeza art. 409; alimentação vai p/ bares) | −40% |

* Fato gerador: alienação no ato (363 I); locação a cada pagamento (363 III); fornecedor regular credita insumos hotelaria (406), hóspede não (407).
* Porta de entrada art. 359: só contribuinte no regime regular. Pessoa física: art. 382 (>3 imóveis + >R$240 mil).
* Acima de 90 dias: volta para locação Cap. V.
* Alíquotas padrão editáveis (ref. 8,8% CBS + 17,7% IBS = 26,5%).

## Uso

1. Escolha Alienação / Locação / Hospedagem.
2. Preencha valores (calculadora auxiliar soma aquisição + IPCA% + ITBI/laudêmio + outorgas no redutor).
3. Calcular → CBS + IBS + base + memória técnica.
4. Modo Escritório (técnico) / Cliente (simplificado). Botão Imprimir gera PDF.

## Valores-limite para testar

* Venda 0 + redutor 0 → base 0.
* Redutor > venda → base 0.
* Dias 0 ou 91 → erro.
* Alíquota >100 → limitada a 100.
* Exclusões > aluguel → base 0.

## Aviso legal

Ferramenta de estudo/simulação. Não constitui parecer fiscal. Redutores corrigidos pelo IPCA, Sinter/CIB e transição art. 463 (3,65%) exigem análise do caso concreto. Valide com a legislação vigente e contador responsável.

## Estrutura

```
index.html  — simulador completo (HTML+CSS+JS)
README.md   — este arquivo
```

MIT — uso livre com atribuição.
