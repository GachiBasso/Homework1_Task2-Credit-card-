# Отчёт о тестировании функциональности валидации номера банковской карты

## Краткое описание

28.11.2021 было проведено компонентное (модульное) тестирование функциональности валидации номера банковской карты.

На тестирование затрачено: 1 час

В результате тестирования выявлены следующие дефекты:
* [Результат выполнения "Result is FAIL" при использовании валидного номера карты с кол-вом цифр, отличающимся от 16](https://github.com/GachiBasso/Homework1_Task2-Credit-card-/issues/1#issue-1065349726)

## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты:
* [Текст кейс](https://github.com/GachiBasso/Homework1_Task2-Credit-card-/blob/9b67a886dcf80f0fc103c07a899e2b4bc4666c78/Test%20case.md)
* [Баг репорт](https://github.com/GachiBasso/Homework1_Task2-Credit-card-/issues/1#issue-1065349726)

В качестве тестовых данных использовались валидные номера карт с соответствующим кол-вом цифр, сгенерированные с помощью сервисов [getcreditcardnumbers.com](https://www.getcreditcardnumbers.com), [freeformatter.com](https://www.freeformatter.com/credit-card-number-generator-validator.html).  

Тестирование производилось в следующем окружении:
* ОС Windows 10 Домашняя для одного языка (Версия 20H2, сборка 19042.1348), x64
* Java версия 11.0.13
* IntelliJ IDEA 2021.2.3 (Community Edition)
  Build #IC-212.5457.46, built on October 12, 2021
  Runtime version: 11.0.12+7-b1504.40 amd64
  VM: OpenJDK 64-Bit Server VM by JetBrains s.r.o.