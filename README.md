# Simulador de Taxas

Simulador de parcelamento no cartão (débito e 1x a 18x). O cliente informa o valor e a entrada; o Simples Nacional e as taxas da maquininha são aplicados internamente.

**Acesse:** https://andersonelias3-cell.github.io/simulador-taxas/

## Como alterar as taxas

Edite o arquivo `index.html` e procure por `CONFIG` no início do script:

- `novo` e `seminovo`: cada tipo de aparelho tem sua configuração
- `simples`: % do Simples Nacional (zero no Novo)
- `simplesAcrescimo`: % do Simples sobre o acréscimo da taxa
- `debito`: taxa do débito
- `parcelas`: taxas de 1x a 18x

Depois de salvar (commit), o site atualiza sozinho em 1 a 2 minutos.

## Fórmula

```
saldo = valor - entrada
base = saldo / (1 - simples)
bruto = base / (100 - taxa) * 100
total = bruto + (bruto - base) * simples_sobre_acrescimo
parcela = total / número de parcelas
```
