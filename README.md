# Создание индивидуальной системы достижения пользователя и ее интеграция в пользовательский интерфейс
Отчет по лабораторной работе #5 выполнила:
- Завьялова Екатерина Николаевна
- РИ300023
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | # | 60 |
| Задание 2 | # | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения.
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения.
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения.
- Выводы.

## Цель работы
создание интерактивного приложения с рейтинговой системой пользователя и интеграция игровых сервисов в готовое приложение.

## Задание 1
### Используя видео-материалы практических работ 1-5 повторить реализацию приведенного ниже функционала:
1) Практическая работа «Интеграции авторизации с помощью Яндекс
SDK»
2) Практическая работа «Сохранение данных пользователя на платформе
Яндекс Игры»
3) Практическая работа «Сбор данных об игроке и вывод их в интерфейсе»
4) Практическая работа «Интеграция таблицы лидеров»
5) Практическая работа «Интеграция системы достижений в проект»

Ход работы:
1) 
```c#
public class YGManager : MonoBehaviour
{
    private void OnEnable() => YG.YandexGame.GetDataEvent += CheckAutorisation;
    private void OnDisable() => YG.YandexGame.GetDataEvent -= CheckAutorisation;


    void Start()
    {
        if (YG.YandexGame.SDKEnabled == true)
            CheckAutorisation();
    }

    private void CheckAutorisation()
    {
        if (!YG.YandexGame.auth)
        {
            YG.YandexGame.AuthDialog();
        }
    }
}

```



![Фото](https://github.com/KatyaZav/lab-4/blob/main/Screens/1%20task/1.gif)


```c#
public static void EndGame()
    {
        if (GameCount > YG.YandexGame.savesData.RecordCount)
        {
            YG.YandexGame.savesData.RecordCount = GameCount;

            Debug.Log(YG.YandexGame.savesData.RecordCount);
        }
        
        GameCount = 0;
        LosePoints = 0;
    }
```


```c#
```

```c#
```


![Видео](https://github.com/KatyaZav/lab-4/blob/main/Screens/1%20task/3.gif)


![Видео](https://github.com/KatyaZav/lab-4/blob/main/Screens/1%20task/4.1.jpg)



## Задание 2
### Описать не менее трех дополнительных функций Яндекс SDK, которые могут быть интегрированы в игру.

Ход работы:
1) Прочитать документацию SDK и написать их

Вот что еще можно добавить в игру, используя SDK:
- Рекламные банеры
- Перевод на другие языки
- Таблицы лидеров
- Промоакции
- События, которые происходят при адблоке/читиринге



![фото](https://github.com/KatyaZav/lab-4/blob/main/Screens/2%20task/1.jpg)

Ссылка на ЯндексИгры: https://yandex.ru/games/app/190276?draft=true&lang=ru.

## Задание 3
### Доработать стилистическое оформление списка лидеров и системы достижений, реализованных в задании 1.

Ход работы:
1) Дополнить код класса для слайдера-настройки звукового проигрывателя.

```c#
```


![фото](https://github.com/KatyaZav/lab-4/blob/main/Screens/3%20task/1.gif)

## Выводы



## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
