video    https://youtu.be/uc21cH0cDNo🔍 

Camera Check

Для перевірки роботи камери можна запустити:

gst-launch-1.0 nvarguscamerasrc ! nvoverlaysink

⚠️ Проблеми, з якими я зіткнувся

❌ Неправильна класифікація об’єктів
Наприклад: Class names: ['bird'], хоча очікував "person".

❌ Невірна інтерпретація вихідних тензорів YOLOv8
Jetson Nano добре працює з YOLOv5, а я використав YOLOv8, через що результати виявились некоректними.

🧩 Реалізація

Створив клас TRTDetector та TRTResults, які працюють подібно до ultralytics на ПК.

Клас приймає frame та параметр conf=0.3, де conf — це поріг впевненості моделі.

📉 Поточний статус проекту

Проєкт було зупинено через слабку продуктивність Jetson Nano.
Основна проблема — невірна інтерпретація вихідних тензорів YOLOv8.
👉 Рішення: замінити YOLOv8 на YOLOv5, оскільки вона краще адаптована під Jetson Nano.

📂 Основні файли

camera.py — потрібно налаштувати свій camera pipeline.

⚡ Вимоги

JetPack 4.6

TensorRT (перевірити сумісну версію для конкретної збірки)
------------------------------------------------------------------------------------------------------------------------
🔍 Camera Check

To verify the camera functionality, run:

gst-launch-1.0 nvarguscamerasrc ! nvoverlaysink

⚠️ Issues Encountered

❌ Incorrect object classification
Example: detected class ['bird'] instead of expected "person".

❌ Invalid interpretation of YOLOv8 output tensors
Jetson Nano works well with YOLOv5, but using YOLOv8 caused incorrect inference results.

🧩 Implementation

Developed custom classes TRTDetector and TRTResults, mirroring the behavior of Ultralytics inference on desktop.
The detector takes a video frame and a confidence threshold parameter conf=0.3, where conf defines model confidence.

📉 Project Status

The project was paused due to Jetson Nano’s limited performance.
The main issue was incorrect YOLOv8 tensor parsing.
👉 Solution: switch to YOLOv5, which is better optimized for Jetson Nano.

📂 Key Files

camera.py — requires manual setup of the camera pipeline.

⚡ Requirements

JetPack 4.6

TensorRT (check compatibility with your specific JetPack version)



