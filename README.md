# Ep_Design_Software
#Jogo Bacará
#Eric de Araújo
# 18/10/2020


import random

# Sorteando cartas
A = 1
J = 0
Q = 0
K = 0
lista_somatório = [A, 2, 3, 4, 5, 6, 7, 8, 9, 10, J, Q, K] * 4
lista_somatório[9] = 0
mesa_embaralha_cartas_1 = random.choice(lista_somatório)
mesa_embaralha_cartas_2 = random.choice(lista_somatório)
soma = mesa_embaralha_cartas_1 + mesa_embaralha_cartas_2  # somatório das cartas em mãos
mesa_embaralha_cartas_3 = random.choice(lista_somatório)
mesa_embaralha_cartas_4 = random.choice(lista_somatório)
soma_2 = mesa_embaralha_cartas_3 + mesa_embaralha_cartas_4
mesa_embaralha_cartas_5 = random.choice(lista_somatório)
mesa_embaralha_cartas_6 = random.choice(lista_somatório)
soma_3 = mesa_embaralha_cartas_5 + mesa_embaralha_cartas_6
mesa_embaralha_cartas_7 = random.choice(lista_somatório)
mesa_embaralha_cartas_8 = random.choice(lista_somatório)
soma_4 = mesa_embaralha_cartas_7 + mesa_embaralha_cartas_8


# Restrições soma

if soma >= 10:
    soma = soma - 10
if soma_2 >= 10:
    soma_2 = soma - 10

# -----------------------------------------------------------Background
print('-=' * 20)
print('{:^40}'.format('BACARÁ'))
print('-=' * 20)

nome_jogador = str(input('Seja Bem Vindo ao Bacará , por favor digite seu nome:'))
print('Olá {} , você tem inicialmente 2 fichas para começar suas apostas'.format(nome_jogador))
print('Sem mais enrolações, Vamos jogar!!')
print('''Escolha em que você quer apostar:
[1] Jogador
[2] Banco
[3] Empate''')

opcao = int(input('Qual sua aposta?'))  # pedindo que o usuario aposte
# -------------------------------------------------------------------------- Estrutura de Repetição
while opcao == 1 or opcao == 2 or opcao == 3:
    quantidade_fichas = int(input('Quantas fichas você quer apostar?'))
    if 1 <= quantidade_fichas <= 2:
        print('O jogador recebeu as cartas {} e {}'.format(mesa_embaralha_cartas_1, mesa_embaralha_cartas_2))
        print('Portanto , o somatório deu {}'.format(soma))
        if soma != 8 or soma != 9:
            if soma == 6 or soma == 7:
                print('Somatório insuficiente para distribuir mais um carta!')
                print('Vamos fazer uma nova aposta?')
                print('''Escolha em quem você quer apostar:
                [1] Jogador
                [2] Banco
                [3] Empate''')
                opcao = int(input('Qual sua aposta?'))  # pedindo que o usuario aposte
                while opcao == 1 or opcao == 2 or opcao == 3:
                    quantidade_fichas = int(input('Quantas fichas você quer apostar?'))
                    if quantidade_fichas==1:
                        print('O jogador recebeu as cartas {} e {}'.format(mesa_embaralha_cartas_3,mesa_embaralha_cartas_4))
                        print('Portanto , o somatório deu {}'.format(soma_2))
                        if soma!=8 or soma!=9:
                            print('Somatório insuficiente para distribuir mais um carta!')
                            print('Você não tem mais fichas para apostar')
                            print('FIM DO JOGO!!')
                        else:
                            print('Jogador Venceu!')

else:
    while opcao != 1 or opcao != 2 or opcao != 3:
        print('\033[1;31mNennhuma opção selecionada!\033[m')
        print('Você têm que apostar no Jogador  ou no Banco ou empate')
        print('Vamos tentar de novo!')
        opcao = int(input('Qual sua aposta?'))
        if opcao==1 or opcao ==2 or opcao==3:
            quantidade_fichas = int(input('Quantas fichas você quer apostar?'))
            if 1 <= quantidade_fichas <=2:
                print('O jogador recebeu as cartas {} e {}'.format(mesa_embaralha_cartas_5, mesa_embaralha_cartas_6))
                print('Portanto , o somatório deu {}'.format(soma_3))
                if soma_3 != 8 or soma_3 != 9:
                    if soma_3 == 6 or soma_3 == 7:
                        print('Somatório insuficiente para distribuir mais um carta!')
                        print('Vamos fazer uma nova aposta?')
                        print('''Escolha em quem você quer apostar:
                        [1] Jogador
                        [2] Banco
                        [3] Empate''')
                        opcao = int(input('Qual sua aposta?'))  # pedindo que o usuario aposte
                        while opcao == 1 or opcao == 2 or opcao == 3:
                            quantidade_fichas = int(input('Quantas fichas você quer apostar?'))
                            if quantidade_fichas == 1:
                                print('O jogador recebeu as cartas {} e {}'.format(mesa_embaralha_cartas_7,mesa_embaralha_cartas_8))
                                print('Portanto , o somatório deu {}'.format(soma_4))
                                if soma!=8 or soma!=9:
                                    print('Você não tem mais fichas!')
                                    print('Fim do Jogo!')
                                else:
                                    ('O Jogador venceu')
                else:
                    print('Jogador Venceu!')
            else:
                print('\033[1;31mTente novamente!\033[m')
                print('Você têm que apostar de acordo com sua quantidade de fichas')
                quantidade_fichas = int(input('Quantas fichas você quer apostar?'))



