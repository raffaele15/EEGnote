# Modelli usati dall'Annotatore EEG

## ied_resnet_attention.safetensors

- Origine: [SenuaLab/EEG-IED-Detection](https://huggingface.co/SenuaLab/EEG-IED-Detection), file `models/resnet_attention/model.safetensors` (rinominato).
- SHA-256: `971fa0d2b38f0cc76ca479931872ae957123aeb51263de59b11098be1531b1e1` (verificato con MANIFEST.json del repository).
- Architettura: EEGResNetAttention, 4,99 milioni di parametri; ingresso 19 canali 10-20, 4 s a 250 Hz; uscita [non IED, IED].
- Soglia di partenza: 0,6944 (scelta dagli autori sulla validazione vEpiSet; test: AUROC 0,90, sensibilità 0,61, 0,41 falsi positivi/min).
- Licenza: CC BY 4.0, © SenuaLab; addestrato su vEpiSet (CC BY 4.0, doi:10.6084/m9.figshare.28069568).
- Uso di ricerca: non è un dispositivo medico; ogni candidato va rivisto sul tracciato.

Il file è binario: caricarlo solo con GitHub Desktop (mai con "Edit" sul sito) e controllare che resti di 20.011.088 byte.
