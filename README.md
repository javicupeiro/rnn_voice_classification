# rnn_voice_classification

# Trabajo de Deep Learning

## Máster IA3 - Universidad de Valencia



<img src="img/ETSE_logo.jpg" alt="ETSE Logo" width="100" height="100"> <img src="img/IDAL_logo.png" alt="Idal logo" width="100" height="100">

Este repositorio contiene los notebooks empleados para el trabajo de la asignatura de Deep Learning, así como los pesos de los modelos con los que se ha trabajado.


### Objetivos:
- Clasificar diferentes acentos hispanos mediante el uso de RNN.
- Comparar LSTM vs GRU


<img src="img/project_archt.png" alt="project_archt" width="400" height="200">

### Dataset:

Los audios se han obtenido de  "Common Voice" de Mozilla, en particular del subset "Common Voice Delta Segment 16.1" con voces en español.

https://commonvoice.mozilla.org/es

### Transformación de los audios:
En todos los notebooks se muestra la fase de exploración de los datos del dataset así como la transformación del fichero WAV a espectrograma de MEL.

<img src="img/Captura_mel.PNG" alt="Captura_mel" width="500" height="300">

### Dataloader:
Se emplea la clase VoiceDataset para cargar los datos y realizar las transformaciones pertinentes del dataset, desde eliminar datos innecesarios como transformar los audios a espectrograma de MEL. 

<img src="img/VoiceDataset_init.png" alt="VoiceDataset_init" width="300" height="300">

Se emplea el método mágico ```__get_item__``` para procesar todo los audios

<img src="img/getitem.png" alt="getitem" width="400" height="400">

## Modelos:
### LSTM básico + 1FC:
<img src="img/lstmbasic.png" alt="lstm basic" width="500" height="400">

<img src="img/lstm_forward.png" alt="lstm forward" width="500" height="400">

### GRU básico + 1FC:
<img src="img/gru_basic.png" alt="gru basic" width="500" height="400">

### GRU avanzado:
<img src="img/gru_adv.png" alt="gru adv" width="500" height="400">

<img src="img/gru_forward_adv.png" alt="gru frw adv" width="500" height="400">

### Hiperparámetros:
Dado que se trata de un problema de clasificación con múltiples clases se ha decidido emplear el método ```CrossEntropyLoss``` [link](https://pytorch.org/docs/stable/generated/torch.nn.CrossEntropyLoss.html).

El optimizador empleado es el método ```Adam```.

El scheduler empleado para la reducción dinámica de 'learning rate' es ```ReduceLROnPlateau```.

<img src="img/hiperparametros.png" alt="hiperparametros" width="500" height="300">

### Fases de Test y Train:
#### Fase de test:

<img src="img/test.png" alt="test" width="400" height="400">

#### Fase de train:

<img src="img/train.png" alt="train" width="400" height="400">


### Librerías:
<img src="img/pytorch_logo_icon.png" alt="ETSE Logo" width="200" height="200"> <img src="img/torchaudio.png" alt="Idal logo" width="200" height="200"> <img src="img/librosa.png" alt="librosa.png" width="200" height="200">