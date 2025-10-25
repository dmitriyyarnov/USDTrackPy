## USDTrackPy
Проект для **сбора, хранения, анализа и предоставления курса USD с сайта ЦБ РФ на Python**.
### **Что делает проект**
1. **Сбор данных (скрапинг)**  
   - `scraper.py` получает текущий курс USD с сайта ЦБ РФ.  
   - Сохраняет данные в JSON-файл в папке `data/` (например: `data/2025-09-22.json`).  

2. **Анализ и визуализация**
   -  plot.py строит график динамики курса USD с помощью matplotlib.
   -  График отображается в отдельном окне matplotlib.
  <img width="640" height="480" alt="68e2e32209c072 84908179a56b8cc5" src="https://github.com/user-attachments/assets/bb60a0bf-61b4-4b61-a751-93a43b2cf792" />
     
3. **API** для получения исторических курсов USD из JSON-файлов (data/).
   - Параметры: limit (1–100, по умолчанию 10), sort (asc/desc, по умолчанию desc)

### Установка зависимостей
    pip install -r requirements.txt

### Сбор первого курса USD
    python scraper.py

### Построение графика
    python plot.py
График динамики курса USD откроется в отдельном окне matplotlib.

### Rates API
API на FastAPI для получения исторических курсов USD из JSON-файлов (`data/`). 
Запуск:  
     
    uvicorn app.main:app --reload
Эндпоинт: `GET /rates`  
Параметры: `limit` (1–100, по умолчанию 10), `sort` (`asc`/`desc`, по умолчанию `desc`)  
Пример: 'http://127.0.0.1:8000/rates', 'GET http://127.0.0.1:8000/rates?limit=5&sort=desc'

Swagger UI: 'http://127.0.0.1:8000/docs'