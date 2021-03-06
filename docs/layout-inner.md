<style>
    .example .tpl-grid__fraction {
        background: var(--color-bg-brand);
        min-height: 100px;
    }
</style>

`tpl-grid` – адаптивная сетка для контентных блоков. Есть два сценария использования: [сетка с равными секциями](#Сетка-с-равными-секциями) для равнозначных блоков и [колоночная сетка](#Колоночная-сетка) для блоков разной ширины.

?> Помните, что все адаптивные правила перестроения и изменения свойств наследуются от меньшего брейкпоинта к большему.

## Отступы
Для управления отступами используй модификаторы на расстояние между колонками и между строками. В них используются переменные с префиксом `--col-gap-`, `--row-gap-`, которые находятся в теме, где их можно при необходимости переопределить. Перед началом использования сеток, советуем прочитать про [отступы в теме](http://whitepaper.tools/doc.html#/theme-gap).

Модификатор | Значение                                        | Описание
----------- | ----------------------------------------------- | --------------------------
col-gap     | full / two-thirds / half / third / none         | Отступ между колонками: полный / две-трети / половина / треть / без отступа
row-gap     | full / two-thirds / half / third / none         | Отступ между строками: полный / две-трети / половина / треть / без отступа

## Сетка с равными секциями
Достаточно указать только количество секций в строке, расстояние между колонками и расстояние между строками. Все прямые «дети» такой секции сами подстроятся по указанным правилам.

Для каждого брейкпоинта из [указанных в теме](http://whitepaper.tools/doc.html#/theme-breakpoint)  можно указывать свой модификатор `ratio`, но это необязательно.

Модификатор | Значение                                          | Описание
----------- | ------------------------------------------------- | --------------------------
xs-ratio    | 1-1 / 1-1-1                                       | Количество секций в одном ряду сетки при ширине экрана `screen-xs`
s-ratio     | 1-1 / 1-1-1 / 1-1-1-1 / 1-1-1-1-1 / 1-1-1-1-1-1   | Количество секций в одном ряду сетки при ширине экрана `screen-s`
m-ratio     | 1-1 / 1-1-1 / 1-1-1-1 / 1-1-1-1-1 / 1-1-1-1-1-1   | Количество секций в одном ряду сетки при ширине экрана `screen-m`
l-ratio     | 1-1 / 1-1-1 / 1.1-1-1 / 1-1-1-1-1 / 1-1-1-1-1-1   | Количество секций в одном ряду сетки при ширине экрана `screen-l`
xl-ratio    | 1-1 / 1-1-1 / 1-1-1-1 / 1-1-1-1-1 / 1-1-1-1-1-1   | Количество секций в одном ряду сетки при ширине экрана `screen-xl`

### Пример
Меняйте размер экрана браузера, чтобы увидеть адаптивное перестроение сетки.

<div class="example">
    <div class="tpl-grid tpl-grid_s-ratio_1-1 tpl-grid_m-ratio_1-1-1 tpl-grid_l-ratio_1-1-1-1 tpl-grid_col-gap_third tpl-grid_row-gap_third">
        <div class="tpl-grid__fraction"></div>
        <div class="tpl-grid__fraction"></div>
        <div class="tpl-grid__fraction"></div>
        <div class="tpl-grid__fraction"></div>
    </div>
</div>

```html
<div class="tpl-grid tpl-grid_s-ratio_1-1 tpl-grid_m-ratio_1-1-1 tpl-grid_l-ratio_1-1-1-1 tpl-grid_col-gap_third tpl-grid_row-gap_third">
    <div class="tpl-grid__fraction">
        ...
    </div>
</div>
```

## Колоночная сетка

Чтобы описать колоночную сетку, нужно указать несколько модификаторов: количество колонок `columns`, расстояние между колонками и расстояние между строками. Каждому элементу `fraction` надо отдельно указывать размеры. Колоночная сетка хорошо подходит, если внутренние секции не равнозначны и могут быть разной ширины или высоты.

Для каждого брейкпоинта из [указанных в теме](http://whitepaper.tools/doc.html#/theme-breakpoint) при необходимости можно указывать свой модификатор `columns`.

Если на твоем проекте сетка с другим количеством колонок, создай нужное значение модификатора на [уровне проекта](whitepaper-stub.md).

Модификатор  | Значение               | Описание
-----------  | ---------------------- | --------------------------------------
xs-columns   | 2 / 3                  | Количество возможных колонок при ширине экрана `screen-xs`
s-columns    | 5 / 6 / 8              | Количество возможных колонок при ширине экрана `screen-s`
m-columns    | 6 / 10 / 12            | Количество возможных колонок при ширине экрана `screen-m`
l-columns    | 6 / 10 / 12            | Количество возможных колонок при ширине экрана `screen-l`
xl-columns   | 6 / 10 / 12            | Количество возможных колонок при ширине экрана `screen-xl`

### Примеры
Меняйте размер экрана браузера, чтобы увидеть адаптивное перестроение сетки.

<div class="example">
    <div class="tpl-grid tpl-grid_s-columns_6 tpl-grid_m-columns_10 tpl-grid_l-columns_12 tpl-grid_col-gap_third tpl-grid_row-gap_third">
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_6 tpl-grid__fraction_l-col_8"></div>
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_4"></div>
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_4"></div>
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_6 tpl-grid__fraction_l-col_8"></div>
    </div>
</div>

```html
<div class="tpl-grid tpl-grid_s-columns_6 tpl-grid_m-columns_10 tpl-grid_l-columns_12 tpl-grid_col-gap_third tpl-grid_row-gap_third">
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_6 tpl-grid__fraction_l-col_8">
        ...
    </div>
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_4">
        ...
    </div>
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_4">
        ...
    </div>
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_m-col_6 tpl-grid__fraction_l-col_8">
        ...
    </div>
</div>
```


<div class="example">
    <div class="tpl-grid tpl-grid_s-columns_6 tpl-grid_l-columns_12 tpl-grid_col-gap_third tpl-grid_row-gap_third">
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_6 tpl-grid__fraction_l-col_8 tpl-grid__fraction_l-row_2"></div>
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_l-col_4"></div>
        <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_l-col_4"></div>
    </div>
</div>

```html
<div class="tpl-grid tpl-grid_s-columns_6 tpl-grid_l-columns_12 tpl-grid_col-gap_third tpl-grid_row-gap_third">
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_6 tpl-grid__fraction_l-col_8 tpl-grid__fraction_l-row_2">
        ...
    </div>
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_l-col_4">
        ...
    </div>
    <div class="tpl-grid__fraction tpl-grid__fraction_s-col_3 tpl-grid__fraction_l-col_4">
        ...
    </div>
</div>
```

## Элемент fraction

В колоночной сетке элементы `fraction` имеют модификаторы на ширину в колонках `col` и опциональный на высоту в строках `row`. Также с помощью модификатора `order` можно переопределять порядок элемента в общем потоке с помощью.

Модификатор | Значение                                         | Описание
----------- | ------------------------------------------------ | --------------------------
xs-col      | 1 / 2 / 3                                        | Ширина элемента в колонках при ширине экрана `screen-xs`
s-col       | 1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12 | Ширина элемента в колонках при ширине экрана `screen-s`
m-col       | 1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12 | Ширина элемента в колонках при ширине экрана `screen-m`
l-col       | 1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12 | Ширина элемента в колонках при ширине экрана `screen-l`
xl-col      | 1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12 | Ширина элемента в колонках при ширине экрана `screen-xl`
xs-row      | 1 / 2 / 3                                        | Высота элемента в колонках при ширине экрана `screen-xs`
s-row       | 1 / 2 / 3                                        | Высота элемента в колонках при ширине экрана `screen-s`
m-row       | 1 / 2 / 3                                        | Высота элемента в колонках при ширине экрана `screen-m`
l-row       | 1 / 2 / 3                                        | Высота элемента в колонках при ширине экрана `screen-l`
xl-row      | 1 / 2 / 3                                        | Высота элемента в колонках при ширине экрана `screen-xl`
xs-order    | -1 / 0 / 1                                       | Порядок элемента в общем потоке при ширине экрана `screen-xs`
s-order     | -1 / 0 / 1                                       | Порядок элемента в общем потоке при ширине экрана `screen-s`
m-order     | -1 / 0 / 1                                       | Порядок элемента в общем потоке при ширине экрана `screen-m`
l-order     | -1 / 0 / 1                                       | Порядок элемента в общем потоке при ширине экрана `screen-l`
xl-order    | -1 / 0 / 1                                       | Порядок элемента в общем потоке при ширине экрана `screen-xl`
