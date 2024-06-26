# Православный церковный календарь

## Структура

### Дата

1) `j: number` Номер юлианского дня по григорианскому календарю (не отображается, используется как ключ для дат).

2) Вычисляемое `gdate: IDate` Дата по григорианскому календарю (н.ст.).

3) Вычисляемое `jdate: IDate` Дата по юлианскому календарю (ст.ст.).

``` ts
export interface IDate {
  Y: number;
  M: number;
  D: number;
  grigorian?: boolean,
}
```

4) Вычисляемое `dow: number` Номер дня седмицы (воскресенье – 1, понедельникы – 2).

5) Название дня седмицы (недели), особое или рядовое (Великого поста, по Пасхе, по Пятидесянице).

## Уставные указания

1) Номер гласа (`1-8`, когда поется Октоих или `0`, когда не поется)

2) Постный день (подробности поста)

```ts
export enum FastKind {
  NoFood,     //Полное воздержание от пищи
  StrictFast, //Сухоядение
  WithoutOil, //Горячая пища без масла
  WithOil,    //Горячая пища с маслом
  Caviar,     //Разрешаются икра
  Fish,       //Разрешается рыба, растительное масло и вино
  NoMeat,     //Исключается мясо
  NoFast,     //Нет поста
  Wine,       //Разрешается вино
}

export const IsFast = (fk: FastKind): boolean => fk != FastKind.NoFast;
```

3) Особое поминовение усопших

## Основной блок календаря

1) `l: 0` памяти или события Триоди, праздники

2) `l: 1` праздники

3) `l: 2` имена вселенских и русских святых, в том числе новомучеников и исповедников Церкви Русской, имеющих службу в минеях и триодях, а также некоторых новопрославленных русских святых, независимо от того, есть или пока еще нет им службы.

4) `l: 3` имена всех остальных святых, память которых приходится в данный день, кроме новомучеников и исповедников Церкви Русской.

5) `l: 4` имена новомучеников и исповедников Церкви Русской, которым пока еще нет отдельных служб

6) `l: 5` праздники в честь местночтимых икон Божией Матери

## Сайтовый блок календаря

1) Акафисты дня

2) Каноны дня

## Дополнительный блок календаря

1) Литургия (какая положена литургия)

2) Цвет облачения (?)

3) Браковенчания

4) Чтения св. Писания

## Богослужебный блок

1) Тропарь, кондак, величание, молитва

2) Богослужебные указания
