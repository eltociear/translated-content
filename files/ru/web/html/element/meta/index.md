---
title: <meta>
slug: Web/HTML/Element/meta
translation_of: Web/HTML/Element/meta
---
{{HTMLRef}}

**HTML-элемент `<meta>`** представляет такие {{Glossary("Metadata","метаданные")}}, которые не могут быть представлены другими HTML-метатегами, такими как {{HTMLElement("base")}}, {{HTMLElement("link")}}, {{HTMLElement("script")}}, {{HTMLElement("style")}} или {{HTMLElement("title")}}.

| [Категории контента](/ru/docs/Web/HTML/Content_categories) | Мета данные. Если задан {{htmlattrxref("itemprop")}} атрибут: [flow content](/ru/docs/Web/HTML/Content_categories#Flow_content), [phrasing content](/ru/docs/Web/HTML/Content_categories#Phrasing_content).                                                               |
| ---------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Разрешённое содержимое                                     | Отсутствует - это {{Glossary("empty element","пустой элемент")}}.                                                                                                                                                                               |
| Пропуск тега                                               | Так как это пустой элемент, то открывающий тег должен присутствовать, а закрывающий - отсутствовать.                                                                                                                                                                              |
| Разрешённые родительские элементы                          | `<meta charset>`, `<meta http-equiv>`: {{HTMLElement("head")}} элемент. Если {{htmlattrxref("http-equiv", "meta")}} это не заявленная декларация, то может быть внутри элемента {{HTMLElement("noscript")}} или {{HTMLElement("head")}}. |
| Разрешённые роли ARIA                                      | Отсутствуют                                                                                                                                                                                                                                                                       |
| DOM интерфейс                                              | {{domxref("HTMLMetaElement")}}                                                                                                                                                                                                                                          |

## Атрибуты

Этот элемент включает в себя [глобальные атрибуты](/ru/docs/Web/HTML/Global_attributes).

> **Примечание:** атрибут {{htmlattrxref("name", "meta")}} имеет особое значение для элемента `<meta>` и атрибут {{htmlattrxref("itemprop")}} не должен быть задан в `<meta>` элементе в котором уже определены какие-либо {{htmlattrxref("name", "meta")}}, {{htmlattrxref("http-equiv", "meta")}} или {{htmlattrxref("charset", "meta")}} атрибуты.

- {{htmlattrdef("charset")}}
  - : Этот атрибут задаёт кодировку символов, используемую на странице. Он должен содержать [стандартное имя IANA MIME для кодировки символов](https://www.iana.org/assignments/character-sets). Хотя стандарт не требует определённой кодировки, он рекомендует:\* Авторам рекомендуется использовать `{{glossary("UTF-8")}}`.
    - Не следует использовать ASCII-несовместимые кодировки, чтобы избежать угроз безопасности: браузеры, не поддерживающие их, могут интерпретировать вредоносный контент как HTML. Это относится к семейству кодировок `JIS_C6226-1983`, `JIS_X0212-1990`, `HZ-GB-2312`, `JOHAB` и `EBCDIC`.

  > **Примечание:** ASCII-несовместимые кодировки - это те, которые не преобразуют 8-битные коды точек `0x20`,`0x7E`, `0x0020`, `0x007E` в коды Unicode точек.

  > **Предупреждение:** \* Авторы **не должны** использовать `CESU-8`, `UTF-7`, `BOCU-1` и/или `SCSU`, так как есть примеры атак [межсайтового скриптинга](/ru/docs/Glossary/Cross-site_scripting) использующих данные кодировки.
      > - Авторам не следует использовать кодировку `UTF-32`, потому что не все алгоритмы кодирования HTML5 могут отличить её от `UTF-16`.

  > **Примечание:\*** Указанный набор символов должен соответствовать одной странице.
      >   Нет веских оснований для объявления неточного набора символов.
      > - `<meta>` элемент должен находиться внутри элемента {{HTMLElement("head")}} и задаваться в **1024 первых байтах** HTML страницы, поскольку некоторые браузеры смотрят только эти байты перед выбором кодировки.
      > - Этот `<meta>` элемент - часть алгоритма, определяющего набор символов ([algorithm to determine the character set](https://www.whatwg.org/specs/web-apps/current-work/multipage/parsing.html#encoding-sniffing-algorithm "Algorithm charset page")) страницы, который браузер поддерживает. Заголовок {{HTTPHeader("Content-Type")}} и любые {{Glossary("Byte-Order Mark","Byte-Order Marks")}} элементы переопределяют данный элемент.
      > - Настоятельно рекомендуется определить кодировку символов. Если для страницы не определён набор символов, то некоторые cross-scripting технологии могут повредить страницу, например такие как [UTF-7 fallback cross-scripting technique](https://code.google.com/p/doctype-mirror/wiki/ArticleUtf7). Постоянная установка этого элемента будет защищать вас от этого риска.
      > - Этот {{HTMLElement("meta")}} элемент это синоним для pre-HTML5 `<meta http-equiv="Content-Type" content="text/html; charset=IANAcharset"> `где *`IANAcharset` *соответствует значению эквивалентного {{htmlattrxref("charset", "meta")}} атрибута.
      >   Этот синтаксис по-прежнему разрешён, хотя и устарел и больше не рекомендуется.
- {{htmlattrdef("content")}}
  - : Этот атрибут содержит значение для {{htmlattrxref("http-equiv", "meta")}} или {{htmlattrxref("name", "meta")}} атрибута, в зависимости от контекста.
- {{htmlattrdef("http-equiv")}}
  - : Этот атрибут определяет прагму, которая может изменять поведение серверов и пользователей. Значение прагмы определяется с помощью {{htmlattrxref("content", "meta")}} и может быть следующим:_ `"content-language"` {{obsolete_inline}}
    _ : Эта прагма определяет значение языка страницы по умолчанию.

  > **Примечание:** Не используйте эту прагму, так как она устарела Используйте глобальный атрибут {{HTMLElement("html")}} элемента вместо этого.
    - `"Content-Security-Policy"`
      - : Это значение позволит администратору веб-сайта определить политику содержания для обслуживаемых ресурсов. За некоторыми исключениями, политика в основном включают в себя указание происхождения сервера и конечные точки сценария. Это помогает предотвратить атаки межсайтового скриптинга.
    - `"content-type"` {{obsolete_inline}}
      - : Этот атрибут определяет [MIME type](/ru/docs/MIME) документа. За ним следует синтаксис такой же как и в поле заголовка объекта содержимого HTTPI, однако как и внутри HTML-элемента, большинство этих значений не доступно.
        Поэтому допустимым синтаксисом для его содержимого является литеральная строка '`text/html`', за которой следует набор символов со следующим синтаксисом: '`; charset=`_`IANAcharset`_' где `IANAcharset` это предпочтительное _MIME имя_ для набора символов, который определяется как[ IANA.](https://www.iana.org/assignments/character-sets)> **Примечание:** **Замечания:\*** Не используйте эту прагму, так как она устарела. Используйте атрибут{{htmlattrxref("charset", "meta")}} в элементе {{HTMLElement("meta")}} вместо этого.
        > - {{HTMLElement("meta")}} не может быть использована для выбора типа документа в XHTML документе, или в HTML5 документе, за которым следует XHTML синтаксис, никогда не задавайте MIME тип как XHTML MIME. Это будет некорректно.
        > - Только HTML документ может использовать контент-тип, так что большинство из них являются неиспользуемыми, поэтому они являются устаревшими и заменяются {{htmlattrxref("charset", "meta")}} атрибутом.
    - `"default-style"`
      - : Специализация этой прагмы - предпочтительный стиль таблиц, используемый на странице. {{htmlattrxref("content", "meta")}} атрибут должен содержать заголовок {{HTMLElement("link")}} элемента который {{htmlattrxref("href", "link")}} связывает атрибут с CSS таблцей стилей, или заголовок {{HTMLElement("style")}} элемента, который содержит [CSS](/ru/docs/Web/CSS) таблицу стилей.
    - `"refresh"`
      - : Эта прагма определяет:\* Количество секунд перезагрузки таблицы, если {{htmlattrxref("content", "meta")}} атрибут содержит только целое положительное число;
        - Время, в количестве секунд, за которое страница должна быть перенаправлена ​​на другую, если {{htmlattrxref("content", "meta")}} атрибут содержит целое положительное число, заканчивающийся строкой '`;url=`' и корректный URL.
    - `"set-cookie"` {{obsolete_inline}}
      - : Эта прагма определяет [cookie](/ru/docs/cookie) для страницы. Её содержимое должно заканчиваться синтаксисом, определяемым [IETF HTTP Cookie Specification](https://tools.ietf.org/html/draft-ietf-httpstate-cookie-14).

  > **Примечание:** **Замечание:** Не используете эту прагму, так как она устарела. Используйте HTTP header set-cookie вместо этого.
- {{htmlattrdef("name")}}

  - : Этот атрибут определяет имя уровня документа метаданных.
    Его не следует устанавливать, если один из атрибутов {{htmlattrxref("itemprop", "meta")}}, {{htmlattrxref("http-equiv", "meta")}} или {{htmlattrxref("charset", "meta")}} также указан в наборе.
    Имя этого документального уровня метаданных связано со значением, которое содержится в {{htmlattrxref("content", "meta")}} атрибуте.Допустимые значения для имени элемента, со связанными с ними значениями, хранятся посредством {{htmlattrxref("content", "meta")}} атрибута:\* `application-name`, определяет имя веб-приложения, запущенного на веб-странице;

        > **Примечание:** **Замечание:***   Браузеры могут использовать его для идентификации приложения. Он отличается от {{HTMLElement("title")}} элемента, который обычно состоит из имени приложения, но также может содержать специальную информацию, как например имя документа или статус;
        > *   Простые веб-страницы не определяют application-name meta.

    - `автор` определяет в свободном формате имя автора документа;
    - описание, содержащее краткое и точное резюме содержания страницы. В некоторых браузерах, среди которых Firefox и Opera, этот мета используется как описание страницы по умолчанию в закладке;
    - генератор, содержащий в свободном формате идентификатор программного обеспечения, создавшего страницу;;
    - Ключевые слова, представленные строками, разделёнными запятыми, связанные с содержанием страницы
    - `referrer` {{experimental_inline}} контролирует содержимое HTTP. `Referer` HTTP - заголовок, прикреплённый к любому запросу, отправленному из этого документа:

      | `no-referrer`                | Не отправлять HTTP `Referer` заголовок.                                                                                                                                          |
      | ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
      | `origin`                     | Отправить оригинал.                                                                                                                                                              |
      | `no-referrer-when-downgrade` | Отправить оригинал, как ссылку по умолчанию на безопасный пункт (https->https), но не отправлять ссылку на менее безопасную структуру (https->http). Это поведение по умолчанию. |
      | `origin-when-crossorigin`    | Отправляет полный URL (удалённый из параметров) при выполнении запроса с тем же источником, или только оригинал документа в других случаях.                                      |
      | `unsafe-URL`                 | Отправляет полный URL (удалённый из параметров), при выполнении запроса того же или перекрёстного происхождения.                                                                 |

      > **Примечание:** **Замечание:** Некоторые браузеры поддерживают ключевые слова всегда, по умолчанию и никогда для реферера. Эти значения устарели.

      > **Примечание:** **Замечание:** Динамическая вставка `<meta name="referrer">` (с помощью document.write или appendChild) создаёт недетерминизм, когда дело доходит до отправки рефереров. Также стоит отметить, что когда определяется несколько конфликтующих политик, применяется No-referrer policy.Атрибут также может иметь значение, взятое из существующего листа определений [WHATWG Wiki MetaExtensions page](https://wiki.whatwg.org/wiki/MetaExtensions). Хотя ни один из них официально не был принят, в число предложений входят несколько часто используемых имён:\* `creator`, определят в свободном формате имя создателя документа. Это также может быть имя института. Если же имён больше чем одно, то несколько {{HTMLElement("meta")}} элементов должны быть использованы;

    - `googlebot`, синоним `robots`, но только следует за Googlebot, сканирует индексы для Google;
    - `publisher`, определяет в свободном формате имя того, кто опубликовал документ. Это также может быть имя института;
    - `robots`, определяет поведение, поисковых роботов на странице. Список этих значений представлен ниже:

      | Значение       | Описание                                                                                                                                                     | Используется                                                                                                                                                                                                                                                                                      |
      | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
      | `index`        | Позволяет роботу индексировать страницу                                                                                                                      | All                                                                                                                                                                                                                                                                                               |
      | `noindex`      | Освобождает робота от индексирования страниц                                                                                                                 | All                                                                                                                                                                                                                                                                                               |
      | `follow`       | Позволяет роботу переходить по ссылкам со страницы                                                                                                           | All                                                                                                                                                                                                                                                                                               |
      | `nofollow`     | Запрещает роботу переходить по ссылкам со страницы                                                                                                           | All                                                                                                                                                                                                                                                                                               |
      | `none`         | Эквивалентно `noindex, nofollow`                                                                                                                             | [Google](https://support.google.com/webmasters/answer/79812)                                                                                                                                                                                                                                      |
      | `noodp`        | Запрещает использование [Open Directory Project](https://www.dmoz.org/) описания, если таковые имеются, как описание страницы на странице результатов поиска | [Google](https://www.google.com/support/webmasters/bin/answer.py?hl=en&answer=79812), [Yahoo](https://help.yahoo.com/l/us/yahoo/search/indexing/indexing-11.html;_ylt=Arh3LHnisvRMPJKzQqmJ97JYqCN4), [Bing](https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240) |
      | `noarchive`    | Запрещает поисковой системе кешировать содержимое страницы.                                                                                                  | [Google](https://www.google.com/support/webmasters/bin/answer.py?hl=en&answer=79812), [Yahoo](https://help.yahoo.com/l/us/yahoo/search/indexing/basics-10.html;_ylt=Aszma_Ly8TfhL7mn_LGWn5RYqCN4), [Bing](https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240)   |
      | `nosnippet`    | Запрещает отображение любого описания страницы на странице результатов поиска                                                                                | [Google](https://www.google.com/support/webmasters/bin/answer.py?answer=35304), [Bing](https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240)                                                                                                                      |
      | `noimageindex` | Запрещает отображение этой страницы в качестве ссылающейся страницы индексированного изображения.                                                            | [Google](https://www.google.com/support/webmasters/bin/answer.py?hl=en&answer=79812)                                                                                                                                                                                                              |
      | `nocache`      | Синоним `noarchive`                                                                                                                                          | [Bing](https://www.bing.com/webmaster/help/which-robots-metatags-does-bing-support-5198d240)                                                                                                                                                                                                      |

      > **Примечание:** **Замечания:\*** Только кооперативные роботы будут следовать правилам, определённым именем роботов.
      >
      > - Роботу необходимо получить доступ к странице, чтобы считать мета значение. Если вы хотите скрыть от них информацию, то используйте _[robots.txt](/ru/docs/Robot_Exclusion_Protocol "Robot Exclusion Protocol")_ файл.
      > - Если вы хотите удалить страницу индекса, изменение мета в noindex будет работать, но только тогда, когда робот снова посетит страницу. Убедитесь, что файл robots.txt не предотвращает такие посещения. Некоторые поисковые системы имеют инструменты, позволяющие быстро удалить какую-либо страницу.
      > - Некоторые возможные значения взаимно исключают друг друга, такие как использование индекса и noindex или follow и nofollow одновременно. В этих случаях поведение робота не определено и может варьироваться от одного к другому. Поэтому избегайте этих случаев.
      > - Некоторые поисковые роботы-роботы, такие как Google, Yahoo Search или Bing, поддерживают те же значения в директиве HTTP, X-Robot-Tags: это позволяет им использовать эту прагму для документов, отличных от HTML, например изображений.

    - `slurp`,синоним `robots`, но следует только за Slurp, индексирующим роботом от Yahoo Search;Наконец несколько общих терминов:\* `viewport`, который даёт подсказки о размере изначального размера {{glossary("viewport")}}. Эта прагма используется только на некоторых мобильных устройствах.

      | Значение        | Допустимые значения                                   | Описание                                                                                                                 |
      | --------------- | ----------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
      | `width`         | целое положительное число или литерал `device-width`  | Определяет ширину области просмотра в пикселях                                                                           |
      | `height`        | целое положительное число или литерал `device-height` | Определяет высоту области просмотра в пикселях                                                                           |
      | `initial-scale` | положительное число между `0.0` и `10.0`              | Определяет соотношение между шириной устройства и размером области просмотра                                             |
      | `maximum-scale` | положительное число между `0.0` и `10.0`              | Определяет максимальное значение зума; должен быть больше или равен минимальному масштабу или быть неопределённым.       |
      | `minimum-scale` | положительное число между `0.0` и `10.0`              | Определяет минимальное значение зума; должен быть меньше или равен максимальному масштабу или быть неопределённым.       |
      | `user-scalable` | булевское значение (да или нет)                       | Если весь набор содержит значения нет, то пользователю не доступен зум на веб-странице. По умолчанию задано значение да. |

      | Спецификация                                                                                             | Статус                           | Комментарий                                  |
      | -------------------------------------------------------------------------------------------------------- | -------------------------------- | -------------------------------------------- |
      | {{SpecName('CSS3 Device', '#viewport-meta', '&lt;meta name="viewport"&gt;')}} | {{Spec2('CSS3 Device')}} | Ненормативно описывает элемент META Viewport |

      Смотрите также: {{cssxref("@viewport")}}

      > **Примечание:** **Замечания:\*** Хотя и не стандартизирован, этот атрибут используется разными мобильными браузерами, например Safari Mobile, Firefox for Mobile or Opera Mobile.
      >
      > - Значения по умолчанию могут быть изменены у разных браузеров или устройств..
      > - Для изучения этой прагмы на Firefox for Mobile, посмотрите статью [this article](/ru/docs/Mobile/Viewport_meta_tag "Mobile/Viewport meta tag").

- {{htmlattrdef("scheme")}} {{obsolete_inline}}
  - : Этот атрибут определяет схему, которая описывает метаданные.
    Схема - это контекст, ведущий к правильной интерпретации {{htmlattrxref("content", "meta")}} значения, например формата.

  > **Примечание:** **Замечание:** Не используйте этот атрибут, так как он устарел. Для него нет никакой замены, поскольку реально он не использовался. Опустите его.

## Замечания

В зависимости от установленных атрибутов, тип метаданных может быть одним из следующих:

- Если в наборе {{htmlattrxref("name", "meta")}}, то это _document-level_ _metadata_, применяемая ко всей странице.
- Если в наборе{{htmlattrxref("http-equiv", "meta")}} , то это _pragma directive_,
  то есть информация, веб-сервер предоставляет информацию о том, как должна обслуживаться веб-страница.
- Если в наборе {{htmlattrxref("charset", "meta")}}, то это _charset declaration_,
  то есть кодировка, используемая для сериализованной формы веб-страницы.
- Если в наборе {{htmlattrxref("itemprop", "meta")}}, то это _user-defined metadata_,
  прозрачна для агента пользователя, поскольку семантика метаданных зависит от пользователя. {{experimental_inline}}

## Пример

```html
<!-- In HTML5 -->
<meta charset="utf-8">

<!-- Redirect page after 3 seconds -->
<meta http-equiv="refresh" content="3;url=https://www.mozilla.org">
```

## Спецификации

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- Другие элементы, содержащие метаданные: {{HTMLElement("base")}}, {{HTMLElement("head")}}, {{HTMLElement("link")}}, {{HTMLElement("style")}},{{HTMLElement("title")}}.