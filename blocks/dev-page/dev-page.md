# dev-page

Отладочная страница. Пустая страница, на страницу можно подключить код/стили блоков и отладочный код.

## Модификатор `type`

Определяет тип отладочной страницы. Допустимые значения: `'test'`, `'sandbox'`.

**test**

Страница для запуска тестов. 

Добавляет в зависимости блоки `dev-jquery`, `dev-mocha`, `dev-chai`, `dev-chai-matches`, `dev-sinon`. На страницу автоматически 
рендерится код запуска тестов через mocha/mocha-phantomjs.

Страница также содержит контейнер `div#test-container` для размещения DOM-элементов блоков, создаваемых во время тестирования.


```js
{
    block: 'dev-page',
    mods: { type: 'test' },
    refs: {
        js: 'index.js',
        devJs: 'index.test.js',
        css: 'index.css'
    }
}
```

**sandbox**

Страница-песочница для независимой разработки блоков. 

Добавляет в зависимости блок `dev-sandbox` для инициализации песочницы, реализованной в технологии `.sandbox.js`.

Страница также содержит контейнер `div#sandbox-container` для размещения DOM-элементов блоков песочницы.

```js
{
    block: 'dev-page',
    mods: { type: 'sandbox' },
    refs: {
        js: 'index.js',
        devJs: 'index.sandbox.js',
        css: 'index.css'
    }
}
```
