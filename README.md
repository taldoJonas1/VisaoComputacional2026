# Contador de Objetos com Visão Computacional

## Descrição do Projeto

Este projeto é uma aplicação de Visão Computacional desenvolvida em Python com OpenCV.  
O objetivo é detectar e contar objetos posicionados sobre uma superfície clara, como moedas, tampinhas, celulares ou outros itens.

A aplicação pode ser usada no cotidiano para facilitar a contagem rápida de objetos sobre uma mesa, sem precisar contar manualmente um por um.

O projeto **não utiliza Inteligência Artificial, Machine Learning ou redes neurais**.  
Toda a detecção é feita com algoritmos clássicos de processamento de imagens.

---

## Problema Resolvido

Em algumas situações do dia a dia, é necessário contar vários objetos sobre uma superfície. Fazer isso manualmente pode ser demorado e sujeito a erro.

A aplicação resolve esse problema utilizando a câmera do computador para identificar automaticamente os objetos e exibir a quantidade detectada na tela em tempo real.

---

## Tecnologias Utilizadas

- Python 3
- OpenCV
- NumPy
- Webcam do computador

---

## Técnicas de Visão Computacional Utilizadas

O projeto utiliza técnicas clássicas de Visão Computacional, sem uso de IA:

### 1. Captura de vídeo pela webcam
A webcam captura os frames em tempo real. Cada frame é processado individualmente como uma imagem estática.

### 2. Conversão para escala de cinza
A imagem colorida é convertida para escala de cinza para simplificar o processamento e reduzir o custo computacional.

### 3. Gaussian Blur
É aplicado um desfoque gaussiano para suavizar a imagem e reduzir ruídos antes do threshold.

### 4. Threshold com método de Otsu
A imagem em escala de cinza é binarizada usando o método de Otsu, que calcula automaticamente o melhor valor de limiar para separar objetos escuros do fundo claro.

### 5. Operações morfológicas
São aplicadas as operações de **Opening** (para remover pequenos ruídos) e **Closing** (para fechar buracos internos nos objetos detectados), melhorando a qualidade da máscara binária.

### 6. Detecção de contornos
Os contornos dos objetos são encontrados usando `cv2.findContours` com modo `RETR_EXTERNAL`, capturando apenas os contornos externos.

### 7. Filtragem por área e contagem
Cada contorno válido dentro do intervalo de área configurado é contado como um objeto. Contornos fora do intervalo são descartados para evitar falsos positivos.

### 8. Calibração em tempo real com Trackbars
A aplicação abre uma janela de configuração com sliders que permitem ajustar os parâmetros de detecção (área mínima, área máxima e blur) em tempo real, sem precisar alterar o código.

---

## Instalação

Clone este repositório:

```bash
git clone https://github.com/SEU-USUARIO/contador-objetos-opencv.git
```

Entre na pasta do projeto:

```bash
cd contador-objetos-opencv
```

Instale as dependências:

```bash
pip install -r requirements.txt
```

---

## Como Executar

Execute o arquivo principal:

```bash
python main.py
```

A webcam será aberta junto com a janela de resultado e a janela de configurações com os sliders.

Para encerrar a aplicação, pressione:

```
q
```

---

## Como Usar

1. Coloque os objetos sobre uma folha branca ou superfície clara.
2. Evite sombras fortes e procure ter boa iluminação.
3. Execute o programa.
4. Observe o valor **"Maior contorno: X px"** exibido na parte inferior da tela — ele indica a área em pixels do maior objeto detectado.
5. Ajuste o slider **Area Min** para um valor um pouco abaixo do número exibido.
6. Ajuste **Area Max** para descartar objetos maiores do que os desejados.
7. Use o slider **Blur** para suavizar mais a imagem caso apareçam ruídos.
8. Veja na tela a quantidade de objetos detectados em tempo real.

---

## Estrutura do Projeto

```
contador-objetos-opencv/
├── main.py
├── requirements.txt
├── README.md
├── imagens/
│   ├── exemplo_1.png
│   ├── exemplo_2.png
│   └── resultado.png
└── video/
    └── funcionamento.mp4
```

---

## Imagens do Projeto
[!Imagem_1](imagens\imagem1.png)
[!Imagem_2](imagens\imagem2.png)
[!Imagem_3](imagens\imagem3.png)

---

## Vídeo de Funcionamento

O vídeo demonstrando a aplicação em funcionamento está disponível na pasta:
(video\video demonstracao visao computacional.mp4)
```
video/funcionamento.mp4
```

