Качаем ollama
В терминале windows:

ollama pull qwen3.5:9b
mkdir C:\AI\EGE
ollama pull glm-ocr:q8_0

В C:\AI\EGE перемещаем modelfile

ollama create ege-math -f C:\AI\EGE\Modelfile

Для красивой веб панели:
качаем питон 3.12 (https://www.python.org/downloads/release/python-3120/) и копируем его в папку C:\AI\EGE
py install 3.12
New-Item -ItemType Directory -Force C:\AI | Out-Null
py -3.12 -m venv C:\AI\open-webui
& "C:\AI\open-webui\Scripts\python.exe" -m pip install --upgrade pip
& "C:\AI\open-webui\Scripts\python.exe" -m pip install open-webui

запускаем веб панель в powershell
& "C:\AI\open-webui\Scripts\open-webui.exe" serve

в браузере открываем http://localhost:8080

Настройки для обеих моделей в OpenWEB:
Параметр	Значение
num_ctx	13000
max_tokens	4096
Temperature для assistant	0.7
Temperature для ege-math	0.2

ollama create assistant -f C:\AI\Assistant\Modelfile
ollama create ege-math -f C:\AI\EGE\Modelfile




https://chatgpt.com/c/6af87415-25f8-83eb-a7b9-a2dfda898ed1
