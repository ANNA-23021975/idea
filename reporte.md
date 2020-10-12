# Отчет о тестировании Credit Card Number Validator
## Rраткое описание
Дата проведения:11.10.2020-12.10.2020

Было проведено:функциональное тестирвание,метод белого ящика,компонентное тестирование

Приложения: JAVA,GIT,GitHub,IntelliJ IDEA,Visual Studio Code

На тестирование затрачено 5 часов

В результате тестирования выявлены следующие дефекты

* [ссылка](https://docs.google.com/document/d/1KtM0jlyuY42WM6wcbcSVLXU_vRtqSbrqFByVV1ya2_Y/edit?usp=sharing)

* [ссылка](https://docs.google.com/document/d/1Mz_-I68yKhvNvxvuMgYIvPJxgnVBSLq8jVB2_UXQeK4/edit?usp=sharing)

* [ссылка](https://docs.google.com/document/d/1eIkIJTiQafUGYI2_flSJgWXxxd5d5OCljw53Mh-lrc8/edit?usp=sharing)

## Описание процесса тестирования

В процессе тестирования использовались следующие артефакты

* Установить IntelliJ IDEA [по инструкции](https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md)

* Вставить вместо код "Hello programming" код <public class Main {
  public static void main(String[] args) {
    // TODO: подставлять номер карты нужно сюда между двойными кавычками, без пробелов
    String number = "5351719427810741";
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
}>

* Вставить в четвертую строку кода вымышленные номера банковских карт

* Заведены баг-репорты

### В качестве тестовых данных использовались данные [ссылка](https://www.freeformatter.com/credit-card-number-generator-validator.html)

* Ввести в код четвертой строки Master card 5335819212430605, ожидаемый результат-номер не валидный

* Ввести в код четвортой строки JSB 5274310268714590, ожидаемый результат-номер не валидный

* Ввести в код четвортой строки Виза 4929603573102622, ожидаемый результат-номер не валидный

### Тестирование проводилось в следующем окружении

* Windows 10, Домашняя

* JAVA 11

* IntelliJ IDEA     
