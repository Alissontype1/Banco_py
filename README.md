menu = ("""
----Banco Milenium----
      
    [1] Depositar
    [2] Sacar
    [3] Extrato
    [4] Sair

----------------------
         """
        )

saldo = 0
limite = 500
extrato = ""
numero_saques = 0
LIMITE_SAQUES = 3

while True :
        opcao = input(menu)

        if (opcao)  == '1':

                valor= float(input('Informe o valor de deposito: '))

                if valor > 0:
                        saldo += valor
                        extrato += f"Depósito: R$ {valor:.2f}\n"
                else:
                        print('Erro na operação tente novamente!')

        elif (opcao) == '2':
                valor= float(input('Digique o valor que gostaria de ser sacado: '))
                exedeu_saldo = valor > saldo
                exedeu_limite = valor > limite
                exedeu_saques = numero_saques >= LIMITE_SAQUES

                if exedeu_saldo:
                        print('Erro!! você não tem saldo suficiente.')
                elif exedeu_limite:
                        print('Erro!! você exedeu o valor limite de saque.')
                elif exedeu_saques:
                        print('Erro!! você exedeu o limite de saques diarios.')
                elif valor > 0:
                        saldo -= valor
                        extrato += f' Saque: R$ {valor:.2f}\n'
                        numero_saques += 1
                else:
                        print('Erro!! Valoe informado é inválido')




        elif (opcao) == '3':
                print('\n==Extrato de movimentações==')
                print('Não foram realizadas movimentações.'if not extrato else extrato)
                print(f'\nSaldo: R$ {saldo:.2f}')
                print('=============================')


        elif (opcao) == '4':

                print('Obrigado, tenha um bom dia!!')

                break

        else:
                print('Operação invalida!!\nTente outra opção!!')


