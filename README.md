# Teste Backend BuyCo.

Este teste é apresentado aos candidatos as vagas de desenvolvimento back-end, o objetivo é avaliar seus conhecimentos em organização, estilo, boas práticas e habilidades.

________________________________________________


#### O Desafio:

Seu objetivo é criar uma simples API que deve conter as seguintes funcionalidades:

| MÉTODO | URI         | AÇÃO                      |
| ------ | ----------- | ------------------------- |
| GET    | /doc      | Lista as URLs disponíveis para serem chamadas e uma breve explicação de cada   |
| GET   | /info/{id}      | Obtém a quantidade de processamentos realizados utilizando aquele id            |
| POST    | /interpretar/{id} | Processa o texto passado pelo objeto  |



#### Requisitos funcionais:

- O retorno das URIs com o método GET deve ser um json. Utilize sua criatividade para retornar esses resultados.

- Entretanto o retorno do POST será mais específico:
  - A API deve receber um objeto com uma chave *text* e um texto para ser interpretado. Como o exemplo a seguir:

```json
{
	"text": "Esse será o primeiro contato com seu cliente, então, a primeira reunião com o possível comprador deve ser bem planejada! Divida os assuntos da reunião em temas para não esquecer de falar nada. E lembre-se, fale menos e escute mais. Ouça o que o possível comprador tem para dizer e identifique quais as demandas dele, porque ele quer investir no seu negócio. Assim, busque entender quais são as intenções do seu comprador, pós-venda da empresa. Nessa parte, você também conseguirá perceber as reais necessidades e objetivos do comprador, e verificar se corresponde com suas expectativas! Na sequência, apresente a solução para a demanda do comprador, que nesse caso é: a sua empresa! O objetivo é mostrar como a sua empresa é um investimento e como ela atende as demandas do seu comprador. Fale sobre os aspectos internos, as finanças, histórico, funcionários e detalhes do seu negócio. E conte sobre aspectos externos da empresa, a imagem da empresa no mercado e seus concorrentes. Tudo isso, a fim de deixar seu comprador a par das informações, o que aumenta as chances de sucesso na venda! Depois de comentar sobre o seu negócio, fale sobre você e seus sócios. Conte sobre sua vida profissional e idoneidade. Aqui, você se mostrará confiável para esse possível comprador. Esteja preparado para tirar dúvidas e responder qualquer pergunta que possa surgir. Por fim, fale sobre o valor do seu negócio. Crie a tratativa e o convide para uma visita à empresa. Pergunte ainda, quais as impressões que o possível comprador teve de seu negócio."
}
```

  - Deve-se usar a API que será enviada por email que retorna o seguinte corpo
```json
{
    "sentiment": "NEUTRAL",
    "sentimentScore": {
        "Positive": 0.019267577677965164,
        "Negative": 0.0009215825120918453,
        "Neutral": 0.9797793030738831,
        "Mixed": 0.000031589417631039396
    },
    "keyPhrases": [
        {
            "Score": 0.9977802634239197,
            "Text": "Esse",
            "BeginOffset": 0,
            "EndOffset": 4
        },
        {
            "Score": 0.9963236451148987,
            "Text": "o primeiro contato com seu cliente",
            "BeginOffset": 10,
            "EndOffset": 44
        },
        {
            "Score": 0.996285080909729,
            "Text": "a primeira reunião com o possível comprador",
            "BeginOffset": 53,
            "EndOffset": 96
        },
	[OCULTADAS PELO ESPAÇO],
        {
            "Score": 0.8249384760856628,
            "Text": "negócio",
            "BeginOffset": 1531,
            "EndOffset": 1538
        }
    ],
    "entities": [
        {
            "Score": 0.9913205504417419,
            "Type": "QUANTITY",
            "Text": "primeiro contato",
            "BeginOffset": 12,
            "EndOffset": 28
        },
        {
            "Score": 0.9793554544448853,
            "Type": "QUANTITY",
            "Text": "primeira reunião",
            "BeginOffset": 55,
            "EndOffset": 71
        },
        {
            "Score": 0.6773239374160767,
            "Type": "QUANTITY",
            "Text": "fale menos",
            "BeginOffset": 206,
            "EndOffset": 216
        },
        {
            "Score": 0.8153877258300781,
            "Type": "QUANTITY",
            "Text": "escute mais",
            "BeginOffset": 219,
            "EndOffset": 230
        },
        {
            "Score": 0.6690317392349243,
            "Type": "QUANTITY",
            "Text": "Tudo isso",
            "BeginOffset": 982,
            "EndOffset": 991
        },
        {
            "Score": 0.9173813462257385,
            "Type": "QUANTITY",
            "Text": "qualquer pergunta",
            "BeginOffset": 1322,
            "EndOffset": 1339
        }
    ]
}
```

- O Objetivo da atividade é:
	- Utilizar o *keyPhrases* para identificar quais as frases mais importantes do texto.
	- Extrair os períodos que contenham as frases mais importantes. (Lembre-se que período finaliza-se em um ponto final)
	- Retorne um *array* com os principais períodos do texto recebido.
	- Lembre-se de fazer um controle de quantas solicitações foram feitas por cada ID que chamou.
	- Não há necessidade de fazer controle do tipo de id (ele pode ser qualquer string/interger)
	- Não há necessidade de haver persistencia nos dados, ou seja, a partir do momento que o programa finaliza ele nâo precisa permanecer com as informações salvas.



#### O que seria um PLUS:

- O retorno dos ararys possuir um grau de importância, por exemplo:

```json
[
    {
        "sentence": "blablabla",
        "score": 0.99
    },
    {
        "sentence": "bfasdfadsnnjfsdajkfsa",
        "score": 0.85
    }
]
```

Você tem liberdade para escolher como calcular esse *score* para cada período encontrado.

- Tratamento de erros
- Testes unitários

#### Requisitos não funcionais:

- Sua aplicação deverá rodar localmente.
- Deverá ser utilizado alguma linguagem de programação de mercado (Dê preferencia a Node e/ou Python)


Qualquer dúvida: Envie um e-mail para paulo@buyco.com.br
