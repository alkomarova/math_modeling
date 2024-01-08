# Задание 5
**ноутбук с работой** - [task3](https://github.com/alkomarova/math_modeling/blob/task5/task5.ipynb)
### Цель:
Реализация модели Хольта-Винтерса

### Задачи: 
1. Сформулировать модель Хольта-Винтерса
2. Подобрать оптимальные гиперпараметры

### Формулировка задачи: 
1. **Уровень (Level):**
   \[ L_t = \alpha \cdot (y_t - S_{t-m}) + (1 - \alpha) \cdot (L_{t-1} + T_{t-1}) \]

2. **Тренд (Trend):**
   \[ T_t = \beta \cdot (L_t - L_{t-1}) + (1 - \beta) \cdot T_{t-1} \]

3. **Сезонность (Seasonality):**
   \[ S_t = \gamma \cdot (y_t - L_t) + (1 - \gamma) \cdot S_{t-m} \]
   где \( m \) - период сезонности (например, для ежемесячных данных с месячной сезонностью \( m = 12 \)).

4. **Прогноз (Forecast):**
   \[ \hat{y}_{t+h} = L_t + h \cdot T_t + S_{t-m+h_m^+} \]
   где \( h \) - горизонт прогнозирования, \( h_m^+ = (h-1) \mod m + 1 \).

5. **Оптимизационная функция (MSE):**
   \[ \text{MSE} = \frac{1}{T-m} \sum_{t=m+1}^{T} (y_t - \hat{y}_t)^2 \]

Где:
- \( \alpha, \beta, \gamma \) - параметры модели (коэффициенты сглаживания);
- \( L_t \) - уровень (уровень уровня);
- \( T_t \) - тренд;
- \( S_t \) - сезонность;
- \( \hat{y}_{t+h} \) - прогноз на \( h \) шагов вперед.


### Заключение: 
В результате работы удалось реализовать модели Хольта-Винтерса и подобрать оптимальные гиперпараметры.
