# Estagio.SmartAgri
Esse é o projeto que fiz, foi o meu primeiro contato com Python então espero que esteja bom, dei o meu melhor e tentei fazer o máximo que consegui.

from flask import Flask, jsonify, json
import requests

#pegar informações do Random Color 
app = Flask("SmartAgriColor")
cor = requests.get('https://random-data-api.com/api/color/random_color?size=%20&is_xml=true')
@app.route("/color", methods=["GET"])
def color():
    print("Sorteio de cores aleatorias:")
    return(cor.text)
#printar a lista de cores na tela    
@app.route("/color<string:lista.sorteio>", methods=["GET"])
def lista(cor):
    print("Lista de cores:")
    return jsonify(lista)   
#procurar as cores pelo seu id
@app.route("/color<int:id>", methods=["GET"])
def id(cor):
    for cor in cor:
        if cor['id'] == id: 
            return jsonify(id)
#A ideia front-end é que haveriam na página 2 botoes em uma tela bem colorida, onde o usuário escolheria apenas o sorteio de 
#cores ou o sorteio mais o mapa da "linha de chegada" de cada cor, quase como um jogo, poderia haver animações até que o sorteio
#das cores fosse finalizado.
#Os próximos comandos devem ser para juntar o id de cada cor e o tempo de chegada para que eles possam fazer assim um 
#gráfico em plano (x,y) de cores;
app.run(port=2000, debug=True)
