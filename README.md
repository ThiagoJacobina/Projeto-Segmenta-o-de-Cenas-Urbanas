# Projeto: Segmentação de Cenas Urbanas com ResNet como Encoder

### Autor: Thiago Morais Jacobina

## Descrição
Este projeto tem como objetivo realizar **segmentação semântica de cenas urbanas** utilizando a arquitetura **ResNet-50 como encoder** e um **Fully Convolutional Network (FCN)** como decodificador. A tarefa é classificar cada pixel de uma imagem urbana em diferentes categorias (carros, pedestres, edifícios, etc.), com base no conjunto de dados **Cityscapes**.
O Cityscapes é um dataset de grande escala para pesquisa em visão computacional, focado especificamente em análise e segmentação de cenas urbanas. Ele é amplamente utilizado para treinar e avaliar modelos de segmentação semântica, que é a tarefa de classificar cada pixel de uma imagem.


---

## Dataset: Cityscapes

- **Cenas Diversas**: Imagens de ruas de 50 cidades diferentes na Europa.
- **Anotação Precisa**: 30 classes de objetos anotadas, com foco em 8 classes principais para o treino.
- **Tamanho Considerável**: 5.000 imagens com anotações detalhadas e 20.000 com anotações fracas.

---

## Arquitetura do Modelo

### ResNet-50 (Encoder)
- Utilizada para extrair **características hierárquicas** das imagens.
- Pré-treinada para tarefas de classificação.

### FCN - Fully Convolutional Network (Decodificador)
Responsável por reconstruir a imagem segmentada. Composto por:

1. **Upsampling**:
   - Técnicas como transconvolução para aumentar a resolução das características.
2. **Skip Connections**:
   - Ligações entre camadas do encoder e decodificador, preservando detalhes.
3. **Camada de Saída**:
   - Predição da classe para cada pixel da imagem.

---

## 📊 Métricas de Avaliação

| Métrica                 | Valor    | Descrição                                                                 |
|------------------------|----------|---------------------------------------------------------------------------|
| **mIoU**               | 0.0776   | Mean Intersection over Union: mede a sobreposição entre predição e rótulo. |
| **Loss**               | 1.9253   | Mede o erro do modelo durante o treinamento. Quanto menor, melhor.       |
| **Acurácia por Classe**| 0.2809   | Avalia o desempenho em cada classe de objeto individualmente.            |

---

## Conclusão

A combinação de **ResNet-50** com **FCN** mostrou-se eficaz na tarefa de segmentação, mesmo com métricas iniciais modestas. O projeto pode ser expandido com técnicas de data augmentation, regularização e ajustes na arquitetura para melhorar os resultados.
