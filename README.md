# Simulador de Taxas

Simulador de parcelamento no cartão (débito e 1x a 18x), serviços e boleto, já com Simples Nacional e taxa da maquininha.

**Acesse:** https://andersonelias3-cell.github.io/simulador-taxas/

## Como alterar as taxas padrão

Edite o arquivo `index.html` e procure por `DEFAULTS` no início do script:

- `iphone.parc`: taxas de 1x a 18x para aparelhos
- `servico.parc`: taxas de 1x a 18x para serviços
- `debito`: taxa do débito

Depois de salvar (commit), o site atualiza sozinho em 1 a 2 minutos.

## Fórmula

```
bruto = valor / (100 - taxa) * 100
total = bruto + (bruto - valor) * simples_sobre_acrescimo
parcela = total / número de parcelas
```
