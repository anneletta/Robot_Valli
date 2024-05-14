ЗАТО САМЫЙ КРАСИВЫЙ РОБОТ!

![photo_2024-05-14_16-19-51](https://github.com/anneletta/Robot_Valli/assets/144317669/2c41621b-4c74-4718-9f6e-1c6a17d2538c)

Наш робот состоит из деталей стандартного набора: он включает в себя моторы, контроллер, две аккумуляторные батареи, радио-модули, тумблеры,
концевик, потенциометр, RGB LED матрица и джойстик.
Мы использовали:
х1 Arduino Uno (+USB A-B)
x1 Iskra Nano Pro (+USB Micro)
x1 Motor Shield
x2 радиомодуль NRF24L01+
x3 аккумулятор Li-ion 18650
x1 держатель для аккумуляторов
x2 DC-мотор 12В с редуктором
x2 тумблер
x1 джойстик
x1 потенциометр
x2 макетная плата
x2 адаптер для NRF24L01.
Дополнительные компоненты:
*датчики, кнопки
*болты, гайки
*клей, скотч, стяжки
*сервоприводы, микросервоприводы
*концевые переключатели
*подшипники


Корпус робота был смоделирован и напечатан на 3D принтере:

![3D](https://github.com/anneletta/Robot_Valli/assets/144317669/e9dc0ee2-87da-42fa-9e23-ff765d2cdc69)


Далее описана наша поэтапная работа над роботом, а также пробелемы с которыми мы столкнулись и их решения:

1. Сборка двигателей:
После сборки мотора и подключения его к плате обнаружили, что плохо склеили припой моторов и проводов, вследствие чего провода оторвались от моторов. Решение: повтороно припояли все провода к моторам, а также надёжно склеили. 



![pult_photo](https://github.com/anneletta/Robot_Valli/assets/144317669/b56f44e0-b1ed-4d36-945c-24cc8376bac9)


2. Пульт:
После сборки пульта и многократной перепроверки схемы сборки обнаружили, что пульт не передаёт свои значния на компьютер. Решено было заменить плату Arduino Micro. А также заменить радио модуль на новый. По рузельтатам внесённых изменений значения всё ещё не подавались на компьютер, т.е. чувствительность к подвижности джойстика/тумблера игнорировалась (выводились нулевые инициализованные значения положения в виде 0.0). Проблема была выявлена и решена на этапе последующей связи мотора и пульта.


![provodki](https://github.com/anneletta/Robot_Valli/assets/144317669/7eb7f996-f5db-4418-ba46-8f0e3b554508)


3. Машинный код для пульта и мотора:
Первоначально возникла сложность с некомпелируемостью любого, даже тестового кода. Эта проблема была решена подключением дополнительных библиотек и их установкой. Дальнйёшие сложности были связаны с подключением радио модуля пульта и мотора. Дело в том, что мотор был запрограммирован верно, одна на изменения джойстика и тумблера он не регировал. Как было сказано выше, координаты джойстика и тумблера всё это время оставались нулевыми. Нами было выдвинуто предположение, что радио модуль пульта не ловит радио модуль мотора. Как оказалось в итоге, все сигналы ловились исправно, однако в сборке пульта была допущена ошибка в вдиде подключения к неверному каналу(т.е. не сопадающему с кодом). В результате: мы поменяли в коде каналы, радио сигнал был полйман , джойстик и тумблер был стали чувстивительными


Над роботом работали: Деева Анна, Кривушин Артем, Очиров Лиджи.

