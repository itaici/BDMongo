# Vai começar o Campeonato os times ja estão escalados.

Foram criadas quatro tabelas: Classificacao, Times, Jogos e Jogadores.

Assim com os dados inseridos foram realizadas as sequintes operações:

db.getCollection('Times').find({Nome: 'São Caetano'})

db.getCollection('Jogos').find({$or:[{"Mandante": 'São Caetano'},{"Visitante": 'São Caetano'}]})

db.getCollection('Classificacao').find({Nome: 'São Caetano'})

db.getCollection('Classificacao').find({Nome: /.*São*./})

db.getCollection('Jogos').update({"Mandante": 'São Caetano'},{$set:{"Gols_mandante": 3, Gols_visitantes:2}});

db.getCollection('Classificacao').update({"Nome": 'São Caetano'},{$set:{"Pontos": 3, "Jogos":1, "Vitorias":1, "Gols_pro": 3, "Gols_contra": 2}});

db.getCollection('Classificacao').find().sort({"Pontos": -1, "Vitorias": -1})
