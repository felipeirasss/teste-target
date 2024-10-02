1) PYTHON
INDICE = 13
SOMA = 0
K = 0

while K < INDICE:
    K += 1          
    SOMA += K        
print("O valor final de SOMA é:", SOMA)

2)  Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.
def is_fibonacci(num):
    a, b = 0, 1
    while a < num:
        a, b = b, a + b
    if a == num or num == 0:
        return True
    else:
        return False

numero = int(input("Digite um número para verificar se pertence à sequência de Fibonacci: "))
if is_fibonacci(numero):
    print(f"O número {numero} pertence à sequência de Fibonacci.")
else:
    print(f"O número {numero} NÃO pertence à sequência de Fibonacci.")
    
3) Dado um vetor que guarda o valor de faturamento diário de uma distribuidora, faça um programa, na linguagem que desejar, que calcule e retorne:
• O menor valor de faturamento ocorrido em um dia do mês;
• O maior valor de faturamento ocorrido em um dia do mês;
• Número de dias no mês em que o valor de faturamento diário foi superior à média mensal.

import json

with open('faturamento.json', 'r') as file:
    dados = json.load(file)

faturamento = [dia['valor'] for dia in dados if dia['valor'] > 0]

menor_valor = min(faturamento)
maior_valor = max(faturamento)

media_faturamento = sum(faturamento) / len(faturamento)

dias_acima_da_media = len([valor for valor in faturamento if valor > media_faturamento])

print(f"Menor valor de faturamento: {menor_valor}")
print(f"Maior valor de faturamento: {maior_valor}")
print(f"Número de dias com faturamento acima da média: {dias_acima_da_media}")

[
    {"dia": 1, "valor": 22174.1664},
    {"dia": 2, "valor": 24537.6698},
    {"dia": 3, "valor": 26139.6134},
    {"dia": 4, "valor": 0.0},
    {"dia": 5, "valor": 0.0},
    {"dia": 6, "valor": 26742.6612},
    {"dia": 7, "valor": 0.0}
]

4) Dado o valor de faturamento mensal de uma distribuidora, detalhado por estado:
• SP – R$67.836,43
• RJ – R$36.678,66
• MG – R$29.229,88
• ES – R$27.165,48
• Outros – R$19.849,53

Escreva um programa na linguagem que desejar onde calcule o percentual de representação que cada estado teve dentro do valor total mensal da distribuidora.  

faturamento_estados = {
    'SP': 67836.43,
    'RJ': 36678.66,
    'MG': 29229.88,
    'ES': 27165.48,
    'Outros': 19849.53
}

faturamento_total = sum(faturamento_estados.values())

for estado, valor in faturamento_estados.items():
    percentual = (valor / faturamento_total) * 100
    print(f"{estado}: {percentual:.2f}% do faturamento total.")
    
5) Escreva um programa que inverta os caracteres de um string.
    
def inverter_string(s):
    string_invertida = ""
    for i in range(len(s) - 1, -1, -1):
        string_invertida += s[i]
    
    return string_invertida
   
string = input("Digite uma string para inverter: ")
print(f"String invertida: {inverter_string(string)}")
