# 👋 Привет! Я Егор Болонкин

<div align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white" alt="PyTorch">
  <img src="https://img.shields.io/badge/CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white" alt="CUDA">
  <img src="https://img.shields.io/badge/Machine%20Learning-FF9F1C?style=for-the-badge&logo=ml&logoColor=white" alt="ML">
  <img src="https://img.shields.io/badge/Computer%20Vision-4CAF50?style=for-the-badge&logo=opencv&logoColor=white" alt="CV">
  <img src="https://img.shields.io/badge/Physics-1E90FF?style=for-the-badge&logo=atom&logoColor=white" alt="Physics">
</div>

---

## 🧑‍🎓 Обо мне

Data Scientist / ML Engineer с фундаментальной подготовкой по теоретической физике. Учусь на **5-м курсе специалитета** Физического факультета МГУ им. М.В. Ломоносова (кафедра квантовой статистики и теории поля, 2022–2028).

Делаю модели, которые можно обучить, измерить и запустить: глубокое обучение, speech ML (ASR/TTS), LLM-системы, reinforcement learning, компьютерное зрение, аномалии во временных рядах и нейросетевые суррогаты физических симуляторов. Рядом с исследованием — инженерная обвязка: PyTorch, CUDA, Docker, CI, экспорт в ONNX.

Интересны задачи на стыке физики и машинного обучения: ускорители, численные методы, суррогатные модели.

---

## 🎓 Образование

**Московский государственный университет имени М.В. Ломоносова**, Физический факультет  
Кафедра квантовой статистики и теории поля, специалитет (5-й курс, 2022–2028)

Квантовая теория поля, статистическая физика, теория групп, моделирование физических систем на GPU, параллельное программирование, квантовая теория рассеяния.

---

## 🚀 Проекты

### Трассировка пучка и нейросетевой суррогат

Полный цикл моделирования пучка заряженных частиц: магнитное поле конечного соленоида (Био–Савар), интерполяция на 2D-сетке, релятивистский трекер на алгоритме Бориса (Numba CUDA) и MLP, который предсказывает отклонение от свободного пролёта, а не всю траекторию.

На учебной задаче ускорительной физики суррогат (~10³ параметров) дал ускорение около **1300×** относительно эталонного трекера при mean Δr/r ≈ 1.2×10⁻³. Безразмерная нормировка и аугментация поворотом пучка.

Публичный код:

- [Beam-Tracing](https://github.com/Egor-Error000/Beam-Tracing) — трекер во внешних полях (соленоиды, квадруполи, диполи, RF), PIC в RZ-геометрии
- [Beam-Surrogate](https://github.com/Egor-Error000/Beam-Surrogate) — генерация датасета, обучение и оценка MLP-суррогата, MLflow
- [Coursework](https://github.com/Egor-Error000/Coursework) · [solenoid_tracker](https://github.com/Egor-Error000/solenoid_tracker)

**Стек:** Python, PyTorch, Numba CUDA, SciPy, HDF5, Matplotlib.

---

### Обнаружение аномалий во временных рядах

Два дополняющих подхода к многоканальным рядам и раннему поиску отклонений.

**Transformer Autoencoder + contrastive learning.** Окна восстанавливает автокодировщик-трансформер, InfoNCE разводит режимы в латентном пространстве, взвешенная MSE компенсирует дисбаланс. Оценка аномалии сочетает квантильный порог и Z-score с весом, который зависит от стабильности ошибок. События собираются по длительности и связности; сдвиг домена смотрится через PCA/UMAP.

**Hierarchical temporal VAE + forecasting.** Иерархический VAE с головой прогноза. Аномалия читается по латентному пространству (GMM), ошибке реконструкции и ошибке прогноза следующего состояния; канал-источник — по поканальным остаткам.

**Стек:** PyTorch, multi-GPU, Docker.

---

### Речевые модели и голосовые агенты

Сравнение ASR-моделей (Qwen, Whisper, SenseVoice) по качеству и скорости, стриминговые замеры ASR и TTS (TTFT, RTF, TTFA) через HTTP/WebSocket, сборка voice-to-voice агента (ASR + TTS + LLM) на одном GPU.

**Стек:** vLLM, vLLM-Omni, Qwen3, Faster-Whisper, FunASR, Docker, GitLab CI.

---

### Reinforcement learning

Прикладные RL-пайплайны: MaskablePPO (обучение с нуля и дообучение) и DAgger, единый формат чекпоинтов для нескольких алгоритмов, экспорт политики в ONNX вместе с метриками и артефактами прогона, CI для сборки и проверки.

**Стек:** PyTorch, Stable-Baselines3, TorchRL, pydantic, ONNX.

---

### Label Studio Converters

Python-библиотека: экспорт Label Studio → разметка для детекции (полигоны и прямоугольники). Реестр конвертеров, CLI и Python API, параллельная обработка, тесты (unit / integration / e2e), линтеры.

**Стек:** Python, black, ruff, isort, pytest, GitLab CI.

---

### Антиферромагнитная XXX-цепочка

Точная диагонализация спиновой цепочки \(s = 1/2\), \(J = 1\), открытые и периодические границы, чётные \(N = 4, \ldots, 26\).

**[Репозиторий](https://github.com/Egor-Error000/XXX--)**

---

### Учебные и пет-проекты

| Проект | О чём | Стек |
|--------|--------|------|
| [Анализ спортивных видео](https://github.com/Egor-Error000/AI_and_Individual_sports-CV) | Детекция, трекинг, pose estimation | PyTorch, Faster R-CNN, DeepSort, HRNet, Numba |
| [Мультиагентная LLM-система](https://github.com/Egor-Error000/AI-agents-and-multi-agent-systems) | Агенты с веб-поиском и символьной математикой | Together API, SerpApi, Wolfram Alpha, SymPy, Docker |
| [Дилемма заключённого](https://github.com/Egor-Error000/The-prisoner-s-dilemma) | Стратегии через policy gradient и self-play | PyTorch, RNN/LSTM/GRU |
| [Задержки авиарейсов](https://github.com/Egor-Error000/-2013-) | Регрессия по открытым данным 2013 года | XGBoost, CatBoost, MLflow |
| [Детекция людей, YOLOv8](https://github.com/Egor-Error000/Person-Detection_YOLOv8x) | Детекция | YOLOv8, PyTorch |
| [U-Net](https://github.com/Egor-Error000/-U-Net) | Сегментация | PyTorch |

---

## 🛠️ Стек

**Языки:** Python, C++, CUDA (Numba)

**ML:** PyTorch, Transformers, VAE, Vision Transformers, GNN, scikit-learn, XGBoost, CatBoost, UMAP

**Speech / LLM:** vLLM, vLLM-Omni, Qwen3, Whisper, Faster-Whisper, FunASR

**RL:** Stable-Baselines3 (MaskablePPO), TorchRL, DAgger, ONNX

**Инженерия:** Docker, GitLab CI, MLflow, HDF5, pydantic, OpenCV

**Научные расчёты:** NumPy, SciPy, pandas, Matplotlib

---

## 📫 Контакты

<div align="center">

**Email:** [bolonkin.ev22@physics.msu.ru](mailto:bolonkin.ev22@physics.msu.ru) · [bolonkin.egor16@gmail.com](mailto:bolonkin.egor16@gmail.com)  
**Телефон:** +7 (953) 080-73-92  
**Локация:** Москва, Россия  
**GitHub:** [Egor-Error000](https://github.com/Egor-Error000)

</div>
