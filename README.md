Reference: [NVIDIA/tacotron2](https://github.com/NVIDIA/tacotron2)

## How to use
1. Put raw Japanese texts in ./filelists
2. Put WAV files in ./wav
3. (Optional) Download NVIDIA's [pretrained model](https://drive.google.com/file/d/1c5ZTuT7J08wLUoVZ2KkUs_VdZuJ86ZqA/view?usp=sharing)
4. Open ./train.ipynb to install requirements and start training
5. Download NVIDIA's [WaveGlow model](https://drive.google.com/open?id=1rpK8CzAAirq9sWZhe9nlfvxMF1dRgFbF) or [WaveGlow model](https://sjtueducn-my.sharepoint.com/:u:/g/personal/cjang_cjengh_sjtu_edu_cn/EbyZnGnCJclGl5q_M3KGWTUBq4IIqSLiGznFdqHbv3WM5A?e=8c2aWE) based on Ayachi Nene
6. Open ./inference.ipynb to generate voice

## Cleaners
File ./hparams.py line 30
### 1. 'japanese_cleaners'
#### Before
何かあったらいつでも話して下さい。学院のことじゃなく、私事に関することでも何でも
#### After
nanikaacltaraitsudemohanashItekudasai.gakuiNnokotojanaku,shijinikaNsurukotodemonanidemo.
### 2. 'japanese_tokenization_cleaners'
#### Before
何かあったらいつでも話して下さい。学院のことじゃなく、私事に関することでも何でも
#### After
nani ka acl tara itsu demo hanashi te kudasai. gakuiN no koto ja naku, shiji nikaNsuru koto de mo naNdemo.
### 3. 'japanese_accent_cleaners'
#### Before
何かあったらいつでも話して下さい。学院のことじゃなく、私事に関することでも何でも
#### After
:na)nika a)cltara i)tsudemo ha(na)shIte ku(dasa)i.:ga(kuiNno ko(to)janaku,:shi)jini ka(Nsu)ru ko(to)demo na)nidemo.
### 4. 'japanese_phrase_cleaners'
#### Before
何かあったらいつでも話して下さい。学院のことじゃなく、私事に関することでも何でも
#### After
nanika acltara itsudemo hanashIte kudasai. gakuiNno kotojanaku, shijini kaNsuru kotodemo nanidemo.

## Models
Remember to change this line in ./inference.ipynb
```python
sequence = np.array(text_to_sequence(text, ['japanese_cleaners']))[None, :]
```
