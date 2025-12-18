## Calculadora de partidas Rankeadas

```py

players = [
]

def absorvendoInfo ():
    nome = input("qual nome do seu player? \n")
    vitorias = int(input("quantas vitórias você teve em partidas? \n"))
    derrotas = int(input("quantas derrotas você teve em partidas? \n"))

    player = {"nome": nome, "vitorias": vitorias, "derrotas": derrotas}

    players.append(player)
    return player

def calculoPontuacao(player):
    CalVitorias = player["vitorias"] * 3
    CalDerrotas = player["derrotas"] * 2

    pontuacaoFinal = CalVitorias - CalDerrotas

    player["pontuacaoFinal"] = pontuacaoFinal
    players.append(player)
    return player

def classificandoRank(player):
    print(player)
    if player["pontuacaoFinal"] <= 10:
        rank = ("Ferro")
    elif player["pontuacaoFinal"] <= 20:
        rank = ("Bronze")
    elif player["pontuacaoFinal"] <= 50:
        rank = ("Prata")
    elif player["pontuacaoFinal"] <= 80:
        rank = ("Ouro")
    elif player["pontuacaoFinal"] <= 90:
        rank = ("Diamante")
    elif player["pontuacaoFinal"] <= 100:
        rank = ("Lendário")
    else:
        rank = ("Imortal")

    print(f"\nO Herói tem de saldo de {player["vitorias"]} está no ranking {rank}")

player = absorvendoInfo ()
player = calculoPontuacao(player) 
classificandoRank(player)
