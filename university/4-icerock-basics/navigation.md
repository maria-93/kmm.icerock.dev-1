---
sidebar_position: 13
---

# Навигация между экранами

## Android 

Для навигации в Android-приложении мы будем использовать [Navigation component](https://developer.android.com/guide/navigation).  
Вы уже читали об этом в блоке [Экраны и навигация](../android-basics/user-interface#экраны-и-навигация), повторите при необходимости.

## iOS

Для понимания того, как будет реализована навигация в `iOS` приложениях на проектах, ознакомьтесь сначала с [видео-разбором](https://www.youtube.com/watch?v=Pt9TGFzLVzc) использования `ApplicationCoordinator` для навигации между экранами, а затем со [статьей](../../learning/ios/navigation) и материалами из нее.

В наших проектах, для верстки и навигации на iOS мы больше не будем использовать `.storyboard`, вместо этого мы будем пользоваться следующими инструментами:
- `AppCoordinator` - главный координатор приложения, который будет запускать другие координаторы в зависимости от входных данных
- Другие координаторы - отвечают за свои зоны приложения (авторизация, просмотр новостей, редактирование профиля и тд)
- `.xib` и `код` для верстки
    - экраны верстаем в `.xib`
    - `navigation items` и более сложные настройки делаем через `код`

## Практическое задание

В качестве практики предлагаем вам потренироваться в использовании `AppCoordinator`. На основе [mobile-moko-boilerplate](https://gitlab.icerockdev.com/scl/boilerplate/mobile-moko-boilerplate) сделать следующее приложение:
- всего 2 экрана: `AuthViewController` и `HomeViewController` и 3 координатора: `AppCoordinator`, `AuthCoordinator` и `HomeCoordinator`
- `AuthViewController` - экран регистрации, добавьте сюда поле для ввода никнейма и кнопку "Login"
- `HomeViewController` - основной экран приложения, добавьте сюда `Label` с приветствием юзера по никнейму и кнопку "Logout"
- никнейм сохранять в параметры устройства используя `NSUserDefaults`
- использовать `AppCoordinator` для первичной навигации:
  - если никнейм есть в `NSUserDefaults` - запускать `HomeViewController`
  - иначе - запускать `AuthCoordinator`
- не использовать `.storyboard`, создавайте необходимые контроллеры и свяжите их с `.xib`
- для `AuthViewController` используйте `.xib` с таким же именем, а для `HomeViewController` создайте `.xib` с отличающимся именем
