# Распознавание рукописного текста

В рамках проекта рассматривались подходы к распознаванию рукописного текста:
- Готовый продукт Tesseract OCR,
- Использование связки из свёрточной сети ResNet и рекуррентной BiLSTM.

[Презентация](handwritten%20text%20recognition.pdf) содержит основную информацию о проекте, [ноутбук](handwritten%20text%20recognition.ipynb) отображает
весь код, необходимый для экспериментов.

# Модели
1. Готовое решение Tesseract Open Source OCR Engine (https://github.com/tesseract-ocr/tesseract), а именно его Python wrapper (https://github.com/madmaze/pytesseract).
2. Предобученные DL модели (https://github.com/clovaai/deep-text-recognition-benchmark): ResNet-BiLSTM-{CTC encoder/Attention}.

# Используемые данные для экспериментов
В качестве датасета использовался набор [IAM Handwriting](https://fki.tic.heia-fr.ch/databases/iam-handwriting-database), содержащий 1539 страниц англязычных
текстов, написанных различными людьми. Почерк очень разный, что делает датасет хорошим проверочным набором данных.

# Выводы
Файн тюненные нейросетевые модели куда лучше справились с распознаванием, чем Tesseract из коробки. 
Tesseract OCR больше подходит для распознавания не рукописных символов, а текстов со строгими шрифтами.
