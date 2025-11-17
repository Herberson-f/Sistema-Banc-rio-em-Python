# A seguir deixarei o codigo usado para esse projeto.

```python

usuarios = [
    {"nome": "Ana", "cpf": "123", "saldo": 500, "extrato":""},
    {"nome": "Bruno", "cpf": "456", "saldo": 1200, "extrato":""},
    {"nome": "Carla", "cpf": "789", "saldo": 3000, "extrato":""}
]
cpf_existe = ""

def cadastro():
    print("Oque deseja? \n 1. Login \n 2. Cadastro")
    decisao = input("\nescreva a identação da ação desejada: ")
    if decisao == '2':

        nome = input("qual seu nome? ")
        cpf = input("qual seu CPF: ")
        saldo = 0

        usuario = {"nome": nome, "cpf": cpf, "saldo": saldo, "extrato": ""}

        usuarios.append( usuario )

        print(f"Usuário salvo com sucesso! {nome} / {cpf} / {saldo}")
        print("faça seu primeiro deposito")
        return usuario

    elif decisao == '1':
        cpf_existe = input("Digite seu CPF: ")

        for usuario in usuarios:
            if usuario["cpf"] == cpf_existe:
                return usuario
    return None

def saque(usuario):
    print("================SAQUE================\n")
    valor_saque = float(input("qual o valor de saque? "))
    if valor_saque < usuario["saldo"]:
        usuario["saldo"] -= valor_saque

        usuario['extrato'] += f"Saque: R$ {usuario["saldo"]:.2f}\n"
        print(f"Saque realizado! Saldo restante: R$ {usuario["saldo"]:.2f}")

        return usuario
    
    else:
        print("Não foi possível realizar o saque: saldo insuficiente.")
        return usuario


def deposito(usuario):
        print("===============DEPÓSITO===============\n")
        valor_deposito = float(input(f"qual o valor de deposito? "))
        usuario["saldo"] += valor_deposito
        print(f"seu novo saldo é: {usuario["saldo"]}")

        usuario["extrato"] += f'depósito: R$ {usuario["saldo"]:.2f}'
        

        return usuario

def extratoo(usuario):
    print("\n===============EXTRATO==============")
    print(usuario["extrato"] if not "não há movimentações" else usuario["extrato"])
    print(f"Saldo: R$ {usuario["saldo"]:}\n")


def sistema_bancario():
    usuario = cadastro()
    print(usuario)
    while True:
        print("\n===============MENU===============\nEscolha uma das opções abaixo: \n s. saque \n d. deposito \n e. extrato \n sa. sair \n===============OPÇÃO===============")

        acao_desejada = input("Escreva aqui: ").lower()
        if acao_desejada in ["s", "d", "e", "sa"]:
            try:    
                if acao_desejada == "s":
                    saque(usuario)

                elif acao_desejada == "d":
                    deposito(usuario) 
                    
                elif acao_desejada == "e":
                    extratoo(usuario)
                    
                elif acao_desejada == "sa":
                    print("Saindo do sistema...")
                    break

            except ValueError:
                print("Erro: Por favor, insira valores válidos.")
        else:
            print("Opção inválida. Tente novamente.")


sistema_bancario()
```
