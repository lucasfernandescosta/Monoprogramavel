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
    #fechando arquivo txt que foi aberto para leitura
    arquivo.close()

#Organização dos processo por listas para facilitar a utilização no bloco de repetição
processos = linhas1[0], linhas2[0], linhas3[0], linhas4[0]
tipoProcessos = linhas1[1], linhas2[1], linhas3[1], linhas4[1]
tempoProcesso = linhas1[2], linhas2[2], linhas3[2], linhas4[2]
nums = [3, 2, 4, 1]

#import usado para utilizar a função time.sleep
import time
#Definição de variáveis para receber tempo de execução total, CPU e ES
acumTotal = 0
acumCPU=0
acumES=0
#bloco de repetição dentro de outra para poder usar o tempo de processo unica de cada
for a in range(4):
    for b in range(nums[a]):
        print("Executando o processo: ",processos[a])
        print("Tipo do processo: ",tipoProcessos[a])
        print("Tempo estimado da execução: ",tempoProcesso[a])
        print("Tempo restante: ", nums[a]-b,"segundo(s)")
        #Acumulador para contar o tempo total de todos os processos
        acumTotal = acumTotal + 1
        #Acumulador para contar tempo de processo se o tipo do processo for CPU
        if tipoProcessos[a] == "cpu":
            acumCPU = acumCPU + 1
        #Acumulador para contar tempo de processo se o tipo do processo for ES
        if tipoProcessos[a] == "es":
            acumES = acumES + 1
        #função para aguardar 1 segundo por volta
        time.sleep(1)
#Cálculo do tempo médio de processos total
tempMedio=acumTotal/4

#Criação do arquivo txt para poder ser escrito
with open('/Users/Usuario/Desktop/saida.txt', 'w') as arq:
    #linhas para escrever dentro do arquivo de texto criado
    arq.write('Tempo total de execução:')
    arq.write(str(acumTotal))
    arq.write('\nTempo total de execução processos CPU:')
    arq.write(str(acumCPU))
    arq.write('\nTempo total de execução processos ES:')
    arq.write(str(acumES))
    arq.write('\nTempo de espera médio dos processos:')
    arq.write(str(tempMedio))
    arq.write('es            -')
    arq.write('cpu      ----')
    arq.write('es     --')
    arq.write('cpu ---')
    #fechando o arquivo criado aberto
    arq.close()

´´´´
