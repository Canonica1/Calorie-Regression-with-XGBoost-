# Регрессия сожжённых калорий (XGBoost + sklearn)

Реализация регрессионной модели для предсказания количества сожжённых калорий во время тренировки на основе физиологических данных и параметров тренировки. Используются методы feature engineering, лог-преобразования, масштабирование признаков и ансамблевая модель XGBoost.

## 🧠 Модель

Модель принимает на вход числовые параметры:

- Возраст, пол, рост, вес
- Пульс во время тренировки (`Heart_Rate`)
- Длительность тренировки (`Duration`)
- Температура тела (`Body_Temp`)

После инженерии признаков добавляются дополнительные характеристики:

- Индекс массы тела (BMI)
- Интенсивность тренировки (`Heart_Rate / Duration`)
- Взаимодействия признаков (например, возраст × BMI)
- Логарифмическое преобразование для устранения асимметрии

В качестве регрессионных моделей рассматривались:

- Линейная регрессия
- Ridge, Lasso, ElasticNet
- **XGBoost Regressor** (финальный выбор)

