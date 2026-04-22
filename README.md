# lista3.py
#1.Faça um programa que imprima todos os números de 1 até 100.
def q1():
    for i in range(1, 101):
        print(i)
#2. Faça um programa que imprima todos os números pares de 100 até 1.
def q2():
    for i in range(100, 0, -1):
        if i % 2 == 0:
            print(i)
#3. Faça um programa que imprima os múltiplos de 5, no intervalo de 1 até 500.
def q3():
    for i in range(1, 501):
        if i % 5 == 0:
            print(i)
#4. Faça um programa que permita entrar com o nome, a idade e o sexo de 20
#pessoas.O programa deve imprimir o nome da pessoa se ela for do sexo masculino
#e tiver mais de 21 anos.
def q4():
    for _ in range(20):
        nome = input("Nome: ")
        idade = int(input("Idade: "))
        sexo = input("Sexo: ").upper()
        if sexo == 'M' and idade > 21:
            print(nome)
#5. Sabendo-se que a unidade lógica e aritmética calcula o produto através de somas
#sucessivas, crie um programa que calcule o produto de dois números inteiros
#lidos. Suponha que os números lidos sejam positivos.
def q5():
    a = int(input())
    b = int(input())
    res = 0
    for _ in range(b):
        res += a
    print(res)
#6. Crie um programa que imprima os 20 primeiros termos da série de Fibonacci.
#Observação: os dois primeiros termos desta série são 1 e 1 e os demais são gerados
#a partir da soma dos anteriores. Exemplo:
#• 1 + 1 = 2, terceiro termo;
#• 1 + 2 = 3, quarto termo, etc.
# 1 1 2 3 5 8 13 21
def q6():
    a, b = 1, 1
    print(a, b, end=" ")
    for _ in range(18):
        a, b = b, a + b
        print(b, end=" ")
    print()
#7. Crie um programa que permita entrar com o nome, a nota da
#prova 1 e da prova 2 de 15 alunos. Ao final, imprimir uma listagem, contendo:
#nome, nota da prova 1, nota da prova 2, e média das notas de cada aluno. Ao final,
#imprimir a média geral da turma.
def q7():
    soma = 0
    for _ in range(15):
        nome = input()
        n1 = float(input())
        n2 = float(input())
        m = (n1+n2)/2
        soma += m
        print(nome, n1, n2, m)
    print("Média geral:", soma/15)
#8. Faça um programa que permita entrar com o nome e o salário bruto de 10 pessoas.
#Após ler os dados, imprimir o nome e o valor da alíquota do imposto de renda
#calculado conforme a tabela a seguir:
#Salário IRPF
#Salário menor que R$1300,00 Isento
#Salário maior ou igual a R$1300,00 e menor que R$2300,00 10% do salário bruto
#Salário maior ou igual a R$2300,00 15% do salário bruto
def q8():
    for _ in range(10):
        nome = input()
        sal = float(input())
        if sal < 1300:
            print(nome, "Isento")
        elif sal < 2300:
            print(nome, sal*0.1)
        else:
            print(nome, sal*0.15)
#9. No dia da estreia do filme "Procurando Dory", uma grande emissora de TV realizou
#uma pesquisa logo após o encerramento do filme. Cada espectador respondeu
#a um questionário no qual constava sua idade e a sua opinião em relação ao filme:
#excelente - 3; bom - 2; regular - 1. Criar um programa que receba a idade e a
#opinião de 20 espectadores, calcule e imprima:
#• A média das idades das pessoas que responderam excelente;
#• A quantidade de pessoas que responderam regular;
#• A percentagem de pessoas que responderam bom entre todos os expectadores
#analisados.
def q9():
    soma = cont_exc = cont_reg = cont_bom = 0
    for _ in range(20):
        idade = int(input())
        op = int(input())
        if op == 3:
            soma += idade
            cont_exc += 1
        elif op == 2:
            cont_bom += 1
        else:
            cont_reg += 1
    if cont_exc:
        print(soma/cont_exc)
    print(cont_reg)
    print((cont_bom/20)*100)
#10. Em um campeonato Europeu de Volleyball, se inscreveram 30 países. Sabendo-se
#que na lista oficial de cada país consta, além de outros dados, peso e idade de 12
#jogadores, crie um programa que apresente as seguintes informações:
#
#• O peso médio e a idade média de cada um dos times;
#• O atleta mais pesado de cada time;
#• O atleta mais jovem de cada time;
#• O peso médio e a idade média de todos os participantes.
def q10():
    total_i = total_p = total = 0
    for _ in range(30):
        si = sp = 0
        max_p = 0
        min_i = 999
        for _ in range(12):
            i = int(input())
            p = float(input())
            si += i
            sp += p
            total_i += i
            total_p += p
            total += 1
            if p > max_p: max_p = p
            if i < min_i: min_i = i
        print(si/12, sp/12, max_p, min_i)
    print(total_i/total, total_p/total)
#11. Construa um programa que leia vários números e informe quantos números
#entre 100 e 200 foram digitados. Quando o valor 0 (zero) for lido, o algoritmo
#deverá cessar sua execução.

def q11():
    cont = 0
    while True:
        n = int(input())
        if n == 0: break
        if 100 <= n <= 200:
            cont += 1
    print(cont)
#12. Dado um país A, com 5 milhões de habitantes e uma taxa de natalidade de 3% ao
#ano, e um país B com 7 milhões de habitantes e uma taxa de natalidade de 2% ao
#ano, fazer um programa que calcule e imprima o tempo necessário para que a
#população do país A ultrapasse a população do país B.
def q12():
    a = 5000000
    b = 7000000
    anos = 0
    while a <= b:
        a *= 1.03
        b *= 1.02
        anos += 1
    print(anos)
#13. Uma empresa de fornecimento de energia elétrica faz a leitura mensal dos medidores
#de consumo. Para cada consumidor, são digitados os seguintes dados:
#• número do consumidor
#• quantidade de kWh consumidos durante o mês
#• tipo (código) do consumidor
#1-residencial, preço em reais por kWh = 0,3
#2-comercial, preço em reais por kWh = 0,5
#3-industrial, preço em reais por kWh = 0,7
#Os dados devem ser lidos até que seja encontrado o consumidor com número 0
#(zero). O programa deve calcular e imprimir:
#• O custo total para cada consumidor
#• O total de consumo para os três tipos de consumidor
#• A média de consumo dos tipos 1 e 2
def q13():
    total = [0,0,0]
    while True:
        n = int(input())
        if n == 0: break
        k = float(input())
        t = int(input())
        preco = [0.3,0.5,0.7]
        print(k*preco[t-1])
        total[t-1] += k
    print(total)
    print((total[0]+total[1])/2)
#14. Faça um programa que leia vários números inteiros e apresente o fatorial de cada
#número. O algoritmo encerra quando se digita um número menor do que 1.
def q14():
    while True:
        n = int(input())
        if n < 1: break
        f = 1
        for i in range(1,n+1):
            f *= i
        print(f)
#15. Faça um programa que permita entrar com a idade de várias pessoas e
#imprima:
#• total de pessoas com menos de 21 anos
#• total de pessoas com mais de 50 anos
def q15():
    m21 = m50 = 0
    while True:
        i = int(input())
        if i < 0: break
        if i < 21: m21 += 1
        if i > 50: m50 += 1
    print(m21, m50)
#16. Sabendo-se que a unidade lógica e aritmética calcula a divisão por meio de subtrações
#sucessivas, criar um algoritmo que calcule e imprima o resto da divisão de
#números inteiros lidos. Para isso, basta subtrair o divisor ao dividendo, sucessivamente,
#até que o resultado seja menor do que o divisor. O número de subtrações
#realizadas corresponde ao quociente inteiro e o valor restante da subtração corresponde
#ao resto. Suponha que os números lidos sejam positivos e que o dividendo
#seja maior do que o divisor.
#Exemplo:
#  10 / 5
#  10 é o Dividendo
#  5 é o Divisor
#  2 é o Quociente (resultado inteiro da divisão)
#  0 é o Resto da Divisão
def q16():
    d = int(input())
    v = int(input())
    q = 0
    while d >= v:
        d -= v
        q += 1
    print(q, d)
#17. Crie um programa que possa ler um conjunto de pedidos de compra e
#calcule o valor total da compra. Cada pedido é composto pelos seguintes campos:
#• número de pedido
#• data do pedido (dia, mês, ano)
#• preço unitário
#• quantidade
#O programa deverá processar novos pedidos até que o usuário digite 0 (zero)
#como número do pedido.
def q17():
    total = 0
    while True:
        n = int(input())
        if n == 0: break
        p = float(input())
        q = int(input())
        total += p*q
    print(total)
#18. Uma pousada estipulou o preço para a diária em R$30,00 e mais uma taxa de
#serviços diários de:
#• R$15,00, se o número de dias for menor que 10;
#• R$8,00, se o número de dias for maior ou igual a 10;
#Faça um programa que imprima o nome, a conta e o número da conta de cada
#cliente e ao final o total faturado pela pousada.
#O programa deverá ler novos clientes até que o usuário digite 0 (zero) como
#número da conta.
def q18():
    total = 0
    while True:
        c = int(input())
        if c == 0: break
        nome = input()
        d = int(input())
        taxa = 15 if d < 10 else 8
        val = d*30 + d*taxa
        total += val
        print(nome, c, val)
    print(total)
#19. Em uma Universidade, os alunos das turmas de informática fizeram uma prova
#de algoritmos. Cada turma possui um número de alunos. Criar um programa que
#imprima:
#• quantidade de alunos aprovados;
#• média de cada turma;
#• percentual de reprovados.
#Obs.: Considere aprovado com nota >= 7.0
def q19():
    aprov = soma = total = 0
    n = int(input())
    for _ in range(n):
        nota = float(input())
        soma += nota
        total += 1
        if nota >= 7:
            aprov += 1
    print(aprov, soma/total, ((total-aprov)/total)*100)
#20. Uma pesquisa de opinião realizada no Rio de Janeiro, teve as seguintes perguntas:
#• Qual o seu time de coração?
#1-Fluminense;
#2-Botafogo;
#3-Vasco;
#4-Flamengo;
#5-Outros
#• Onde você mora?
#1-RJ;
#2-Niterói;
#3-Outros
#• Qual o seu salário?
#Faça um programa que imprima:
#• o número de torcedores por clube;
#• a média salarial dos torcedores do Botafogo;
#• o número de pessoas moradoras do Rio de Janeiro, torcedores de outros
#clubes;
#• o número de pessoas de Niterói torcedoras do Fluminense
#3.12. Exercícios da Aula 73
#Obs.: O programa encerra quando se digita 0 para o time.
def q20():
    tor = [0]*5
    total = 0
    sal_b = cont_b = 0
    rj_out = nit_flu = 0
    while True:
        t = int(input())
        if t == 0: break
        l = int(input())
        s = float(input())
        tor[t-1]+=1
        total+=1
        if t==2:
            sal_b+=s
            cont_b+=1
        if l==1 and t==5:
            rj_out+=1
        if l==2 and t==1:
            nit_flu+=1
    print(tor)
    if cont_b: print(sal_b/cont_b)
    print(rj_out, nit_flu)
#21. Em uma universidade cada aluno possui os seguintes dados:
#• Renda pessoal;
#• Renda familiar;
#• Total gasto com alimentação;
#• Total gasto com outras despesas;
#Faça um programa que imprima a porcentagem dos alunos que gasta acima de
#R$200,00 com outras despesas. O número de alunos com renda pessoal maior
#que a renda familiar e a porcentagem gasta com alimentação e outras despesas
#em relação às rendas pessoal e familiar.
#Obs.: O programa encerra quando se digita 0 para a renda pessoal.
def q21():
    total = acima = maior = 0
    while True:
        rp = float(input())
        if rp == 0: break
        rf = float(input())
        a = float(input())
        o = float(input())
        total+=1
        if o>200: acima+=1
        if rp>rf: maior+=1
    print((acima/total)*100 if total else 0, maior)
#22. Crie um programa que ajude o DETRAN a saber o total de recursos que foram
#arrecadados com a aplicação de multas de trânsito.
#O algoritmo deve ler as seguintes informações para cada motorista:
#• número da carteira de motorista (de 1 a 4327);
#• número de multas;
#• valor de cada uma das multas.
#Deve ser impresso o valor da dívida para cada motorista e ao final da leitura o
#total de recursos arrecadados (somatório de todas as multas). O programa deverá
#imprimir também o número da carteira do motorista que obteve o maior número
#de multas.
#Obs.: O programa encerra ao ler a carteira de motorista de valor 0.
def q22():
    total = 0
    max_m = 0
    max_c = 0
    while True:
        c = int(input())
        if c == 0: break
        q = int(input())
        soma = 0
        for _ in range(q):
            soma += float(input())
        print(soma)
        total += soma
        if q > max_m:
            max_m = q
            max_c = c
    print(total, max_c)
#23. Crie um programa que leia um conjunto de informações (nome, sexo, idade, peso
#e altura) dos atletas que participaram de uma olimpíada, e informar:
#• a atleta do sexo feminino mais alta;
#• o atleta do sexo masculino mais pesado;
#• a média de idade dos atletas.
#Obs.: Deverão se lidos dados dos atletas até que seja digitado o nome @ para um
#atleta.
#Para resolver este exercício, consulte a aula 7 que aborda o tratamento de strings,
#como comparação e atribuição de textos.
def q23():
    soma = total = 0
    max_f = 0
    max_m = 0
    while True:
        nome = input()
        if nome == "@": break
        s = input().upper()
        i = int(input())
        p = float(input())
        a = float(input())
        soma+=i
        total+=1
        if s=='F' and a>max_f: max_f=a
        if s=='M' and p>max_m: max_m=p
    print(max_f, max_m, soma/total if total else 0)
#24. Faça um programa que calcule quantos litros de gasolina são usados em uma
#viagem, sabendo que um carro faz 10 km/litro. O usuário fornecerá a velocidade
#do carro e o período de tempo que viaja nesta velocidade para cada trecho do
#percurso. Então, usando as fórmulas distância = tempo x velocidade e litros
#consumidos = distância / 10, o programa computará, para todos os valores não negativos
#de velocidade, os litros de combustível consumidos. O programa deverá
#imprimir a distância e o número de litros de combustível gastos naquele trecho.
#Deverá imprimir também o total de litros gastos na viagem. O programa encerra
#quando o usuário informar um valor negativo de velocidade.
#74 Aula 3. Estruturas de Iteração
def q24():
    total = 0
    while True:
        v = float(input())
        if v < 0: break
        t = float(input())
        d = v*t
        l = d/10
        total += l
        print(d, l)
    print(total)
#25. Faça um programa que calcule o imposto de renda de um grupo de contribuintes,
#considerando que:
#a) os dados de cada contribuinte (CIC, número de dependentes e renda bruta
#anual) serão fornecidos pelo usuário via teclado;
#b) para cada contribuinte será feito um abatimento de R$600 por dependente;
#c) a renda líquida é obtida diminuindo-se o abatimento com os dependentes
#da renda bruta anual;
#d) para saber quanto o contribuinte deve pagar de imposto, utiliza-se a tabela
#a seguir:
#Renda Líquida Imposto
#até R$1000 Isento
#de R$1001 a R$5000 15%
#acima de R$5000 25%
#e) o valor de CIC igual a zero indica final de dados;
#f ) o programa deverá imprimir, para cada contribuinte, o número do CIC e o
#imposto a ser pago;
#g) ao final o programa deverá imprimir o total do imposto arrecadado pela
#Receita Federal e o número de contribuintes isentos;
#h) leve em consideração o fato de o primeiro CIC informado poder ser zero.
def q25():
    total = isento = 0
    while True:
        cic = int(input())
        if cic == 0: break
        dep = int(input())
        r = float(input())
        liq = r - dep*600
        if liq <= 1000:
            imp = 0
            isento+=1
        elif liq <= 5000:
            imp = liq*0.15
        else:
            imp = liq*0.25
        total += imp
        print(cic, imp)
    print(total, isento)
#26. Foi feita uma pesquisa de audiência de canal de TV em várias casas de uma
#certa cidade, em um determinado dia. Para cada casa visitada foram fornecidos o
#número do canal (4, 5, 7, 12) e o número de pessoas que estavam assistindo a ele
#naquela casa. Se a televisão estivesse desligada, nada seria anotado, ou seja, esta
#casa não entraria na pesquisa. Criar um programa que:
#• Leia um número indeterminado de dados, isto é, o número do canal e o
#número de pessoas que estavam assistindo;
#• Calcule e imprima a porcentagem de audiência em cada canal.
#Obs.: Para encerrar a entrada de dados, digite o número do canal zero.
def q26():
    canais = {4:0,5:0,7:0,12:0}
    total = 0
    while True:
        c = int(input())
        if c == 0: break
        p = int(input())
        if c in canais:
            canais[c]+=p
            total+=p
    for k in canais:
        print(k, (canais[k]/total)*100 if total else 0)
#27. Crie um programa que calcule e imprima o CR do período para os alunos de
#computação. Para cada aluno, o algoritmo deverá ler:
#• número da matrícula;
#• quantidade de disciplinas cursadas;
#• notas em cada disciplina;
#Além do CR de cada aluno, o programa deve imprimir o melhor CR dos
#alunos que cursaram 5 ou mais disciplinas.
#• fim da entrada de dados é marcada por uma matrícula inválida (matrículas
#válidas de 1 a 5000);
#• CR do aluno é igual à média aritmética de suas notas.
def q27():
    melhor = 0
    while True:
        m = int(input())
        if m<1 or m>5000: break
        q = int(input())
        soma = 0
        for _ in range(q):
            soma += float(input())
        cr = soma/q
        print(cr)
        if q>=5 and cr>melhor:
            melhor = cr
    print(melhor)
#28. Construa um programa que receba a idade, a altura e o peso de várias pessoas,
#Calcule e imprima:
#• a quantidade de pessoas com idade superior a 50 anos;
#• a média das alturas das pessoas com idade entre 10 e 20 anos;
#• a porcentagem de pessoas com peso inferior a 40 quilos entre todas as
#pessoas analisadas.
def q28():
    cont50 = cont1020 = cont40 = total = 0
    soma_alt = 0
    while True:
        i = int(input())
        if i < 0: break
        a = float(input())
        p = float(input())
        total+=1
        if i>50: cont50+=1
        if 10<=i<=20:
            soma_alt+=a
            cont1020+=1
        if p<40: cont40+=1
    print(cont50, soma_alt/cont1020 if cont1020 else 0, (cont40/total)*100 if total else 0)
#29. Construa um programa que receba o valor e o código de várias mercadorias
#vendidas em um determinado dia. Os códigos obedecem a lista a seguir:
#L-limpeza
#A-Alimentação
#H-Higiene
#Calcule e imprima:
#• o total vendido naquele dia, com todos os códigos juntos;
#• o total vendido naquele dia em cada um dos códigos.
#Obs.: Para encerrar a entrada de dados, digite o valor da mercadoria zero.
def q29():
    tot = {'L':0,'A':0,'H':0}
    total = 0
    while True:
        v = float(input())
        if v == 0: break
        c = input().upper()
        if c in tot:
            tot[c]+=v
        total+=v
    print(total, tot)
#30. Faça um programa que receba a idade e o estado civil (C-casado, S-solteiro, V-viúvo
#e D-desquitado ou separado) de várias pessoas. Calcule e imprima:
#• a quantidade de pessoas casadas;
#• a quantidade de pessoas solteiras;
#• a média das idades das pessoas viúvas;
#• a porcentagem de pessoas desquitadas ou separadas dentre todas as pessoas
#analisadas.
#Obs.: Para encerrar a entrada de dados, digite um número menor que zero para a
#idade.
def q30():
    c = s = d = total = soma_v = cont_v = 0
    while True:
        i = int(input())
        if i < 0: break
        e = input().upper()
        total+=1
        if e=='C': c+=1
        elif e=='S': s+=1
        elif e=='V':
            soma_v+=i
            cont_v+=1
        elif e=='D': d+=1
    print(c, s, soma_v/cont_v if cont_v else 0, (d/total)*100 if total else 0)

# --- Menu Principal ---

menu = '''
--- LISTA DE EXERCÍCIOS (1-30) ---
Escolha o número da questão para executar.

Digite a opção: '''

try:
    opcao = input(menu)
    if opcao.isdigit() and 1 <= int(opcao) <= 25:
        eval(f'q{opcao}()')
    else:
        print("Opção inválida!")
except Exception as e:
    print(f"Erro: {e}")
