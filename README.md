# Facial-Recognition-Azure

Reconhecimento Facial e transformação de imagens em Dados no Azure Machine Learning.

Detalhamento do processo de analise facial com Azure Machine Learning

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

5º Nessa página nós podemos observar que temos uma variedade de recursos, o recurso que nós iremos utilizar nessa atividade, se chama "Detect faces in an image", clique nele para sermos direcionados para a página de trabalho do recurso.

6º Nessa página iremos ativar a opção "I acknowledge that this demo will incur usage to resouce ( o nome do seu recurso) in my Azure account.", agora selecione uma das imagens a baixo ou faça o update da imagem que voce desejar que contenha um rosto, para que ele possa analisar a imagem e lhe informar abaixo a confirmação de detecção de uma face na imagem selecionada, a quantidade de faces na imagem, se o rosto está coberto por alguma máscara ou algum outro objeto e o que a máscara ou o outro objeto está tapando:

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

7º Podemos também adquirir um arquivo JSON, com o código da imagem analisada, onde podemos utilizar em uma aplicação, ou em um banco de dados e etc...

<<<<<<< Updated upstream
8º Como exemplo prático eu utilizei uma imagem minha
=======
8º Como exemplo prático eu utilizei uma imagem minha:

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

>>>>>>> Stashed changes
