# Отчет о тестировании Credit Card Number Validator
## Rраткое описание
Дата проведения:11.10.2020-12.10.2020

Было проведено:функциональное тестирвание,метод белого ящика,компонентное тестирование

Приложения: JAVA,GIT,GitHub,IntelliJ IDEA,Visual Studio Code

На тестирование затрачено 5 часов

В результате тестирования выявлены следующие дефекты

* [ссылка](https://github.com/ANNA-23021975/idea/issues/1#issue-719610250)


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

* Заведен баг-репорт

### В качестве тестовых данных использовались данные [ссылка](https://www.freeformatter.com/credit-card-number-generator-validator.html), [карта МИР](https://cardguru.io/)

* Ввести в код четвертой строки Master card 5335819212430605, ожидаемый результат-карта валидная

* Ввести в код четвортой строки JSB 5274310268714590, ожидаемый результат-карта валидная

* Ввести в код четвортой строки Виза 4929603573102622, ожидаемый результат-карта валидная

* Ввести в код четвертой строки American Express (AMEX)
348114452125487, ожидаемый результат-карта валидная; фактический результат-карта FAIL

* Ввести в код четвертой строки ,Diners Club - Северная Америка 5577843919075429, ожидаемый результат-карта валидная

* Ввести в код четвертой строки , Diners Club - Карт-бланш
30467302153494,ожидаемый результат-карта валидная; фактический результат-карта FAIL

* Ввести в код четвертой строки ,Diners Club - международный
36703086724678, ожидаемый результат-карта валидная; фактический резултат-карта FAIL

* Ввести в код четвертой строки ,МИР
2200899947183280, ожидаемый результат-карта валидная

### Тестирование проводилось в следующем окружении

* Windows 10, Домашняя

* JAVA 11

* IntelliJ IDEA     
