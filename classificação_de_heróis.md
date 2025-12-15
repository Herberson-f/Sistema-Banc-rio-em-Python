## Desafio Classificador de nível de Herói

projeto para treinamento de logica apenas.

```py

personagem = input("Qual seu personagem: ")
XP = int(input("Quantos XP tem seu personagem: "))
nivel = ""

if XP <= 1000:
    nivel = "Ferro"
elif XP >= 1.001:
    nivel = "Bronze"
elif XP >= 2.001:
    nivel = "Prata"
elif XP >= 5.001:
    nivel = "Ouro"
elif XP >= 7.001:
    nivel = "Platina"
elif XP >= 8.001:
    nivel = "Ascendente"
elif XP >= 9.001 :
    nivel = "Imortal"
elif XP >= 10.001:
    nivel = "Radiante"
else:
    nivel = "indefinido"


print(f"O {personagem} nivel: {nivel}")
