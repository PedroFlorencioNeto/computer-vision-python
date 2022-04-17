# Visão Computacional em Python

---

Este notebook tem como objetivo reunir as principais frameworks existentes em Python para o desenvolvimento de projetos na área de Visão Computacional.

Autor: Pedro Florencio de Almeida Neto

---

<aside>
💡 **Visão Computacional** é a ciência que estuda e desenvolve tecnologias que permitem que as máquinas enxerguem e extraiam características do meio, através de imagens capturadas por diferentes tipos de sensores e dispositivos. Essas informações permitem reconhecer, manipular e processar dados sobre os objetos que compõem a imagem capturada.

*Computer Vision* (1982) - Ballard e Brown.

</aside>

1. **Imagens**
Matematicamente, imagens são um conjunto de *pixels* que variam de 0 a 1, quando são representadas de forma binária, isto é, quando utilizam um espaço de cor limitado a 2 bits (Figura 01). O valor 0 é graficamente interpretado como a cor preta e 1 branca. 
    
    ![Figura 01: Imagens binárias](Visa%CC%83o%20Com%20c4f45/Untitled.png)
    
    Figura 01: Imagens binárias
    
    Para a representação de imagens em tons de cinza, há uma margem para cada pixel, que carrega a informação de intensidade de luz, sendo representado por 8 bits. Ao utilizar esta quantidade de bits, há portanto 2⁸ = 256 níveis de de “cinza”. As imagens coloridas são constituídas pela sobreposição de canais de cores de vermelho (R), verde (G) e azul (B), onde cada um representa a intensidade dessas cores primárias variando de 0 a 255.
    
    ![Figura 02: Sobreposição de canais RGB](Visa%CC%83o%20Com%20c4f45/Untitled%201.png)
    
    Figura 02: Sobreposição de canais RGB
    

1. **OpenCV**

[OpenCV: OpenCV-Python Tutorials](https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html)

**2.1 Instalação**

```python
pip install opencv-python
```

**2.2 Importando a biblioteca**

```python
import cv2
```

**2.3 Carregando uma imagem** 

```python
# Carrega a imagem a partir de um arquivo
img = cv2.imread('assets/michaelscott.jpg') 

# Mostra a imagem na tela com o nome "Michael Scott"
cv2.imshow('Michael Scott', img) 

# Tempo de exibição da imagem em ms (0 siginifica infinito) 
cv2.waitKey(0)
```

**2.4 Carregando um vídeo**

O método VideoCapture da OpenCV permite o carregamento do vídeo e o método read() retorna um booleano que informa se a leitura foi bem sucedida além dos frames do vídeo.

```python
# Carrega o vídeo a partir de um arquivo
cap = cv2.VideoCapture('assets/michaelscott.mp4')

# Estrutura de repetição que reproduz cada frame
while True:
    success, frame = cap.read()
    cv2.imshow('No God No!', frame)
    # Critério de parada é a tecla q
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Fechar arquivo de vídeo
cap.release()

# Fechar as janelas abertas
cv2.destroyAllWindows()
```

**2.5 Capturando com a webcam**

Há uma única alteração fundamental com relação ao código anterior: o valor do parâmetro no método VideoCapture.

```python
# Inicializa a webcam. O valor 0 é utilizado quando há uma única webcam conectada
cap = cv2.VideoCapture(0)

# Tamanho  da janela. O valor 3 se refere à width e 4 se refere à height
cap.set(3,640) 
cap.set(4,480)

# Ajuste do brilho
cap.set(10,100)

# Estrutura de repetição que reproduz cada frame
while True:
    success, frame = cap.read()
    cv2.imshow('Janela Webcam', frame)
    # Critério de parada é a tecla q
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

# Fechar arquivo de vídeo
cap.release()

# Fechar as janelas abertas
cv2.destroyAllWindows()
```

1. **Convolutional Neural Networks**
    
    **3.1 Introdução Teórica**
    
    **3.2 Implementando uma CNN no Tensorflow e Keras**
    
    **3.3 Implementando uma CNN no Pytorch**
