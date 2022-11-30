# Доработка интерактивного приложения и его подготовка к сборке.
Отчет по лабораторной работе #4 выполнила:
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
интеграция интерфейса пользователя в разрабатываемое интерактивное приложение.

## Задание 1
### Используя видео-материалы практических работ 1-5 повторить реализацию приведенного ниже функционала:


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
```


![Видео](https://github.com/KatyaZav/lab-4/blob/main/Screens/1%20task/3.gif)


![Видео](https://github.com/KatyaZav/lab-4/blob/main/Screens/1%20task/4.1.jpg)



## Задание 2
### Привести описание того, как происходит сборка проекта проекта под другие платформы. Какие могут быть особенности?

Ход работы:
1) Посмотреть какие бывают стандартные сборки:
- Мобильное устройства
- Веб
- ПК

Из неосновных:
- VR
- PS4, например

Каждый из этих варантов запускается только на определенном устройстве (для веба нужен сервер, для запуска надо загрузить на платформу или выбрать "build and run").

![фото](https://github.com/KatyaZav/lab-4/blob/main/Screens/2%20task/1.jpg)

Ссылка на ЯндексИгры: https://yandex.ru/games/app/190276?draft=true&lang=ru.

## Задание 3
### Добавить в меню Option возможность изменения громкости (от 0 до 100%) фоновой музыки в игре.

Ход работы:
1) Дополнить код класса для слайдера-настройки звукового проигрывателя.

```c#
public class _Slider : MonoBehaviour
{
    Slider slider;
    public bool isMusic;

    MainMenu soundManager;

    private void OnEnable()
    {
        if (slider == null)
            Start();

        //Debug.Log("enable");
        if (isMusic)
            slider.value = MainMenu.VolumeMusic;
        else
            slider.value = MainMenu.VolumeSounds;
    }

    void Start()
    {
        soundManager = GameObject.FindGameObjectWithTag("SoundManager").GetComponent<MainMenu>();
        slider = GetComponent<Slider>();

        if (isMusic)
            slider.value = MainMenu.VolumeMusic;
        else
            slider.value = MainMenu.VolumeSounds;
    }

    public void UpdateSoundsVolume()
    {
        MainMenu.VolumeSounds = slider.value;
        soundManager.UpdateVolume();
    }

    public void UpdateMusicVolume()
    {
        MainMenu.VolumeMusic = slider.value;
        soundManager.UpdateVolume();
    }
}
```

Осталось все скрипты повесить на объекты.

![фото](https://github.com/KatyaZav/lab-4/blob/main/Screens/3%20task/1.gif)

## Выводы

Я попыталась сделать базовую навигацию кнопок, научилась работать со звуками и музыкой, поработала со слайдерами.

Так же я посмотрела возможные платформы для билда.

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
