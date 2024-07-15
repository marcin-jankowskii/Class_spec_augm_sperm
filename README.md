Aby kod zadziałał należy pozmieniać ścieżki.
Stworzony został plik config.yaml, który znajduję się w folderze Kod/config

W plikach train i inference w init wybierany jest obecnie używany config 
" "place": "lab" "
W przypadku gdy w inicie ustawiony jest "lab" to używany jest config_lab.yaml tam należy pozmieniać ścieżki.

Aby uruchomić trening należy mode ustawić na "multiclass" lub "normal"
" "mode": "normal" "

Przykładowy init:

wandb.init(project="example", entity="example",
            config={
            "epochs": 300,
            "batch_size": 6,
            "lr": 1e-3,
            "annotator": 1,
            "model": 'smpUNet++',
            "augmentation": False,
            "loss": "CrossEntropyLoss",
            "optimizer": "Adam",
            "scheduler": "CosineAnnealingLR",
            "place": "lab",
            "mode": "normal",
            "aug_type": "BetterAugmentation",
            "k": 5 })

Aby wyniki były zgodne z artykułem należy użyć annotatora 1
" "annotator": 1 "

Przy inferencji należy ustawić mode na "intersection_inference"

!!!!
Brakuje datasetu, należy w configu określić jego ścieżkę
