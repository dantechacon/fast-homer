# fast-homer
def registrar_votos(votos):
    with open("votos.txt", "w") as arquivo:
        for voto in votos:
            arquivo.write(str(voto) + "\n")

def apurar_votos():
    votos = []
    
    with open("votos.txt", "r") as arquivo:
        for linha in arquivo:
            votos.append(int(linha.strip()))

    votos_bart = 0
    votos_homer = 0
    votos_nulos = 0

    for voto in votos:
        if voto == 1:
            votos_bart += 1
        elif voto == 2:
            votos_homer += 1
        else:
            votos_nulos += 1

    if votos_bart > votos_homer:
        candidato_mais_votado = "Bart"
        quantidade_mais_votado = votos_bart
    elif votos_homer > votos_bart:
        candidato_mais_votado = "Homer"
        quantidade_mais_votado = votos_homer
    else:
        candidato_mais_votado = "Empate"
        quantidade_mais_votado = votos_bart 

    if votos_bart < votos_homer:
        candidato_menos_votado = "Bart"
        quantidade_menos_votado = votos_bart
    elif votos_homer < votos_bart:
        candidato_menos_votado = "Homer"
        quantidade_menos_votado = votos_homer
    else:
        candidato_menos_votado = "Empate"
        quantidade_menos_votado = votos_bart 

    print("Resultado da votação:")
    print(f"Candidato mais votado: {candidato_mais_votado} com {quantidade_mais_votado} votos")
    print(f"Candidato menos votado: {candidato_menos_votado} com {quantidade_menos_votado} votos")
    print(f"Votos nulos: {votos_nulos}")

