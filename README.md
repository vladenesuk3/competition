# competition

У першу чергу ми вивчали дані, видалили COUNTRY_ і SOURCE_ з текстових комірок, щоб перетворити їх у числові.  Змінили ios на 1 і android на 0 (замінили саме в такому порядку, щоб не було зворотної кореляції, так як прибуток з айос трохи вище, ніж з андроїдом), та також змінили колонку на числові.
  
Потім ми змінили колонку з датою встановлення на довжину життя облікового запису, у файлі з навчальними моделями ми віднімали не від сьогоднішньої дати та від останньої дати реєстрації, тому що як ми зрозуміли дані були взяті 31 січня 2022 року, тобто пів року тому, а для навчання основні моделі нам потрібно мати облікові записи, які вже прожили 30 днів(а якщо б вирахували з сьогоднішньої дати, то всі аккаунти жили були б більше 30 днів)

Після цього ми вирішили очистити дані від шумів і викидів, для цього ми використали ізоляційний ліс, кращі параметри ми знайшли за допомогою gridsearchCV, ми не кинули це ні в які файли, так як фітится  більше часу, і ми кинули в файл з EDA ізоляційний ліс вже з кращими параметрами.

Потім ми переглянули важливість колонок за допомогою RandomForestRegressor, ми побачили, що найбільш важливі колонки це прибуток за 3 дні та колонки, що входять до внутрішньої ігрової покупки (так як це найважливіша колонка).

Після цього ми вирішили визначити ступінь зацікавленості гравця за допомогою кластеризації  к-середнє передав туди всі інші параметри, які не використовувалися в основній моделі

Потім ми перевірили кілька видів моделей SVR('poly', 'linear'), LinearSVR, секвенсор з тензором та інші, але найкращі показники показали RandomForestRegressor, тому ми використали його.

Оскільки файл моделі важив 1.5 gb мы не змогли завантажити його на GitHub, тому нижче залишаємо посилання на Google Drive, в якому буде збережена модель. 

