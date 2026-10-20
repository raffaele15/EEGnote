# Modelli usati dall'Annotatore EEG

**Dal 18/10/2026 l'app usa CBraMod v3 e SpikeNet2 (anche a cascata).** SenuaLab e CBraMod v2 non sono più pubblicati (copie locali in `modelli_locali/`, fuori dal repository); le loro schede restano qui sotto per riferimento.

## ied_resnet_attention.safetensors

- Origine: [SenuaLab/EEG-IED-Detection](https://huggingface.co/SenuaLab/EEG-IED-Detection), file `models/resnet_attention/model.safetensors` (rinominato).
- SHA-256: `971fa0d2b38f0cc76ca479931872ae957123aeb51263de59b11098be1531b1e1` (verificato con MANIFEST.json del repository).
- Architettura: EEGResNetAttention, 4,99 milioni di parametri; ingresso 19 canali 10-20, 4 s a 250 Hz; uscita [non IED, IED].
- Soglia di partenza: 0,6944 (scelta dagli autori sulla validazione vEpiSet; test: AUROC 0,90, sensibilità 0,61, 0,41 falsi positivi/min).
- Licenza: CC BY 4.0, © SenuaLab; addestrato su vEpiSet (CC BY 4.0, doi:10.6084/m9.figshare.28069568).
- Uso di ricerca: non è un dispositivo medico; ogni candidato va rivisto sul tracciato.

(Non più pubblicato dal 18/10/2026.)

# Altri modelli (dal 17-18/10/2026)

Uso didattico e di ricerca, non commerciale. Non sono dispositivi medici: ogni candidato va rivisto sul tracciato.

| File | Modello | Addestramento | Licenza / permesso |
|---|---|---|---|
| `ied_resnet_attention.safetensors` | SenuaLab EEG-IED-Detection, resnet_attention | vEpiSet | CC BY 4.0 (SenuaLab) |
| `ied_cbramod_v2.onnx` (non più pubblicato) | CBraMod v2 (EEGnote) | pesi pre-addestrati CBraMod (braindecode, BSD-3-Clause), rifiniti su vEpiSet (CC BY 4.0), TUEV e TUSL (TUH EEG Corpus, NEDC), HMS (BDSP) | pubblicato con il permesso di NEDC e BDSP (18/10/2026); solo uso didattico e di ricerca |
| `ied_cbramod_v3.onnx` | CBraMod v3 (EEGnote) | come v2, più TUAR (TUH EEG Corpus) | come v2 |
| `spikenet2.onnx.part00`, `.part01` | SpikeNet2 (Li et al., NEJM AI 2025; github.com/bdsp-core/SpikeNet2) | dati BDSP | pubblicato con il permesso di BDSP (17/10/2026); codice CC BY-NC 4.0; solo uso non commerciale |
| `rallentamento_tusl.onnx` | Rallentamento per derivazione (EEGnote, rallentamento/tusl_slow.py): CBraMod rifinito, testa per derivazione | TUSL + TUAR (TUH EEG Corpus) | pubblicato con il permesso di NEDC (18/10/2026); CBraMod BSD-3-Clause; solo uso didattico e di ricerca |

I permessi possono essere revocati: in quel caso i file vanno rimossi da questa cartella.
Per usare i dati (vEpiSet, TUH, HMS, BDSP) serve l'accesso presso chi li distribuisce; il repository non contiene dati.

Citazioni: CBraMod (Wang et al., ICLR 2025); vEpiSet (doi:10.6084/m9.figshare.28069568); TUH EEG Corpus (Obeid & Picone, Front. Neurosci. 2016); HMS Harmful Brain Activity Classification (Kaggle/BDSP); SpikeNet2 (Li et al., NEJM AI 2025, doi:10.1056/AIoa2401221).


## Controllo dopo il caricamento (dimensioni e SHA-256)
- `ied_cbramod_v3.onnx`: 39.264.556 byte, `7b5ac684ddbcd4d8f13fab559bb6f984ef203bda8e70c121238e71380792cb80`
- `spikenet2.onnx.part00`: 99.614.720 byte, `ff24b8523e08419d8d68b2459d1d0c545def8ecc67854c31bf6ab605f1cc9e71`
- `spikenet2.onnx.part01`: 23.538.830 byte, `9bf0e72257ab27d9f892e51347d637aa950d1295ea2225530d0166f5a58e164a`
- `rallentamento_tusl.onnx`: 20.778.504 byte, `f05dbc9caf6c5fda29fef5d56e717b5abb574d8e6b9c93959755a01e16383164`

I file binari vanno caricati solo con GitHub Desktop (mai con "Edit" sul sito); dopo il caricamento controllare dimensioni e SHA-256 qui sopra.
