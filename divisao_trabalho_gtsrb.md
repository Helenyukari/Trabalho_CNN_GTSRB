# Divisão de Trabalho — Trabalho de IA (GTSRB)

**Grupo:** Marcos, Helen, Emily

---

## Alinhamento inicial (antes de começar, ~10 min)

Antes de cada um seguir independentemente, o grupo precisa combinar:

- [ ] Arquitetura baseline exata (camadas conv, canais, kernel, FC) — definida pelo Marcos e compartilhada com os outros dois
- [ ] Hiperparâmetros fixos: `img_size`, `batch_size`, número de épocas
- [ ] Otimizador padrão para quem não está testando otimizadores (ex: Adam)

> O split treino/validação já vem fixo no `gtsrb.py` (seed=42), então isso não precisa ser combinado.

---

## Marcos — Baseline + Otimizadores (Experimento 1)

- [ ] Implementar a CNN baseline (Conv → ReLU → Pool ×2, Flatten, FC, saída 43 classes)
- [ ] Compartilhar a definição da arquitetura com Helen e Emily antes de todos começarem a treinar
- [ ] Treinar o baseline com **SGD**, **SGD com momentum** e **Adam**
- [ ] Gerar curvas de loss/acurácia para os três otimizadores
- [ ] Gerar os CSVs:
  - `predicoes_sgd.csv`
  - `predicoes_sgd_momentum.csv`
  - `predicoes_adam.csv`
- [ ] Escrever no relatório: **Introdução** + **Metodologia**

---

## Helen — Batch Normalization (Experimento 2)

- [ ] Pegar a arquitetura combinada com o Marcos e adicionar BatchNorm após as camadas convolucionais
- [ ] Treinar a versão **com** e **sem** BatchNorm (usando o otimizador padrão combinado)
- [ ] Gerar os CSVs:
  - `predicoes_no_bn.csv`
  - `predicoes_bn.csv`
- [ ] Calcular acurácia por classe, macro accuracy e matriz de confusão
- [ ] Escrever no relatório: **Resultados**

---

## Emily — Data Augmentation (Experimento 3) + Experimento opcional

- [ ] Pegar a arquitetura combinada e aplicar pelo menos 2 técnicas de augmentation (ex: `RandomAffine` + `ColorJitter`)
- [ ] Treinar com augmentation e gerar CSV: `predicoes_bn_aug.csv` (ou `predicoes_aug.csv`)
- [ ] Rodar um experimento opcional do grupo (ex: ResNet pequena ou comparação de tamanho de imagem) → `predicoes_resnet.csv`
- [ ] Escrever no relatório: **Discussão** + **Conclusão** (fica por último, pois depende dos resultados do Marcos e da Helen)

---

## Trabalho em conjunto (etapa final)

- [ ] Comparar todos os CSVs e métricas do grupo
- [ ] Decidir o melhor modelo do grupo
- [ ] Selecionar exemplos de imagens classificadas corretamente e incorretamente para o relatório
- [ ] Gerar o CSV final consolidado, se o professor exigir (confirmar nome do arquivo, já que o enunciado original previa apenas 2 nomes no padrão `NOME1_NOME2_RESULTS.csv`)
- [ ] Revisar o relatório completo juntos antes da entrega

---

## Entregáveis finais

- [ ] Código-fonte / notebook com os experimentos
- [ ] Relatório em PDF
- [ ] Arquivo(s) `.csv` com as predições
