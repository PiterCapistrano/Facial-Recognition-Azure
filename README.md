# Facial-Recognition-Azure

Reconhecimento Facial e transformação de imagens em Dados no Azure Machine Learning, AI Vision Service.

## Criando Recurso para a Utilização dos Serviços no Portal Vision Studio

1º Na página (https://portal.azure.com/), na parte a esquerda da página clicar em " + Create a resource", em categories, clicar em " AI + Machine Learning" e depois em "create" no "Azure AI Services".

2º Agora iremos criar uma ponte dos serviços de inteligência artificial na nossa assinatura para o Vision Studio. Nessa tela preencher da seguinte forma convorme o material de apoio da página (https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/04-face.html) e conforme a baixo:

Assinatura: Sua assinatura do Azure.
Grupo de recursos: Selecione ou crie um grupo de recursos com um nome exclusivo.
Região: Leste dos EUA (Para utilizar os serviços com um preço mais barato).
Nome: Digite um nome exclusivo.
Nível de preços: Padrão S0.
Ao marcar esta caixa, reconheço que li e compreendi todos os termos abaixo: Selecionado.

Após o preenchimento dos campos, clicar em "Review + create", para assim finalizar o processo de criação do vinculo com o Vision Studio.

3º Após vincularmos a assinatura ao Vision Studio, iremos acessar o portal através do site (https://portal.vision.cognitive.azure.com/), ao acessar o portal confira se sua conta está logada na plataforma, clicar em "View all resources".

4º Na página de seleção de recursos, devemos selecionar o recurso que nós criamos e clicar em "Select as default resource". Aguarde de 5 a 10 minutos para a plataforma sincronizar o recurso, volte para a página anterior, observe se o recurso selecionado foi atualizado sem erros.

## Detalhamento do Processo de Análise Facial com Azure Machine Learning

1º Nessa página nós podemos observar que temos uma variedade de recursos, o recurso que nós iremos utilizar nessa atividade, se chama "Detect faces in an image", ele se encotra na aba "Face" da pagina inicial, clique nele para sermos direcionados para a página de trabalho do recurso.

2º Nessa página iremos ativar a opção "I acknowledge that this demo will incur usage to resouce ( o nome do seu recurso) in my Azure account.", agora selecione uma das imagens a baixo ou faça o update da imagem que voce desejar que contenha um rosto, para que ele possa analisar a imagem e lhe informar abaixo a confirmação de detecção de uma face na imagem selecionada, a quantidade de faces na imagem, se o rosto está coberto por alguma máscara ou algum outro objeto e o que a máscara ou o outro objeto está tapando:

Exemplo de detecção de atributos:

    Uma pessoa sem mascara:
    Face #1
    Face mask: no

    Duas pessoas sem mascaras:
    Face #1
    Face mask: no
    Face #2
    Face mask: no

    Uma pessoa com mascara:
    Face #1
    Face mask: yes
    Face mask covering nose and mouth: yes

3º Podemos também adquirir um arquivo JSON, com o código da imagem analisada, onde podemos utilizar em uma aplicação, ou em um banco de dados e etc...

4º Como exemplo prático eu utilizei uma imagem minha:

  <img src="/inputs/Piter Capistrano.jpg">

  Onde foram geradas as seguintes informações:

    Detecção de atributos:

    Face #1
    Face mask: no

    Código JSON gerado:

        [
    {
        "recognitionModel": "recognition_01",
        "faceRectangle": {
        "width": 258,
        "height": 308,
        "left": 136,
        "top": 74
        },
        "faceLandmarks": {
        "pupilLeft": {
            "x": 195.6,
            "y": 188.7
        },
        "pupilRight": {
            "x": 310.5,
            "y": 200.1
        },
        "noseTip": {
            "x": 224.8,
            "y": 216.6
        },
        "mouthLeft": {
            "x": 180.2,
            "y": 287.5
        },
        "mouthRight": {
            "x": 284.3,
            "y": 298.7
        },
        "eyebrowLeftOuter": {
            "x": 168.1,
            "y": 153.5
        },
        "eyebrowLeftInner": {
            "x": 222.2,
            "y": 147.9
        },
        "eyeLeftOuter": {
            "x": 178,
            "y": 189.8
        },
        "eyeLeftTop": {
            "x": 197.7,
            "y": 180.9
        },
        "eyeLeftBottom": {
            "x": 193,
            "y": 194.4
        },
        "eyeLeftInner": {
            "x": 213.7,
            "y": 189.8
        },
        "eyebrowRightInner": {
            "x": 282.9,
            "y": 153.6
        },
        "eyebrowRightOuter": {
            "x": 362.8,
            "y": 184.3
        },
        "eyeRightInner": {
            "x": 290.2,
            "y": 198.4
        },
        "eyeRightTop": {
            "x": 310.8,
            "y": 190.5
        },
        "eyeRightBottom": {
            "x": 309.3,
            "y": 205.7
        },
        "eyeRightOuter": {
            "x": 331.6,
            "y": 205.7
        },
        "noseRootLeft": {
            "x": 229.8,
            "y": 185.5
        },
        "noseRootRight": {
            "x": 261.4,
            "y": 186.2
        },
        "noseLeftAlarTop": {
            "x": 211.8,
            "y": 213.3
        },
        "noseRightAlarTop": {
            "x": 260.8,
            "y": 219.2
        },
        "noseLeftAlarOutTip": {
            "x": 197.2,
            "y": 233.1
        },
        "noseRightAlarOutTip": {
            "x": 269.1,
            "y": 243.4
        },
        "upperLipTop": {
            "x": 226.7,
            "y": 269.7
        },
        "upperLipBottom": {
            "x": 223.7,
            "y": 280.1
        },
        "underLipTop": {
            "x": 222.4,
            "y": 287.4
        },
        "underLipBottom": {
            "x": 220,
            "y": 301.1
        }
        },
        "faceAttributes": {
        "mask": {
            "type": "noMask",
            "noseAndMouthCovered": false
        }
        }
    }
    ]

## Detalhamento do Processo de Análise de Documentos

1º Na página inicial do Portal Vision Studio (https://portal.vision.cognitive.azure.com/), procurar na aba "Optical character recognition" a opção "Extract text from images" ao clicar nessa opção de serviço, seremos direcionados para a página do serviço (https://portal.vision.cognitive.azure.com/demo/extract-text-from-images).

2º Nessa página iremos selecionar a opção "I acknowledge that this demo will incur usage to resouce ( o nome do seu recurso) in my Azure account." e selecionar uma imagem abaixo, ou fazer o update de uma imagem do seu computador.

3º Após isso se iniciará o processo de análise da imagem. Quando o processo de análise finalizar, o sistema irá transcrever o que está no arquivo de texto ou imagem de texto no quadrado ao lado direito da imagem na aba "Detected atributes".

No teste que eu realizei eu utilizei a seguinte imagem de texto:

<img src="/inputs/documento escrito a mão.jpeg">


Segue abaixo o resultado da análise do texto da imagem:

<img src="/inputs/Resultado da análise da imagem.png">


4º Ele também gera um arquivo JSON, como demonstrado a baixo:

        [
        {
            "lines": [
            {
                "text": "esta voragem da tecnologia que cada vez",
                "boundingPolygon": [
                {
                    "x": 39,
                    "y": 8
                },
                {
                    "x": 618,
                    "y": 7
                },
                {
                    "x": 618,
                    "y": 53
                },
                {
                    "x": 39,
                    "y": 56
                }
                ],
                "words": [
                {
                    "text": "esta",
                    "boundingPolygon": [
                    {
                        "x": 40,
                        "y": 11
                    },
                    {
                        "x": 97,
                        "y": 10
                    },
                    {
                        "x": 96,
                        "y": 56
                    },
                    {
                        "x": 39,
                        "y": 57
                    }
                    ],
                    "confidence": 0.944
                },
                {
                    "text": "voragem",
                    "boundingPolygon": [
                    {
                        "x": 106,
                        "y": 9
                    },
                    {
                        "x": 225,
                        "y": 8
                    },
                    {
                        "x": 225,
                        "y": 54
                    },
                    {
                        "x": 105,
                        "y": 55
                    }
                    ],
                    "confidence": 0.609
                },
                {
                    "text": "da",
                    "boundingPolygon": [
                    {
                        "x": 241,
                        "y": 7
                    },
                    {
                        "x": 280,
                        "y": 7
                    },
                    {
                        "x": 279,
                        "y": 53
                    },
                    {
                        "x": 241,
                        "y": 53
                    }
                    ],
                    "confidence": 0.962
                },
                {
                    "text": "tecnologia",
                    "boundingPolygon": [
                    {
                        "x": 288,
                        "y": 7
                    },
                    {
                        "x": 421,
                        "y": 7
                    },
                    {
                        "x": 420,
                        "y": 52
                    },
                    {
                        "x": 288,
                        "y": 53
                    }
                    ],
                    "confidence": 0.58
                },
                {
                    "text": "que",
                    "boundingPolygon": [
                    {
                        "x": 430,
                        "y": 7
                    },
                    {
                        "x": 485,
                        "y": 8
                    },
                    {
                        "x": 485,
                        "y": 52
                    },
                    {
                        "x": 429,
                        "y": 52
                    }
                    ],
                    "confidence": 0.993
                },
                {
                    "text": "cada",
                    "boundingPolygon": [
                    {
                        "x": 494,
                        "y": 8
                    },
                    {
                        "x": 556,
                        "y": 9
                    },
                    {
                        "x": 556,
                        "y": 52
                    },
                    {
                        "x": 494,
                        "y": 52
                    }
                    ],
                    "confidence": 0.995
                },
                {
                    "text": "vez",
                    "boundingPolygon": [
                    {
                        "x": 565,
                        "y": 9
                    },
                    {
                        "x": 616,
                        "y": 11
                    },
                    {
                        "x": 616,
                        "y": 53
                    },
                    {
                        "x": 565,
                        "y": 52
                    }
                    ],
                    "confidence": 0.994
                }
                ]
            },
            {
                "text": "mais noscerca e abaja.",
                "boundingPolygon": [
                {
                    "x": 43,
                    "y": 66
                },
                {
                    "x": 398,
                    "y": 66
                },
                {
                    "x": 398,
                    "y": 98
                },
                {
                    "x": 43,
                    "y": 96
                }
                ],
                "words": [
                {
                    "text": "mais",
                    "boundingPolygon": [
                    {
                        "x": 44,
                        "y": 67
                    },
                    {
                        "x": 118,
                        "y": 66
                    },
                    {
                        "x": 118,
                        "y": 96
                    },
                    {
                        "x": 44,
                        "y": 95
                    }
                    ],
                    "confidence": 0.94
                },
                {
                    "text": "noscerca",
                    "boundingPolygon": [
                    {
                        "x": 137,
                        "y": 66
                    },
                    {
                        "x": 247,
                        "y": 66
                    },
                    {
                        "x": 247,
                        "y": 98
                    },
                    {
                        "x": 137,
                        "y": 97
                    }
                    ],
                    "confidence": 0.88
                },
                {
                    "text": "e",
                    "boundingPolygon": [
                    {
                        "x": 270,
                        "y": 66
                    },
                    {
                        "x": 287,
                        "y": 66
                    },
                    {
                        "x": 287,
                        "y": 98
                    },
                    {
                        "x": 270,
                        "y": 98
                    }
                    ],
                    "confidence": 0.995
                },
                {
                    "text": "abaja.",
                    "boundingPolygon": [
                    {
                        "x": 294,
                        "y": 66
                    },
                    {
                        "x": 398,
                        "y": 67
                    },
                    {
                        "x": 398,
                        "y": 99
                    },
                    {
                        "x": 294,
                        "y": 98
                    }
                    ],
                    "confidence": 0.595
                }
                ]
            },
            {
                "text": "Se a minha profissão que obriga a passar",
                "boundingPolygon": [
                {
                    "x": 42,
                    "y": 121
                },
                {
                    "x": 625,
                    "y": 122
                },
                {
                    "x": 625,
                    "y": 157
                },
                {
                    "x": 42,
                    "y": 156
                }
                ],
                "words": [
                {
                    "text": "Se",
                    "boundingPolygon": [
                    {
                        "x": 43,
                        "y": 121
                    },
                    {
                        "x": 73,
                        "y": 121
                    },
                    {
                        "x": 73,
                        "y": 155
                    },
                    {
                        "x": 43,
                        "y": 155
                    }
                    ],
                    "confidence": 0.995
                },
                {
                    "text": "a",
                    "boundingPolygon": [
                    {
                        "x": 79,
                        "y": 121
                    },
                    {
                        "x": 98,
                        "y": 121
                    },
                    {
                        "x": 98,
                        "y": 156
                    },
                    {
                        "x": 79,
                        "y": 155
                    }
                    ],
                    "confidence": 0.996
                },
                {
                    "text": "minha",
                    "boundingPolygon": [
                    {
                        "x": 111,
                        "y": 122
                    },
                    {
                        "x": 205,
                        "y": 122
                    },
                    {
                        "x": 205,
                        "y": 157
                    },
                    {
                        "x": 111,
                        "y": 156
                    }
                    ],
                    "confidence": 0.963
                },
                {
                    "text": "profissão",
                    "boundingPolygon": [
                    {
                        "x": 218,
                        "y": 122
                    },
                    {
                        "x": 348,
                        "y": 123
                    },
                    {
                        "x": 348,
                        "y": 157
                    },
                    {
                        "x": 218,
                        "y": 157
                    }
                    ],
                    "confidence": 0.955
                },
                {
                    "text": "que",
                    "boundingPolygon": [
                    {
                        "x": 369,
                        "y": 123
                    },
                    {
                        "x": 412,
                        "y": 123
                    },
                    {
                        "x": 412,
                        "y": 157
                    },
                    {
                        "x": 369,
                        "y": 157
                    }
                    ],
                    "confidence": 0.106
                },
                {
                    "text": "obriga",
                    "boundingPolygon": [
                    {
                        "x": 419,
                        "y": 123
                    },
                    {
                        "x": 496,
                        "y": 123
                    },
                    {
                        "x": 496,
                        "y": 157
                    },
                    {
                        "x": 419,
                        "y": 157
                    }
                    ],
                    "confidence": 0.684
                },
                {
                    "text": "a",
                    "boundingPolygon": [
                    {
                        "x": 517,
                        "y": 123
                    },
                    {
                        "x": 536,
                        "y": 123
                    },
                    {
                        "x": 536,
                        "y": 157
                    },
                    {
                        "x": 517,
                        "y": 157
                    }
                    ],
                    "confidence": 0.994
                },
                {
                    "text": "passar",
                    "boundingPolygon": [
                    {
                        "x": 548,
                        "y": 123
                    },
                    {
                        "x": 623,
                        "y": 123
                    },
                    {
                        "x": 623,
                        "y": 156
                    },
                    {
                        "x": 548,
                        "y": 157
                    }
                    ],
                    "confidence": 0.918
                }
                ]
            },
            {
                "text": "horas a escrever num computador, a falta",
                "boundingPolygon": [
                {
                    "x": 48,
                    "y": 181
                },
                {
                    "x": 628,
                    "y": 178
                },
                {
                    "x": 628,
                    "y": 226
                },
                {
                    "x": 48,
                    "y": 228
                }
                ],
                "words": [
                {
                    "text": "horas",
                    "boundingPolygon": [
                    {
                        "x": 50,
                        "y": 187
                    },
                    {
                        "x": 128,
                        "y": 186
                    },
                    {
                        "x": 127,
                        "y": 225
                    },
                    {
                        "x": 49,
                        "y": 223
                    }
                    ],
                    "confidence": 0.974
                },
                {
                    "text": "a",
                    "boundingPolygon": [
                    {
                        "x": 137,
                        "y": 186
                    },
                    {
                        "x": 161,
                        "y": 185
                    },
                    {
                        "x": 160,
                        "y": 226
                    },
                    {
                        "x": 136,
                        "y": 225
                    }
                    ],
                    "confidence": 0.992
                },
                {
                    "text": "escrever",
                    "boundingPolygon": [
                    {
                        "x": 171,
                        "y": 185
                    },
                    {
                        "x": 270,
                        "y": 184
                    },
                    {
                        "x": 270,
                        "y": 227
                    },
                    {
                        "x": 170,
                        "y": 226
                    }
                    ],
                    "confidence": 0.967
                },
                {
                    "text": "num",
                    "boundingPolygon": [
                    {
                        "x": 279,
                        "y": 184
                    },
                    {
                        "x": 343,
                        "y": 183
                    },
                    {
                        "x": 343,
                        "y": 228
                    },
                    {
                        "x": 279,
                        "y": 227
                    }
                    ],
                    "confidence": 0.918
                },
                {
                    "text": "computador,",
                    "boundingPolygon": [
                    {
                        "x": 353,
                        "y": 183
                    },
                    {
                        "x": 526,
                        "y": 180
                    },
                    {
                        "x": 527,
                        "y": 227
                    },
                    {
                        "x": 353,
                        "y": 228
                    }
                    ],
                    "confidence": 0.699
                },
                {
                    "text": "a",
                    "boundingPolygon": [
                    {
                        "x": 535,
                        "y": 180
                    },
                    {
                        "x": 555,
                        "y": 180
                    },
                    {
                        "x": 555,
                        "y": 227
                    },
                    {
                        "x": 535,
                        "y": 227
                    }
                    ],
                    "confidence": 0.994
                },
                {
                    "text": "falta",
                    "boundingPolygon": [
                    {
                        "x": 563,
                        "y": 180
                    },
                    {
                        "x": 625,
                        "y": 179
                    },
                    {
                        "x": 625,
                        "y": 226
                    },
                    {
                        "x": 564,
                        "y": 227
                    }
                    ],
                    "confidence": 0.632
                }
                ]
            },
            {
                "text": "de tempo leva a que eu \"escrevinhân os meus",
                "boundingPolygon": [
                {
                    "x": 46,
                    "y": 237
                },
                {
                    "x": 632,
                    "y": 238
                },
                {
                    "x": 631,
                    "y": 282
                },
                {
                    "x": 45,
                    "y": 281
                }
                ],
                "words": [
                {
                    "text": "de",
                    "boundingPolygon": [
                    {
                        "x": 48,
                        "y": 238
                    },
                    {
                        "x": 72,
                        "y": 238
                    },
                    {
                        "x": 72,
                        "y": 282
                    },
                    {
                        "x": 47,
                        "y": 282
                    }
                    ],
                    "confidence": 0.994
                },
                {
                    "text": "tempo",
                    "boundingPolygon": [
                    {
                        "x": 81,
                        "y": 238
                    },
                    {
                        "x": 174,
                        "y": 238
                    },
                    {
                        "x": 173,
                        "y": 283
                    },
                    {
                        "x": 80,
                        "y": 282
                    }
                    ],
                    "confidence": 0.889
                },
                {
                    "text": "leva",
                    "boundingPolygon": [
                    {
                        "x": 183,
                        "y": 238
                    },
                    {
                        "x": 244,
                        "y": 238
                    },
                    {
                        "x": 244,
                        "y": 283
                    },
                    {
                        "x": 183,
                        "y": 283
                    }
                    ],
                    "confidence": 0.918
                },
                {
                    "text": "a",
                    "boundingPolygon": [
                    {
                        "x": 254,
                        "y": 238
                    },
                    {
                        "x": 277,
                        "y": 239
                    },
                    {
                        "x": 276,
                        "y": 283
                    },
                    {
                        "x": 253,
                        "y": 283
                    }
                    ],
                    "confidence": 0.994
                },
                {
                    "text": "que",
                    "boundingPolygon": [
                    {
                        "x": 286,
                        "y": 239
                    },
                    {
                        "x": 332,
                        "y": 239
                    },
                    {
                        "x": 332,
                        "y": 282
                    },
                    {
                        "x": 286,
                        "y": 283
                    }
                    ],
                    "confidence": 0.996
                },
                {
                    "text": "eu",
                    "boundingPolygon": [
                    {
                        "x": 340,
                        "y": 239
                    },
                    {
                        "x": 370,
                        "y": 240
                    },
                    {
                        "x": 370,
                        "y": 282
                    },
                    {
                        "x": 340,
                        "y": 282
                    }
                    ],
                    "confidence": 0.67
                },
                {
                    "text": "\"escrevinhân",
                    "boundingPolygon": [
                    {
                        "x": 378,
                        "y": 240
                    },
                    {
                        "x": 533,
                        "y": 242
                    },
                    {
                        "x": 533,
                        "y": 280
                    },
                    {
                        "x": 378,
                        "y": 282
                    }
                    ],
                    "confidence": 0.075
                },
                {
                    "text": "os",
                    "boundingPolygon": [
                    {
                        "x": 541,
                        "y": 242
                    },
                    {
                        "x": 571,
                        "y": 243
                    },
                    {
                        "x": 570,
                        "y": 279
                    },
                    {
                        "x": 541,
                        "y": 280
                    }
                    ],
                    "confidence": 0.987
                },
                {
                    "text": "meus",
                    "boundingPolygon": [
                    {
                        "x": 579,
                        "y": 243
                    },
                    {
                        "x": 631,
                        "y": 244
                    },
                    {
                        "x": 631,
                        "y": 278
                    },
                    {
                        "x": 579,
                        "y": 279
                    }
                    ],
                    "confidence": 0.939
                }
                ]
            },
            {
                "text": "textos num portátil, e a minha maria da",
                "boundingPolygon": [
                {
                    "x": 48,
                    "y": 289
                },
                {
                    "x": 612,
                    "y": 289
                },
                {
                    "x": 612,
                    "y": 331
                },
                {
                    "x": 48,
                    "y": 331
                }
                ],
                "words": [
                {
                    "text": "textos",
                    "boundingPolygon": [
                    {
                        "x": 51,
                        "y": 290
                    },
                    {
                        "x": 122,
                        "y": 290
                    },
                    {
                        "x": 121,
                        "y": 330
                    },
                    {
                        "x": 49,
                        "y": 328
                    }
                    ],
                    "confidence": 0.951
                },
                {
                    "text": "num",
                    "boundingPolygon": [
                    {
                        "x": 130,
                        "y": 289
                    },
                    {
                        "x": 193,
                        "y": 290
                    },
                    {
                        "x": 192,
                        "y": 331
                    },
                    {
                        "x": 128,
                        "y": 330
                    }
                    ],
                    "confidence": 0.967
                },
                {
                    "text": "portátil,",
                    "boundingPolygon": [
                    {
                        "x": 207,
                        "y": 290
                    },
                    {
                        "x": 314,
                        "y": 290
                    },
                    {
                        "x": 313,
                        "y": 332
                    },
                    {
                        "x": 206,
                        "y": 331
                    }
                    ],
                    "confidence": 0.737
                },
                {
                    "text": "e",
                    "boundingPolygon": [
                    {
                        "x": 321,
                        "y": 290
                    },
                    {
                        "x": 339,
                        "y": 290
                    },
                    {
                        "x": 339,
                        "y": 332
                    },
                    {
                        "x": 321,
                        "y": 332
                    }
                    ],
                    "confidence": 0.993
                },
                {
                    "text": "a",
                    "boundingPolygon": [
                    {
                        "x": 347,
                        "y": 290
                    },
                    {
                        "x": 365,
                        "y": 290
                    },
                    {
                        "x": 365,
                        "y": 332
                    },
                    {
                        "x": 347,
                        "y": 332
                    }
                    ],
                    "confidence": 0.996
                },
                {
                    "text": "minha",
                    "boundingPolygon": [
                    {
                        "x": 373,
                        "y": 290
                    },
                    {
                        "x": 468,
                        "y": 291
                    },
                    {
                        "x": 468,
                        "y": 330
                    },
                    {
                        "x": 373,
                        "y": 332
                    }
                    ],
                    "confidence": 0.666
                },
                {
                    "text": "maria",
                    "boundingPolygon": [
                    {
                        "x": 477,
                        "y": 291
                    },
                    {
                        "x": 568,
                        "y": 292
                    },
                    {
                        "x": 568,
                        "y": 327
                    },
                    {
                        "x": 477,
                        "y": 330
                    }
                    ],
                    "confidence": 0.654
                },
                {
                    "text": "da",
                    "boundingPolygon": [
                    {
                        "x": 575,
                        "y": 292
                    },
                    {
                        "x": 610,
                        "y": 292
                    },
                    {
                        "x": 611,
                        "y": 326
                    },
                    {
                        "x": 576,
                        "y": 327
                    }
                    ],
                    "confidence": 0.697
                }
                ]
            },
            {
                "text": "отдализакой me face us vines аричастей",
                "boundingPolygon": [
                {
                    "x": 45,
                    "y": 345
                },
                {
                    "x": 623,
                    "y": 338
                },
                {
                    "x": 624,
                    "y": 380
                },
                {
                    "x": 46,
                    "y": 391
                }
                ],
                "words": [
                {
                    "text": "отдализакой",
                    "boundingPolygon": [
                    {
                        "x": 46,
                        "y": 347
                    },
                    {
                        "x": 199,
                        "y": 342
                    },
                    {
                        "x": 200,
                        "y": 388
                    },
                    {
                        "x": 47,
                        "y": 392
                    }
                    ],
                    "confidence": 0.193
                },
                {
                    "text": "me",
                    "boundingPolygon": [
                    {
                        "x": 208,
                        "y": 342
                    },
                    {
                        "x": 257,
                        "y": 341
                    },
                    {
                        "x": 257,
                        "y": 386
                    },
                    {
                        "x": 209,
                        "y": 388
                    }
                    ],
                    "confidence": 0.076
                },
                {
                    "text": "face",
                    "boundingPolygon": [
                    {
                        "x": 272,
                        "y": 341
                    },
                    {
                        "x": 326,
                        "y": 340
                    },
                    {
                        "x": 327,
                        "y": 384
                    },
                    {
                        "x": 273,
                        "y": 386
                    }
                    ],
                    "confidence": 0.586
                },
                {
                    "text": "us",
                    "boundingPolygon": [
                    {
                        "x": 335,
                        "y": 340
                    },
                    {
                        "x": 378,
                        "y": 339
                    },
                    {
                        "x": 378,
                        "y": 383
                    },
                    {
                        "x": 336,
                        "y": 384
                    }
                    ],
                    "confidence": 0.529
                },
                {
                    "text": "vines",
                    "boundingPolygon": [
                    {
                        "x": 410,
                        "y": 339
                    },
                    {
                        "x": 488,
                        "y": 338
                    },
                    {
                        "x": 488,
                        "y": 381
                    },
                    {
                        "x": 411,
                        "y": 382
                    }
                    ],
                    "confidence": 0.093
                },
                {
                    "text": "аричастей",
                    "boundingPolygon": [
                    {
                        "x": 496,
                        "y": 338
                    },
                    {
                        "x": 622,
                        "y": 338
                    },
                    {
                        "x": 622,
                        "y": 378
                    },
                    {
                        "x": 497,
                        "y": 381
                    }
                    ],
                    "confidence": 0.158
                }
                ]
            },
            {
                "text": "para arrotar despesas on fazer listas, permanece",
                "boundingPolygon": [
                {
                    "x": 48,
                    "y": 399
                },
                {
                    "x": 648,
                    "y": 389
                },
                {
                    "x": 649,
                    "y": 432
                },
                {
                    "x": 49,
                    "y": 444
                }
                ],
                "words": [
                {
                    "text": "para",
                    "boundingPolygon": [
                    {
                        "x": 48,
                        "y": 400
                    },
                    {
                        "x": 110,
                        "y": 399
                    },
                    {
                        "x": 111,
                        "y": 443
                    },
                    {
                        "x": 50,
                        "y": 445
                    }
                    ],
                    "confidence": 0.989
                },
                {
                    "text": "arrotar",
                    "boundingPolygon": [
                    {
                        "x": 119,
                        "y": 398
                    },
                    {
                        "x": 208,
                        "y": 396
                    },
                    {
                        "x": 209,
                        "y": 441
                    },
                    {
                        "x": 120,
                        "y": 443
                    }
                    ],
                    "confidence": 0.734
                },
                {
                    "text": "despesas",
                    "boundingPolygon": [
                    {
                        "x": 216,
                        "y": 396
                    },
                    {
                        "x": 328,
                        "y": 394
                    },
                    {
                        "x": 330,
                        "y": 438
                    },
                    {
                        "x": 218,
                        "y": 440
                    }
                    ],
                    "confidence": 0.965
                },
                {
                    "text": "on",
                    "boundingPolygon": [
                    {
                        "x": 337,
                        "y": 394
                    },
                    {
                        "x": 379,
                        "y": 393
                    },
                    {
                        "x": 380,
                        "y": 437
                    },
                    {
                        "x": 338,
                        "y": 438
                    }
                    ],
                    "confidence": 0.805
                },
                {
                    "text": "fazer",
                    "boundingPolygon": [
                    {
                        "x": 389,
                        "y": 393
                    },
                    {
                        "x": 449,
                        "y": 392
                    },
                    {
                        "x": 450,
                        "y": 435
                    },
                    {
                        "x": 390,
                        "y": 436
                    }
                    ],
                    "confidence": 0.965
                },
                {
                    "text": "listas,",
                    "boundingPolygon": [
                    {
                        "x": 458,
                        "y": 392
                    },
                    {
                        "x": 524,
                        "y": 391
                    },
                    {
                        "x": 525,
                        "y": 434
                    },
                    {
                        "x": 459,
                        "y": 435
                    }
                    ],
                    "confidence": 0.96
                },
                {
                    "text": "permanece",
                    "boundingPolygon": [
                    {
                        "x": 533,
                        "y": 391
                    },
                    {
                        "x": 646,
                        "y": 389
                    },
                    {
                        "x": 647,
                        "y": 432
                    },
                    {
                        "x": 534,
                        "y": 434
                    }
                    ],
                    "confidence": 0.565
                }
                ]
            },
            {
                "text": "o meu gosto por ver - num caderno, numa agen-",
                "boundingPolygon": [
                {
                    "x": 55,
                    "y": 459
                },
                {
                    "x": 646,
                    "y": 457
                },
                {
                    "x": 646,
                    "y": 491
                },
                {
                    "x": 55,
                    "y": 495
                }
                ],
                "words": [
                {
                    "text": "o",
                    "boundingPolygon": [
                    {
                        "x": 57,
                        "y": 461
                    },
                    {
                        "x": 72,
                        "y": 461
                    },
                    {
                        "x": 72,
                        "y": 496
                    },
                    {
                        "x": 56,
                        "y": 496
                    }
                    ],
                    "confidence": 0.966
                },
                {
                    "text": "meu",
                    "boundingPolygon": [
                    {
                        "x": 80,
                        "y": 461
                    },
                    {
                        "x": 130,
                        "y": 460
                    },
                    {
                        "x": 130,
                        "y": 495
                    },
                    {
                        "x": 79,
                        "y": 496
                    }
                    ],
                    "confidence": 0.666
                },
                {
                    "text": "gosto",
                    "boundingPolygon": [
                    {
                        "x": 143,
                        "y": 459
                    },
                    {
                        "x": 202,
                        "y": 459
                    },
                    {
                        "x": 201,
                        "y": 494
                    },
                    {
                        "x": 142,
                        "y": 495
                    }
                    ],
                    "confidence": 0.969
                },
                {
                    "text": "por",
                    "boundingPolygon": [
                    {
                        "x": 210,
                        "y": 459
                    },
                    {
                        "x": 248,
                        "y": 458
                    },
                    {
                        "x": 247,
                        "y": 494
                    },
                    {
                        "x": 209,
                        "y": 494
                    }
                    ],
                    "confidence": 0.994
                },
                {
                    "text": "ver",
                    "boundingPolygon": [
                    {
                        "x": 255,
                        "y": 458
                    },
                    {
                        "x": 296,
                        "y": 458
                    },
                    {
                        "x": 296,
                        "y": 493
                    },
                    {
                        "x": 254,
                        "y": 494
                    }
                    ],
                    "confidence": 0.83
                },
                {
                    "text": "-",
                    "boundingPolygon": [
                    {
                        "x": 313,
                        "y": 458
                    },
                    {
                        "x": 332,
                        "y": 458
                    },
                    {
                        "x": 331,
                        "y": 493
                    },
                    {
                        "x": 312,
                        "y": 493
                    }
                    ],
                    "confidence": 0.963
                },
                {
                    "text": "num",
                    "boundingPolygon": [
                    {
                        "x": 340,
                        "y": 457
                    },
                    {
                        "x": 395,
                        "y": 457
                    },
                    {
                        "x": 394,
                        "y": 492
                    },
                    {
                        "x": 339,
                        "y": 493
                    }
                    ],
                    "confidence": 0.762
                },
                {
                    "text": "caderno,",
                    "boundingPolygon": [
                    {
                        "x": 407,
                        "y": 457
                    },
                    {
                        "x": 503,
                        "y": 458
                    },
                    {
                        "x": 503,
                        "y": 491
                    },
                    {
                        "x": 406,
                        "y": 492
                    }
                    ],
                    "confidence": 0.785
                },
                {
                    "text": "numa",
                    "boundingPolygon": [
                    {
                        "x": 510,
                        "y": 458
                    },
                    {
                        "x": 579,
                        "y": 458
                    },
                    {
                        "x": 579,
                        "y": 490
                    },
                    {
                        "x": 509,
                        "y": 491
                    }
                    ],
                    "confidence": 0.198
                },
                {
                    "text": "agen-",
                    "boundingPolygon": [
                    {
                        "x": 586,
                        "y": 458
                    },
                    {
                        "x": 643,
                        "y": 459
                    },
                    {
                        "x": 643,
                        "y": 490
                    },
                    {
                        "x": 585,
                        "y": 490
                    }
                    ],
                    "confidence": 0.85
                }
                ]
            },
            {
                "text": "da, num livrinho de apontamentos, num",
                "boundingPolygon": [
                {
                    "x": 57,
                    "y": 508
                },
                {
                    "x": 604,
                    "y": 505
                },
                {
                    "x": 604,
                    "y": 542
                },
                {
                    "x": 57,
                    "y": 547
                }
                ],
                "words": [
                {
                    "text": "da,",
                    "boundingPolygon": [
                    {
                        "x": 59,
                        "y": 512
                    },
                    {
                        "x": 110,
                        "y": 510
                    },
                    {
                        "x": 110,
                        "y": 546
                    },
                    {
                        "x": 59,
                        "y": 547
                    }
                    ],
                    "confidence": 0.963
                },
                {
                    "text": "num",
                    "boundingPolygon": [
                    {
                        "x": 117,
                        "y": 510
                    },
                    {
                        "x": 176,
                        "y": 509
                    },
                    {
                        "x": 177,
                        "y": 545
                    },
                    {
                        "x": 117,
                        "y": 546
                    }
                    ],
                    "confidence": 0.892
                },
                {
                    "text": "livrinho",
                    "boundingPolygon": [
                    {
                        "x": 190,
                        "y": 508
                    },
                    {
                        "x": 294,
                        "y": 507
                    },
                    {
                        "x": 294,
                        "y": 544
                    },
                    {
                        "x": 190,
                        "y": 545
                    }
                    ],
                    "confidence": 0.803
                },
                {
                    "text": "de",
                    "boundingPolygon": [
                    {
                        "x": 301,
                        "y": 507
                    },
                    {
                        "x": 338,
                        "y": 506
                    },
                    {
                        "x": 338,
                        "y": 544
                    },
                    {
                        "x": 301,
                        "y": 544
                    }
                    ],
                    "confidence": 0.997
                },
                {
                    "text": "apontamentos,",
                    "boundingPolygon": [
                    {
                        "x": 345,
                        "y": 506
                    },
                    {
                        "x": 522,
                        "y": 506
                    },
                    {
                        "x": 522,
                        "y": 543
                    },
                    {
                        "x": 345,
                        "y": 544
                    }
                    ],
                    "confidence": 0.761
                },
                {
                    "text": "num",
                    "boundingPolygon": [
                    {
                        "x": 529,
                        "y": 506
                    },
                    {
                        "x": 594,
                        "y": 506
                    },
                    {
                        "x": 593,
                        "y": 543
                    },
                    {
                        "x": 529,
                        "y": 543
                    }
                    ],
                    "confidence": 0.656
                }
                ]
            },
            {
                "text": "post-it - palavras desenhadas à mão, en-",
                "boundingPolygon": [
                {
                    "x": 63,
                    "y": 556
                },
                {
                    "x": 639,
                    "y": 555
                },
                {
                    "x": 639,
                    "y": 590
                },
                {
                    "x": 63,
                    "y": 594
                }
                ],
                "words": [
                {
                    "text": "post-it",
                    "boundingPolygon": [
                    {
                        "x": 64,
                        "y": 556
                    },
                    {
                        "x": 156,
                        "y": 556
                    },
                    {
                        "x": 156,
                        "y": 594
                    },
                    {
                        "x": 64,
                        "y": 595
                    }
                    ],
                    "confidence": 0.932
                },
                {
                    "text": "-",
                    "boundingPolygon": [
                    {
                        "x": 164,
                        "y": 556
                    },
                    {
                        "x": 185,
                        "y": 556
                    },
                    {
                        "x": 184,
                        "y": 594
                    },
                    {
                        "x": 164,
                        "y": 594
                    }
                    ],
                    "confidence": 0.962
                },
                {
                    "text": "palavras",
                    "boundingPolygon": [
                    {
                        "x": 202,
                        "y": 556
                    },
                    {
                        "x": 314,
                        "y": 556
                    },
                    {
                        "x": 313,
                        "y": 593
                    },
                    {
                        "x": 202,
                        "y": 594
                    }
                    ],
                    "confidence": 0.725
                },
                {
                    "text": "desenhadas",
                    "boundingPolygon": [
                    {
                        "x": 321,
                        "y": 556
                    },
                    {
                        "x": 470,
                        "y": 556
                    },
                    {
                        "x": 469,
                        "y": 591
                    },
                    {
                        "x": 320,
                        "y": 593
                    }
                    ],
                    "confidence": 0.948
                },
                {
                    "text": "à",
                    "boundingPolygon": [
                    {
                        "x": 477,
                        "y": 556
                    },
                    {
                        "x": 497,
                        "y": 556
                    },
                    {
                        "x": 497,
                        "y": 590
                    },
                    {
                        "x": 476,
                        "y": 591
                    }
                    ],
                    "confidence": 0.928
                },
                {
                    "text": "mão,",
                    "boundingPolygon": [
                    {
                        "x": 510,
                        "y": 556
                    },
                    {
                        "x": 583,
                        "y": 556
                    },
                    {
                        "x": 583,
                        "y": 589
                    },
                    {
                        "x": 510,
                        "y": 590
                    }
                    ],
                    "confidence": 0.697
                },
                {
                    "text": "en-",
                    "boundingPolygon": [
                    {
                        "x": 590,
                        "y": 556
                    },
                    {
                        "x": 637,
                        "y": 556
                    },
                    {
                        "x": 636,
                        "y": 588
                    },
                    {
                        "x": 590,
                        "y": 589
                    }
                    ],
                    "confidence": 0.973
                }
                ]
            },
            {
                "text": "fileiradas umas ao lado das outras, às vezes",
                "boundingPolygon": [
                {
                    "x": 47,
                    "y": 605
                },
                {
                    "x": 635,
                    "y": 604
                },
                {
                    "x": 636,
                    "y": 648
                },
                {
                    "x": 47,
                    "y": 650
                }
                ],
                "words": [
                {
                    "text": "fileiradas",
                    "boundingPolygon": [
                    {
                        "x": 55,
                        "y": 606
                    },
                    {
                        "x": 183,
                        "y": 605
                    },
                    {
                        "x": 183,
                        "y": 650
                    },
                    {
                        "x": 55,
                        "y": 651
                    }
                    ],
                    "confidence": 0.884
                },
                {
                    "text": "umas",
                    "boundingPolygon": [
                    {
                        "x": 191,
                        "y": 605
                    },
                    {
                        "x": 268,
                        "y": 605
                    },
                    {
                        "x": 268,
                        "y": 649
                    },
                    {
                        "x": 191,
                        "y": 650
                    }
                    ],
                    "confidence": 0.969
                },
                {
                    "text": "ao",
                    "boundingPolygon": [
                    {
                        "x": 277,
                        "y": 605
                    },
                    {
                        "x": 308,
                        "y": 605
                    },
                    {
                        "x": 308,
                        "y": 649
                    },
                    {
                        "x": 277,
                        "y": 649
                    }
                    ],
                    "confidence": 0.996
                },
                {
                    "text": "lado",
                    "boundingPolygon": [
                    {
                        "x": 317,
                        "y": 605
                    },
                    {
                        "x": 383,
                        "y": 605
                    },
                    {
                        "x": 382,
                        "y": 648
                    },
                    {
                        "x": 317,
                        "y": 649
                    }
                    ],
                    "confidence": 0.967
                },
                {
                    "text": "das",
                    "boundingPolygon": [
                    {
                        "x": 391,
                        "y": 605
                    },
                    {
                        "x": 440,
                        "y": 605
                    },
                    {
                        "x": 439,
                        "y": 648
                    },
                    {
                        "x": 391,
                        "y": 648
                    }
                    ],
                    "confidence": 0.992
                },
                {
                    "text": "outras,",
                    "boundingPolygon": [
                    {
                        "x": 448,
                        "y": 605
                    },
                    {
                        "x": 537,
                        "y": 605
                    },
                    {
                        "x": 536,
                        "y": 648
                    },
                    {
                        "x": 448,
                        "y": 648
                    }
                    ],
                    "confidence": 0.835
                },
                {
                    "text": "às",
                    "boundingPolygon": [
                    {
                        "x": 545,
                        "y": 605
                    },
                    {
                        "x": 576,
                        "y": 606
                    },
                    {
                        "x": 576,
                        "y": 648
                    },
                    {
                        "x": 544,
                        "y": 648
                    }
                    ],
                    "confidence": 0.795
                },
                {
                    "text": "vezes",
                    "boundingPolygon": [
                    {
                        "x": 585,
                        "y": 606
                    },
                    {
                        "x": 635,
                        "y": 606
                    },
                    {
                        "x": 634,
                        "y": 648
                    },
                    {
                        "x": 584,
                        "y": 648
                    }
                    ],
                    "confidence": 0.977
                }
                ]
            },
            {
                "text": "meio desalinhadas (porquenão?) , outras",
                "boundingPolygon": [
                {
                    "x": 59,
                    "y": 659
                },
                {
                    "x": 600,
                    "y": 656
                },
                {
                    "x": 600,
                    "y": 701
                },
                {
                    "x": 59,
                    "y": 704
                }
                ],
                "words": [
                {
                    "text": "meio",
                    "boundingPolygon": [
                    {
                        "x": 60,
                        "y": 667
                    },
                    {
                        "x": 119,
                        "y": 664
                    },
                    {
                        "x": 119,
                        "y": 700
                    },
                    {
                        "x": 60,
                        "y": 699
                    }
                    ],
                    "confidence": 0.843
                },
                {
                    "text": "desalinhadas",
                    "boundingPolygon": [
                    {
                        "x": 127,
                        "y": 664
                    },
                    {
                        "x": 296,
                        "y": 659
                    },
                    {
                        "x": 296,
                        "y": 704
                    },
                    {
                        "x": 127,
                        "y": 701
                    }
                    ],
                    "confidence": 0.977
                },
                {
                    "text": "(porquenão?)",
                    "boundingPolygon": [
                    {
                        "x": 304,
                        "y": 659
                    },
                    {
                        "x": 489,
                        "y": 657
                    },
                    {
                        "x": 489,
                        "y": 703
                    },
                    {
                        "x": 304,
                        "y": 704
                    }
                    ],
                    "confidence": 0.771
                },
                {
                    "text": ",",
                    "boundingPolygon": [
                    {
                        "x": 498,
                        "y": 657
                    },
                    {
                        "x": 503,
                        "y": 657
                    },
                    {
                        "x": 502,
                        "y": 702
                    },
                    {
                        "x": 497,
                        "y": 702
                    }
                    ],
                    "confidence": 0.891
                },
                {
                    "text": "outras",
                    "boundingPolygon": [
                    {
                        "x": 509,
                        "y": 657
                    },
                    {
                        "x": 596,
                        "y": 657
                    },
                    {
                        "x": 595,
                        "y": 700
                    },
                    {
                        "x": 508,
                        "y": 702
                    }
                    ],
                    "confidence": 0.918
                }
                ]
            },
            {
                "text": "vezes só rabiscadas, e escritas normalmente",
                "boundingPolygon": [
                {
                    "x": 62,
                    "y": 708
                },
                {
                    "x": 636,
                    "y": 699
                },
                {
                    "x": 637,
                    "y": 741
                },
                {
                    "x": 62,
                    "y": 753
                }
                ],
                "words": [
                {
                    "text": "vezes",
                    "boundingPolygon": [
                    {
                        "x": 62,
                        "y": 708
                    },
                    {
                        "x": 120,
                        "y": 708
                    },
                    {
                        "x": 121,
                        "y": 753
                    },
                    {
                        "x": 62,
                        "y": 753
                    }
                    ],
                    "confidence": 0.945
                },
                {
                    "text": "só",
                    "boundingPolygon": [
                    {
                        "x": 129,
                        "y": 708
                    },
                    {
                        "x": 162,
                        "y": 708
                    },
                    {
                        "x": 163,
                        "y": 752
                    },
                    {
                        "x": 129,
                        "y": 753
                    }
                    ],
                    "confidence": 0.243
                },
                {
                    "text": "rabiscadas,",
                    "boundingPolygon": [
                    {
                        "x": 172,
                        "y": 708
                    },
                    {
                        "x": 310,
                        "y": 707
                    },
                    {
                        "x": 310,
                        "y": 749
                    },
                    {
                        "x": 172,
                        "y": 752
                    }
                    ],
                    "confidence": 0.888
                },
                {
                    "text": "e",
                    "boundingPolygon": [
                    {
                        "x": 318,
                        "y": 707
                    },
                    {
                        "x": 341,
                        "y": 707
                    },
                    {
                        "x": 342,
                        "y": 748
                    },
                    {
                        "x": 319,
                        "y": 749
                    }
                    ],
                    "confidence": 0.725
                },
                {
                    "text": "escritas",
                    "boundingPolygon": [
                    {
                        "x": 351,
                        "y": 707
                    },
                    {
                        "x": 451,
                        "y": 705
                    },
                    {
                        "x": 452,
                        "y": 745
                    },
                    {
                        "x": 351,
                        "y": 748
                    }
                    ],
                    "confidence": 0.89
                },
                {
                    "text": "normalmente",
                    "boundingPolygon": [
                    {
                        "x": 459,
                        "y": 705
                    },
                    {
                        "x": 634,
                        "y": 700
                    },
                    {
                        "x": 635,
                        "y": 738
                    },
                    {
                        "x": 460,
                        "y": 744
                    }
                    ],
                    "confidence": 0.675
                }
                ]
            },
            {
                "text": "em tinta preta (não gosto de usar ou-",
                "boundingPolygon": [
                {
                    "x": 63,
                    "y": 758
                },
                {
                    "x": 633,
                    "y": 759
                },
                {
                    "x": 633,
                    "y": 805
                },
                {
                    "x": 63,
                    "y": 804
                }
                ],
                "words": [
                {
                    "text": "em",
                    "boundingPolygon": [
                    {
                        "x": 65,
                        "y": 761
                    },
                    {
                        "x": 113,
                        "y": 761
                    },
                    {
                        "x": 112,
                        "y": 801
                    },
                    {
                        "x": 64,
                        "y": 799
                    }
                    ],
                    "confidence": 0.952
                },
                {
                    "text": "tinta",
                    "boundingPolygon": [
                    {
                        "x": 129,
                        "y": 760
                    },
                    {
                        "x": 210,
                        "y": 759
                    },
                    {
                        "x": 210,
                        "y": 803
                    },
                    {
                        "x": 128,
                        "y": 801
                    }
                    ],
                    "confidence": 0.963
                },
                {
                    "text": "preta",
                    "boundingPolygon": [
                    {
                        "x": 226,
                        "y": 759
                    },
                    {
                        "x": 298,
                        "y": 759
                    },
                    {
                        "x": 297,
                        "y": 805
                    },
                    {
                        "x": 226,
                        "y": 804
                    }
                    ],
                    "confidence": 0.895
                },
                {
                    "text": "(não",
                    "boundingPolygon": [
                    {
                        "x": 306,
                        "y": 759
                    },
                    {
                        "x": 378,
                        "y": 759
                    },
                    {
                        "x": 377,
                        "y": 805
                    },
                    {
                        "x": 306,
                        "y": 805
                    }
                    ],
                    "confidence": 0.94
                },
                {
                    "text": "gosto",
                    "boundingPolygon": [
                    {
                        "x": 386,
                        "y": 759
                    },
                    {
                        "x": 452,
                        "y": 759
                    },
                    {
                        "x": 452,
                        "y": 805
                    },
                    {
                        "x": 386,
                        "y": 805
                    }
                    ],
                    "confidence": 0.944
                },
                {
                    "text": "de",
                    "boundingPolygon": [
                    {
                        "x": 461,
                        "y": 759
                    },
                    {
                        "x": 502,
                        "y": 759
                    },
                    {
                        "x": 502,
                        "y": 805
                    },
                    {
                        "x": 461,
                        "y": 805
                    }
                    ],
                    "confidence": 0.994
                },
                {
                    "text": "usar",
                    "boundingPolygon": [
                    {
                        "x": 512,
                        "y": 759
                    },
                    {
                        "x": 582,
                        "y": 760
                    },
                    {
                        "x": 582,
                        "y": 803
                    },
                    {
                        "x": 512,
                        "y": 805
                    }
                    ],
                    "confidence": 0.976
                },
                {
                    "text": "ou-",
                    "boundingPolygon": [
                    {
                        "x": 592,
                        "y": 760
                    },
                    {
                        "x": 631,
                        "y": 760
                    },
                    {
                        "x": 631,
                        "y": 802
                    },
                    {
                        "x": 592,
                        "y": 803
                    }
                    ],
                    "confidence": 0.953
                }
                ]
            },
            {
                "text": "+ раз сооб, ё шик манта, en sei).",
                "boundingPolygon": [
                {
                    "x": 66,
                    "y": 811
                },
                {
                    "x": 527,
                    "y": 811
                },
                {
                    "x": 527,
                    "y": 847
                },
                {
                    "x": 66,
                    "y": 847
                }
                ],
                "words": [
                {
                    "text": "+",
                    "boundingPolygon": [
                    {
                        "x": 66,
                        "y": 812
                    },
                    {
                        "x": 74,
                        "y": 812
                    },
                    {
                        "x": 74,
                        "y": 847
                    },
                    {
                        "x": 66,
                        "y": 847
                    }
                    ],
                    "confidence": 0.043
                },
                {
                    "text": "раз",
                    "boundingPolygon": [
                    {
                        "x": 81,
                        "y": 812
                    },
                    {
                        "x": 119,
                        "y": 813
                    },
                    {
                        "x": 118,
                        "y": 848
                    },
                    {
                        "x": 81,
                        "y": 847
                    }
                    ],
                    "confidence": 0.336
                },
                {
                    "text": "сооб,",
                    "boundingPolygon": [
                    {
                        "x": 130,
                        "y": 813
                    },
                    {
                        "x": 209,
                        "y": 814
                    },
                    {
                        "x": 209,
                        "y": 848
                    },
                    {
                        "x": 130,
                        "y": 848
                    }
                    ],
                    "confidence": 0.07
                },
                {
                    "text": "ё",
                    "boundingPolygon": [
                    {
                        "x": 216,
                        "y": 814
                    },
                    {
                        "x": 232,
                        "y": 814
                    },
                    {
                        "x": 231,
                        "y": 848
                    },
                    {
                        "x": 216,
                        "y": 848
                    }
                    ],
                    "confidence": 0.657
                },
                {
                    "text": "шик",
                    "boundingPolygon": [
                    {
                        "x": 238,
                        "y": 814
                    },
                    {
                        "x": 298,
                        "y": 815
                    },
                    {
                        "x": 298,
                        "y": 848
                    },
                    {
                        "x": 238,
                        "y": 848
                    }
                    ],
                    "confidence": 0.044
                },
                {
                    "text": "манта,",
                    "boundingPolygon": [
                    {
                        "x": 310,
                        "y": 815
                    },
                    {
                        "x": 420,
                        "y": 814
                    },
                    {
                        "x": 420,
                        "y": 848
                    },
                    {
                        "x": 310,
                        "y": 848
                    }
                    ],
                    "confidence": 0.265
                },
                {
                    "text": "en",
                    "boundingPolygon": [
                    {
                        "x": 427,
                        "y": 814
                    },
                    {
                        "x": 456,
                        "y": 813
                    },
                    {
                        "x": 455,
                        "y": 848
                    },
                    {
                        "x": 427,
                        "y": 848
                    }
                    ],
                    "confidence": 0.089
                },
                {
                    "text": "sei).",
                    "boundingPolygon": [
                    {
                        "x": 472,
                        "y": 813
                    },
                    {
                        "x": 525,
                        "y": 812
                    },
                    {
                        "x": 524,
                        "y": 847
                    },
                    {
                        "x": 472,
                        "y": 848
                    }
                    ],
                    "confidence": 0.097
                }
                ]
            },
            {
                "text": "Quando estão escritas à mão, as palavras",
                "boundingPolygon": [
                {
                    "x": 67,
                    "y": 862
                },
                {
                    "x": 591,
                    "y": 861
                },
                {
                    "x": 591,
                    "y": 902
                },
                {
                    "x": 67,
                    "y": 904
                }
                ],
                "words": [
                {
                    "text": "Quando",
                    "boundingPolygon": [
                    {
                        "x": 68,
                        "y": 863
                    },
                    {
                        "x": 159,
                        "y": 863
                    },
                    {
                        "x": 160,
                        "y": 905
                    },
                    {
                        "x": 68,
                        "y": 905
                    }
                    ],
                    "confidence": 0.799
                },
                {
                    "text": "estão",
                    "boundingPolygon": [
                    {
                        "x": 168,
                        "y": 863
                    },
                    {
                        "x": 230,
                        "y": 862
                    },
                    {
                        "x": 231,
                        "y": 904
                    },
                    {
                        "x": 168,
                        "y": 904
                    }
                    ],
                    "confidence": 0.993
                },
                {
                    "text": "escritas",
                    "boundingPolygon": [
                    {
                        "x": 239,
                        "y": 862
                    },
                    {
                        "x": 329,
                        "y": 862
                    },
                    {
                        "x": 330,
                        "y": 903
                    },
                    {
                        "x": 239,
                        "y": 904
                    }
                    ],
                    "confidence": 0.95
                },
                {
                    "text": "à",
                    "boundingPolygon": [
                    {
                        "x": 337,
                        "y": 862
                    },
                    {
                        "x": 351,
                        "y": 862
                    },
                    {
                        "x": 352,
                        "y": 903
                    },
                    {
                        "x": 338,
                        "y": 903
                    }
                    ],
                    "confidence": 0.602
                },
                {
                    "text": "mão,",
                    "boundingPolygon": [
                    {
                        "x": 359,
                        "y": 862
                    },
                    {
                        "x": 428,
                        "y": 862
                    },
                    {
                        "x": 428,
                        "y": 903
                    },
                    {
                        "x": 360,
                        "y": 903
                    }
                    ],
                    "confidence": 0.603
                },
                {
                    "text": "as",
                    "boundingPolygon": [
                    {
                        "x": 436,
                        "y": 861
                    },
                    {
                        "x": 471,
                        "y": 861
                    },
                    {
                        "x": 472,
                        "y": 903
                    },
                    {
                        "x": 437,
                        "y": 903
                    }
                    ],
                    "confidence": 0.972
                },
                {
                    "text": "palavras",
                    "boundingPolygon": [
                    {
                        "x": 480,
                        "y": 861
                    },
                    {
                        "x": 588,
                        "y": 861
                    },
                    {
                        "x": 589,
                        "y": 903
                    },
                    {
                        "x": 480,
                        "y": 903
                    }
                    ],
                    "confidence": 0.786
                }
                ]
            },
            {
                "text": "parecem ter mais vida.",
                "boundingPolygon": [
                {
                    "x": 71,
                    "y": 911
                },
                {
                    "x": 408,
                    "y": 904
                },
                {
                    "x": 409,
                    "y": 940
                },
                {
                    "x": 71,
                    "y": 947
                }
                ],
                "words": [
                {
                    "text": "parecem",
                    "boundingPolygon": [
                    {
                        "x": 73,
                        "y": 912
                    },
                    {
                        "x": 166,
                        "y": 911
                    },
                    {
                        "x": 166,
                        "y": 946
                    },
                    {
                        "x": 73,
                        "y": 947
                    }
                    ],
                    "confidence": 0.75
                },
                {
                    "text": "ter",
                    "boundingPolygon": [
                    {
                        "x": 192,
                        "y": 910
                    },
                    {
                        "x": 235,
                        "y": 910
                    },
                    {
                        "x": 235,
                        "y": 944
                    },
                    {
                        "x": 193,
                        "y": 945
                    }
                    ],
                    "confidence": 0.812
                },
                {
                    "text": "mais",
                    "boundingPolygon": [
                    {
                        "x": 252,
                        "y": 909
                    },
                    {
                        "x": 327,
                        "y": 907
                    },
                    {
                        "x": 327,
                        "y": 942
                    },
                    {
                        "x": 252,
                        "y": 944
                    }
                    ],
                    "confidence": 0.965
                },
                {
                    "text": "vida.",
                    "boundingPolygon": [
                    {
                        "x": 335,
                        "y": 907
                    },
                    {
                        "x": 408,
                        "y": 905
                    },
                    {
                        "x": 407,
                        "y": 941
                    },
                    {
                        "x": 335,
                        "y": 942
                    }
                    ],
                    "confidence": 0.969
                }
                ]
            }
            ]
        }
        ]

## Detalhamento do Processo de Análise Descritiva das Imagens com Vision Studio

1º Na página inicial do Portal Vision Studio (https://portal.vision.cognitive.azure.com/), procurar na aba "Image analysis" a opção "Add captions to images" ao clicar nessa opção de serviço, seremos direcionados para a página do serviço (https://portal.vision.cognitive.azure.com/demo/image-captioning). Esse servição gera uma descrição dos eventos que estão ocorrendo na imagem análisada.

2º Nessa página iremos selecionar a opção "I acknowledge that this demo will incur usage to resouce ( o nome do seu recurso) in my Azure account." e selecionar uma imagem abaixo, ou fazer o update de uma imagem do seu computador.

3º Após isso se iniciará o processo de análise da imagem. Quando o processo de análise finalizar, o sistema irá transcrever o que está no arquivo de texto ou imagem de texto no quadrado ao lado direito da imagem na aba "Detected atributes".

No teste que eu realizei eu utilizei a seguinte imagem:

<img src="/inputs/Onça.jpg">

Segue abaixo o resultado da análise da imagem:

<img src="/inputs/Resultado da análise da imagem da onça.png>

4º Ele também gera um arquivo JSON, como demonstrado a baixo:

        {
        "apim-request-id": "0e6ed33b-adeb-4242-92dd-97f818654401",
        "content-length": "152",
        "content-type": "application/json; charset=utf-8",
        "modelVersion": "2023-10-01",
        "captionResult": {
            "text": "a leopard lying on a log",
            "confidence": 0.9312147498130798
        },
        "metadata": {
            "width": 1200,
            "height": 799
        }
        }

## Conclusão Geral dos Recursos da Azure Machine Learn Vision Studio.

Esses recursos podem ser muito úteis e versáteis na área da programação, tanto para auxiliar no desenvolvimento de aplicativos de acessibilidades e inclusão de pessoas com deficiência visual, quanto para abastecer banco de dados com informações como, identificação de rosto na imagem e suas caracteristicas físicas, identificação de movimento, descrição da imagem, identificação de texto e o conteúdo do texto da imagem e etc...