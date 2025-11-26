# Desafio-Free-Fire-Tema-2Desafio Free Fire – Tema 2

Este projeto representa uma simulação simples de tomada de decisão inspirada em mecânicas presentes em jogos como Free Fire. O objetivo é demonstrar como um sistema de IA básico pode escolher ações considerando variáveis como vida, munição e distância até o inimigo.

Como funciona?

A lógica é definida na classe Player, onde:

Se a vida está muito baixa → o jogador foge

Se há pouca munição → o jogador procura loot

Se o inimigo está perto → o jogador ataca

Caso contrário → movimentação tática

Foi implementada uma função simulate_round() que gera valores aleatórios para simular diferentes cenários.

Tecnologias

Python 3

Programação orientada a objetos

Simulação com números aleatórios
=====================  README.md  =====================

# Desafio Free Fire – Tema 2

Este projeto apresenta uma simulação simples de estratégia para tomada de decisão em uma partida de Free Fire.

## 📌 Objetivo
O código demonstra uma lógica de IA básica que:
- Analisa a distância até o inimigo  
- Verifica os recursos do jogador  
- Escolhe uma ação (atacar, fugir ou procurar loot)

## 🚀 Como executar
1. Instale Python 3.10+  
2. Execute:

python src/main.py

## 📂 Estrutura
freefire_project/
│── README.md
└── src/
    └── main.py

## 📜 Licença
Uso livre para fins educacionais.


=====================  src/main.py  =====================

import random

class Player:
    def __init__(self, health, ammo, distance_to_enemy):
        self.health = health
        self.ammo = ammo
        self.distance_to_enemy = distance_to_enemy

    def decide_action(self):
        if self.health < 30:
            return "Fugir (vida baixa)"
        if self.ammo < 3:
            return "Procurar loot (pouca munição)"
        if self.distance_to_enemy < 20:
            return "Atacar inimigo"
        return "Mover-se com cautela"

def simulate_round():
    health = random.randint(10, 100)
    ammo = random.randint(0, 10)
    distance = random.randint(5, 200)

    player = Player(health, ammo, distance)
    decision = player.decide_action()

    print("=== Simulação de Estratégia Free Fire ===")
    print(f"Vida: {health}")
    print(f"Munição: {ammo}")
    print(f"Distância até o inimigo: {distance}m")
    print(f"Ação tomada: {decision}")

if __name__ == "__main__":
    simulate_round()


=====================  ESTRUTURA COMPLETA  =====================

freefire_project/
│── README.md
└── src/
    └── main.py

==============================================================
