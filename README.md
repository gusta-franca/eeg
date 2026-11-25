# Extração de Caracterísitcas em Sinais Biológicoss

Trabalho para a disciplina OPT098 - Tópicos Especiais Em Sistemas De Computação (ICO_CM) do Bacharelado em Ciêncida da Computação da Universidade Tecnolófica Federal do Paraná.

Estudante: Gustavo Martins França

A principal pesquisa utilizada como referência foi [Thinking out loud, an open-access Data Descriptor EEG-based BCI dataset for inner speech recognition](https://www.nature.com/articles/s41597-022-01147-2) (Nieto et al., 2022). Os datasets utilizados estão disponíveis em https://openneuro.org/datasets/ds003626, e todos os arquivos em `src/` foram retirados do repositório https://github.com/N-Nieto/Inner_Speech_Dataset, ambos disponibilizado em Nieto et al (2022).

## Execução

Crie um ambiente Python e instale as dependências do projeto:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Entre no diretório `notebooks` e execute-os em ordem.


## Pré-processamentos

Todos os datasets de sinais EEG disponiblizados foram pré-processados por Nieto et al.:

- Os canais EXG1 e EXG2 (utilizadas como referência nos lóbulos) foram utilizados como referência. Em todos os outros canais, foi subtraída a média dos canais EXG1 e EXG2;

- Foi aplicado um filtro Notch de 50 Hz e um filtro band-pass de 0,5 - 100 Hz;

- Os dados foram dizimados 4 vezes, obtendo uma taxa de amostragem de 265 Hz.;

- Os dados foram epocados para manter apenas os dados entre o início e fim de um trial (4,5s);

- Foi aplicada uma Independent Component Analysis (ICA) nos 128 canais EEG. Ruído advindo de movimentos musculares foram removidos previamente a partir dos canais EXG.

Por conta dos pré-processamentos já aplicados, o presente repositório não contém um notebook para a etapa de pré-processamentos.

## Referências

NIETO, Nicolás; PETERSON, Victoria; RUFINER, Hugo Leonardo; KAMIENKOSKI, Juan; SPIES, Ruben. “Thinking out loud”: an open-access eeg-based bci dataset for inner speech recognition. Nature, [S.L.], 20 abr. 2021. http://dx.doi.org/10.1101/2021.04.19.440473. Disponível em: https://www.nature.com/articles/s41597-022-01147-2.pdf. Acesso em: 14 set. 2026.
