### Компиляция
`gcc -Wall -g <название файла который компилируем> -o <название файла в который все компилируется>`
* `-Wall` включает все разумные предупреждения
* `-g` включает всю отладочную информацию

Пример: `gcc -Wall -g hello.c -o hello`
### Подключение библиотеки при компиляции
`gcc -Wall -g -lm -Calc.c -o calc`
* `-lm` - подключение библиотеки (математической в этом случае)

### Функция вывода 
```
printf("%d times %d is %d\n", x, x, x * x);
```
* `%d` - параметр как целое число
* `%x` - параметр как шестнадцетиричное число
* `%f` - параметр как число с точкой, а `%.5f` - сколько знаков после запятой

### Функция ввода
`scanf` - возвращает число, успешно обслуженных введенных данных ("процентов"). Например:
```
n = scanf("%lf %lf %lf", &p, &q, &r);
if(n != 3){
  printf("Error: wrong input.\n");
  return 1;
}
```

* `%f` - число с точкой
* `%lf` - длинное число с точкой
### Операция взятия адреса 
`&t` - взятие адреса с переменной `t`