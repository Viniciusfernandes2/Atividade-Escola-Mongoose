# Atividade-Escola-Mongoose

curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"07494812857\"}" 
{"nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","_id":"683633ec528913ff3969c100","__v":0}

curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Carlos Silva\", \"email\": \"carlos.silva@fatec.sp.gov.br\", \"cpf\": \"63479695051\"}" 
{"nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","_id":"68363555528913ff3969c101","__v":0}

curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Odete Roitman\", \"email\": \"odete.roitman@fatec.sp.gov.br\", \"cpf\": \"32082128016\"}" 
{"nome":"Odete Roitman","email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","_id":"683636fc528913ff3969c102","__v":0}

curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"07494812857\"}" 
{"message":"CPF ou e-Mail já em uso"}

curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": \"12345678910\"}" 
{"message":"12345678910 não é um CPF válido"}

curl.exe -X POST http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec\", \"cpf\": \"07494812857\"}" 
{"message":"henrique.louro@fatec não é um formato de e-mail válido"}

curl.exe -X GET http://localhost:3001/professor 
[{"_id":"683633ec528913ff3969c100","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},
{"_id":"68363555528913ff3969c101","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},
{"_id":"683636fc528913ff3969c102","nome":"Odete Roitman","email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}]

curl.exe -X PUT http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"id\":\"683636fc528913ff3969c102\",\"nome\": \"Odetinha Roitman\", \"email\": \"odetinha.roitman@fatec.sp.gov.br\", \"cpf\" : \"32082128016\"}" 
{"_id":"683636fc528913ff3969c102","nome":"Odetinha Roitman","email":"odetinha.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}

curl.exe -X DELETE http://localhost:3001/professor -H "Content-Type: application/json" -d "{\"id\":\"683636fc528913ff3969c102\"}" 
{"message":"Professor excluído com sucesso"}

curl.exe -X GET http://localhost:3001/professor 
[{"_id":"683633ec528913ff3969c100","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},
{"_id":"68363555528913ff3969c101","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0}]

curl.exe -X POST http://localhost:3001/disciplina -H "Content-Type: application/json" -d "{\"descricao\": \"Técnicas de Programação II\"}" 
{"descricao":"Técnicas de Programação II","_id":"68363f1a528913ff3969c110","__v":0}

curl.exe -X POST http://localhost:3001/disciplina -H "Content-Type: application/json" -d "{\"descricao\": \"Lógica de Programação\"}" 
{"descricao":"Lógica de Programação","_id":"68363f4e528913ff3969c111","__v":0}

curl.exe -X GET http://localhost:3001/disciplina 
[{"_id":"68363f1a528913ff3969c110","descricao":"Técnicas de Programação II","__v":0},
{"_id":"68363f4e528913ff3969c111","descricao":"Lógica de Programação","__v":0}]

curl.exe -X POST http://localhost:3001/professor_has_disciplina -H "Content-Type: application/json" -d "{\"professor\": \"683633ec528913ff3969c100\", \"disciplina\": \"68363f1a528913ff3969c110\"}" 
{"professor":"683633ec528913ff3969c100","disciplina":"68363f1a528913ff3969c110","_id":"68364375528913ff3969c120","__v":0}

curl.exe -X POST http://localhost:3001/professor_has_disciplina -H "Content-Type: application/json" -d "{\"professor\": \"68363555528913ff3969c101\", \"disciplina\": \"68363f4e528913ff3969c111\"}" 
{"professor":"68363555528913ff3969c101","disciplina":"68363f4e528913ff3969c111","_id":"683643df528913ff3969c121","__v":0}

curl.exe -X GET http://localhost:3001/professor_has_disciplina 
[{"_id":"68364375528913ff3969c120","professor":{"_id":"683633ec528913ff3969c100","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0}, 
  "disciplina":{"_id":"68363f1a528913ff3969c110","descricao":"Técnicas de Programação II","__v":0}}, 

 {"_id":"683643df528913ff3969c121","professor":{"_id":"68363555528913ff3969c101","nome":"Carlos Silva", "email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},
  "disciplina":{"_id":"68363f4e528913ff3969c111", "descricao":"Lógica de Programação","__v":0}}]



