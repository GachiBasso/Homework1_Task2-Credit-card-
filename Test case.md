# Тест кейс № 1
## Название (Title)
Ввод валдиных номеров банковских карт в функциональность валидации номера банковской карты     
## Предварительные условия (Preconditions)
Скопировать следующий код функциональности в тестовую среду Java (класс Main):
```Java
public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "4730290330590767";
    System.out.println(String.format("Result is %s", isValidCardNumber(number) ? "OK" : "FAIL"));
  }

  public static boolean isValidCardNumber(String number) {
    if (number == null) {
      return false;
    }

    if (number.length() != 16) {
      return false;
    }

    long result = 0;
    for (int i = 0; i < number.length(); i++) {
      int digit;
      try {
        digit = Integer.parseInt(number.charAt(i) + "");
      } catch (NumberFormatException e) {
        return false;
      }

      if (i % 2 == 0) {
        digit *= 2;
        if (digit > 9) {
          digit -= 9;
        }
      }
      result += digit;
    }

    return (result != 0) && (result % 10 == 0);
  }
}
```
## Шаги (Steps to reproduce):
1. В поле «String number = "";» ввести без пробелов между двойными кавычками состоящий из 16 цифр валидный номер карты, и запустить (Run) выполнение кода.
2. В поле «String number = "";» ввести без пробелов между двойными кавычками состоящий из 13 цифр валидный номер карты, и запустить (Run) выполнение кода.
3. В поле «String number = "";» ввести без пробелов между двойными кавычками состоящий из 19 цифр валидный номер карты, и запустить (Run) выполнение кода.
## Ожидаемый результат
По результатам выполнения кода выводимые данные ("Result is OK") и код выхода ("Process finished with exit code 0") не отражают ошибок.
## Комментарии и пояснения к тесту
* Стандартным кол-вом цифр в номере банковской карты является 16.
* Минимальным кол-вом цифр в номере банковской карты является 13.
* Максимальным кол-вом цифр в номере банковской карты является 19.
* Валидные номера банковских карт могут быть сгенерированы специальными сервисами (например, [getcreditcardnumbers.com](https://www.getcreditcardnumbers.com), [freeformatter.com](https://www.freeformatter.com/credit-card-number-generator-validator.html)).