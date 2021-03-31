## Title

## Запуск с разными данными

### Summary

Проверим программу заменив определённые данные

### Priority

High

### Steps to reproduce

1. Установить согласное руководству IntelliJ IDEA
   https://github.com/netology-code/javaqa-homeworks/blob/master/intro/idea.md"
2. Нужно заменить код с "Hello programming!" целиком на тот, что указан в пункте "дополнительно".
3. Запустить программу
4. Изменить данные карты на другие в 4 строке(смотреть в комментарий)
5. Запустить программу
6. Изменить данные карты на другие в 4 строке
7. Запустить программу

### Expected result

1. Все шаги руководства пройдены, перед вами код с "Hello programming"
2. Код успешно заменён
3. В терминале пришел ответ Result is OK
4. Данные изменены
5. В терминале пришел ответ Result is OK
6. Данные изменены
7. В терминале пришел ответ Result is OK

### Дополнительно

1. Код для вставки (2 шаг)
  
```java
public class Main {
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
}
 


```




2. Данные для замены (выбирать любые)
 ```
   5353356627810711
   1153396727810711
   4553319427810711
   1356619427810711
   5353319427810711
   ```








