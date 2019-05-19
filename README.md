# Monoprogramavel

```python
print("Simulador SO Monotarefa")
#Linha para fazer a leitura do arquivo txt na área de trabalho
with open('/Users/Usuario/Desktop/Mono.txt') as arquivo:
    #criação dos arrays para armazenar cada linha, e diferenciar cada elemento com split
    linhas1 = arquivo.readline().split(" ")
    linhas2 = arquivo.readline().split(" ")
    linhas3 = arquivo.readline().split(" ")
    linhas4 = arquivo.readline().split(" ")


#Organização dos processo por listas para facilitar a utilização no bloco de repetição
processos = linhas1[0], linhas2[0], linhas3[0], linhas4[0]
tipoProcessos = linhas1[1], linhas2[1], linhas3[1], linhas4[1]
tempoProcesso = linhas1[2], linhas2[2], linhas3[2], linhas4[2]
nums = [3, 2, 4, 1]

#import usado para utilizar a função time.sleep
import time

#bloco de repetição dentro de outra para poder usar o tempo de processo unica de cada
for a in range(4):
    for b in range(nums[a]):
        print("Executando o processo: ",processos[a])
        print("Tipo do processo: ",tipoProcessos[a])
        print("Tempo estimado da execução: ",tempoProcesso[a])

        print("Tempo restante: ", )
        #função para aguardar 1 segundo por volta
        time.sleep(1)

´´´´
