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
        {
            "Score": 0.9955105781555176,
            "Text": "os assuntos da reunião",
            "BeginOffset": 128,
            "EndOffset": 150
        },
        {
            "Score": 0.9634622931480408,
            "Text": "temas",
            "BeginOffset": 154,
            "EndOffset": 159
        },
        {
            "Score": 0.9983154535293579,
            "Text": "nada",
            "BeginOffset": 187,
            "EndOffset": 191
        },
        {
            "Score": 0.7722684144973755,
            "Text": "o que",
            "BeginOffset": 237,
            "EndOffset": 242
        },
        {
            "Score": 0.9995891451835632,
            "Text": "o possível comprador",
            "BeginOffset": 243,
            "EndOffset": 263
        },
        {
            "Score": 0.9105475544929504,
            "Text": "quais as demandas",
            "BeginOffset": 293,
            "EndOffset": 310
        },
        {
            "Score": 0.9999289512634277,
            "Text": "ele",
            "BeginOffset": 324,
            "EndOffset": 327
        },
        {
            "Score": 0.6109952926635742,
            "Text": "negócio",
            "BeginOffset": 349,
            "EndOffset": 356
        },
        {
            "Score": 0.9984216690063477,
            "Text": "quais",
            "BeginOffset": 381,
            "EndOffset": 386
        },
        {
            "Score": 0.9916156530380249,
            "Text": "as intenções do seu comprador",
            "BeginOffset": 391,
            "EndOffset": 420
        },
        {
            "Score": 0.8402135968208313,
            "Text": "pós-venda da empresa",
            "BeginOffset": 422,
            "EndOffset": 442
        },
        {
            "Score": 0.9998794794082642,
            "Text": "parte",
            "BeginOffset": 450,
            "EndOffset": 455
        },
        {
            "Score": 0.9997641444206238,
            "Text": "você",
            "BeginOffset": 457,
            "EndOffset": 461
        },
        {
            "Score": 0.9598071575164795,
            "Text": "as reais necessidades e",
            "BeginOffset": 489,
            "EndOffset": 512
        },
        {
            "Score": 0.844993531703949,
            "Text": "objetivos do comprador",
            "BeginOffset": 513,
            "EndOffset": 535
        },
        {
            "Score": 0.9578990936279297,
            "Text": "expectativas",
            "BeginOffset": 573,
            "EndOffset": 585
        },
        {
            "Score": 0.9998537302017212,
            "Text": "sequência",
            "BeginOffset": 590,
            "EndOffset": 599
        },
        {
            "Score": 0.996788501739502,
            "Text": "a solução para a demanda do comprador",
            "BeginOffset": 611,
            "EndOffset": 648
        },
        {
            "Score": 0.9951924085617065,
            "Text": "que",
            "BeginOffset": 650,
            "EndOffset": 653
        },
        {
            "Score": 0.8715702891349792,
            "Text": "caso",
            "BeginOffset": 660,
            "EndOffset": 664
        },
        {
            "Score": 0.9886749386787415,
            "Text": "a sua empresa",
            "BeginOffset": 668,
            "EndOffset": 681
        },
        {
            "Score": 0.9958885908126831,
            "Text": "O objetivo",
            "BeginOffset": 683,
            "EndOffset": 693
        },
        {
            "Score": 0.9986131191253662,
            "Text": "a sua empresa",
            "BeginOffset": 709,
            "EndOffset": 722
        },
        {
            "Score": 0.9844070076942444,
            "Text": "um investimento",
            "BeginOffset": 725,
            "EndOffset": 740
        },
        {
            "Score": 0.9998953342437744,
            "Text": "ela",
            "BeginOffset": 748,
            "EndOffset": 751
        },
        {
            "Score": 0.9992281198501587,
            "Text": "as demandas do seu comprador",
            "BeginOffset": 759,
            "EndOffset": 787
        },
        {
            "Score": 0.9992629289627075,
            "Text": "os aspectos internos",
            "BeginOffset": 800,
            "EndOffset": 820
        },
        {
            "Score": 0.9983578324317932,
            "Text": "as finanças",
            "BeginOffset": 822,
            "EndOffset": 833
        },
        {
            "Score": 0.9912922978401184,
            "Text": "histórico",
            "BeginOffset": 835,
            "EndOffset": 844
        },
        {
            "Score": 0.9914379715919495,
            "Text": "funcionários",
            "BeginOffset": 846,
            "EndOffset": 858
        },
        {
            "Score": 0.9963358044624329,
            "Text": "detalhes do seu negócio",
            "BeginOffset": 861,
            "EndOffset": 884
        },
        {
            "Score": 0.9978300929069519,
            "Text": "aspectos externos da empresa",
            "BeginOffset": 900,
            "EndOffset": 928
        },
        {
            "Score": 0.9911271333694458,
            "Text": "a imagem da empresa no mercado",
            "BeginOffset": 930,
            "EndOffset": 960
        },
        {
            "Score": 0.9367294311523438,
            "Text": "concorrentes",
            "BeginOffset": 968,
            "EndOffset": 980
        },
        {
            "Score": 0.9975748658180237,
            "Text": "Tudo isso",
            "BeginOffset": 982,
            "EndOffset": 991
        },
        {
            "Score": 0.9698891639709473,
            "Text": "fim",
            "BeginOffset": 995,
            "EndOffset": 998
        },
        {
            "Score": 0.8935773968696594,
            "Text": "comprador",
            "BeginOffset": 1013,
            "EndOffset": 1022
        },
        {
            "Score": 0.7794428467750549,
            "Text": "par das informações",
            "BeginOffset": 1025,
            "EndOffset": 1044
        },
        {
            "Score": 0.9951342344284058,
            "Text": "o que",
            "BeginOffset": 1046,
            "EndOffset": 1051
        },
        {
            "Score": 0.9968703985214233,
            "Text": "as chances de sucesso na venda",
            "BeginOffset": 1060,
            "EndOffset": 1090
        },
        {
            "Score": 0.9995027780532837,
            "Text": "o seu negócio",
            "BeginOffset": 1117,
            "EndOffset": 1130
        },
        {
            "Score": 0.997221827507019,
            "Text": "você",
            "BeginOffset": 1143,
            "EndOffset": 1147
        },
        {
            "Score": 0.9310694336891174,
            "Text": "sócios",
            "BeginOffset": 1155,
            "EndOffset": 1161
        },
        {
            "Score": 0.9554608464241028,
            "Text": "vida profissional",
            "BeginOffset": 1179,
            "EndOffset": 1196
        },
        {
            "Score": 0.9996881484985352,
            "Text": "idoneidade",
            "BeginOffset": 1199,
            "EndOffset": 1209
        },
        {
            "Score": 0.9996901750564575,
            "Text": "você",
            "BeginOffset": 1217,
            "EndOffset": 1221
        },
        {
            "Score": 0.7448092699050903,
            "Text": "se",
            "BeginOffset": 1222,
            "EndOffset": 1224
        },
        {
            "Score": 0.9996207356452942,
            "Text": "esse possível comprador",
            "BeginOffset": 1249,
            "EndOffset": 1272
        },
        {
            "Score": 0.999832272529602,
            "Text": "dúvidas",
            "BeginOffset": 1302,
            "EndOffset": 1309
        },
        {
            "Score": 0.9995576739311218,
            "Text": "qualquer pergunta",
            "BeginOffset": 1322,
            "EndOffset": 1339
        },
        {
            "Score": 0.9986332058906555,
            "Text": "que",
            "BeginOffset": 1340,
            "EndOffset": 1343
        },
        {
            "Score": 0.9990389347076416,
            "Text": "fim",
            "BeginOffset": 1362,
            "EndOffset": 1365
        },
        {
            "Score": 0.9972601532936096,
            "Text": "o valor do seu negócio",
            "BeginOffset": 1378,
            "EndOffset": 1400
        },
        {
            "Score": 0.9989347457885742,
            "Text": "a tratativa",
            "BeginOffset": 1407,
            "EndOffset": 1418
        },
        {
            "Score": 0.9992145299911499,
            "Text": "o",
            "BeginOffset": 1421,
            "EndOffset": 1422
        },
        {
            "Score": 0.998320996761322,
            "Text": "uma visita à empresa",
            "BeginOffset": 1436,
            "EndOffset": 1456
        },
        {
            "Score": 0.9836684465408325,
            "Text": "quais as impressões",
            "BeginOffset": 1474,
            "EndOffset": 1493
        },
        {
            "Score": 0.6742411255836487,
            "Text": "que",
            "BeginOffset": 1494,
            "EndOffset": 1497
        },
        {
            "Score": 0.9908533096313477,
            "Text": "o possível comprador",
            "BeginOffset": 1498,
            "EndOffset": 1518
        },
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
    - Não há necessidade de fazer controle do tipo de id (ele pode ser qualquer string/interger) e não há necessidade de haver persistencia nos dados, ou seja, a partir do momento que o programa finaliza ele nâo precisa permanecer com as informações salvas.
