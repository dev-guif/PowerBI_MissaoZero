# MissãoZero
Dashboard de faturamento construído durante a Missão Zero da Power BI experience. 
- % Discount = % Discount = DIVIDE([Discount], [Gross Sales])
  Porcentagem de desconto.
- % Net Sales Month = % Net Sales MoM (Month over Month) = DIVIDE([Net Sales] - [Net Sales PM], [Net Sales PM])
  Porcentagem de vendas por mês.
- Discount = SUMX(Vendas, Vendas[OrderQuantity] * Vendas[UnitPrice] *Vendas[Discount %])
  Desconto em $.
- Gross Sales = SUMX(Vendas, Vendas[OrderQuantity] * Vendas[UnitPrice])
  Soma das vendas (bruto) por unidade de produto.
- Net Sales = [Gross Sales] - [Discount]
  Faturamento líquido.
- Net Sales Gym = CALCULATE([Net Sales], Vendas[BusinessType] = "Gym")
  Vendas líquidas por gênero (gym).
- Net Sales PM = CALCULATE([Net Sales], PREVIOUSMONTH(Calendario[Date]))
  Faturamento líquido mês anterior.
- Orders = DISTINCTCOUNT(Vendas[SalesOrderNumber])
  Quantidade de ordens de compra.
- Volume = SUM(Vendas[OrderQuantity])
  Soma das quantidades de vendas.
