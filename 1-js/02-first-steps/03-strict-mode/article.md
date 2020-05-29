# حالت مدرن، “use strict”

برای مدتی طولانی جاوا اسکریپت بدون مشکل سازگار پذیری توسعه داده می‌شد و امکانات جدید بدون اینکه نیازی به تغییر در امکانات قبلی باشد، به این زبان اضافه می‌شد.

مزیت این موضوع در این بود که هیچگاه در کدهای قدیمی اشکالی بوجود نمی‌آمد. اما مشکل اینجا بود که اگر اشکالی در طراحی زبان، توسط خالقان جاوا اسکریپت رخ داده بود، تا ابد بجا می‌ماند.

این موضوع تا سال 2009 که ECMAScript 5 (ES5) معرفی شد، ادامه داشت.ES5 قابلیت‌های جدیدی را به زبان افزود و اصلاحاتی را نیز بر روی امکانات فعلی انجام داد. 

به منظور اینکه کدهای قدیمی کار کنند، بیشتر تغییراتی که در ES5 اتفاق افتاد، به صورت پیش‌فرض غیر فعال است، و برای فعال‌سازی آنها باید از طریق عبارت `"use strict"` چنین کاری را انجام داد.

## "use strict"

عبارتِ دستوریِ (directive) `"use strict"` یا `'use strict'` شبیه به یک رشته است که زمانیکه در ابتدای اسکریپت قرار می‌گیرد، تمام اسکریپت در حالت مدرن کار خواهد کرد.
برای نمونه :


```js
"use strict";

// this code works the modern way
...
```

<<<<<<< HEAD
در مورد فانکشِن‌ها (روشی برای گروه‌بندی کردن دستورات) در آینده خواهیم آموخت. 

در اینجا صرفا بدانید که می‌توانیم در ابتدای اکثر فانکشن‌ها `"use strict"` قرار دهیم تا قواعد مدرن صرفا بر روی کدهای داخل فانکشن اعمال شوند.

=======
Quite soon we're going to learn functions (a way to group commands), so let's note in advance that `"use strict"` can be put at the beginning of a function. Doing that enables strict mode in that function only. But usually people use it for the whole script.
>>>>>>> cd2c7ce3c8f033e6f7861ed1b126552e41ba3e31

````warn header="از بالا بودن عبارت \"use strict\" در کدهای خود مطمئن شوید"

این عبارت حتما باید در ابتدای اسکریپت شما باشد، در غیر این صورت حالت مدرن فعال نخواهد شد.
Strict mode در اینجا فعال نیست :

```js no-strict
alert("some code");
// "use strict" below is ignored--it must be at the top

"use strict";

// strict mode is not activated
```

فقط Comment ها می‌توانند در بالای `"use strict"` قرار گیرند..
````

```warn header="هیچ راه برای خنثی کردن `use strict` وجود ندارد"
هیچ دستوری مانند `no use strict` وجود ندارد تا به موتور جاوا اسکریپت دستور دهد به روش قدیمی کار کند.
زمانی‌که `use strict` را قرار می‌دهیم، راه برگشتی وجود ندارد.

```

<<<<<<< HEAD
## کنسول مرورگر
=======
## Browser console

When you use a [developer console](info:devtools) to run code, please note that it doesn't `use strict` by default.
>>>>>>> cd2c7ce3c8f033e6f7861ed1b126552e41ba3e31

در ادامه کار زمانیکه از کنسول مرورگر خود برای اجرای کدها استفاده می‌کنید در نظر داشته باشید که این کنسول به طور پیش فرض از `use strict` استفاده نمی‌کند.
گاهی اوقات زمانیکه وجود `use strict` تفاوتی ایجاد می‌کند، استفاده از کنسول مرورگر نتایج اشتباهی به شما خواهد داد.
حتی اگر از `key:Shift+Enter` برای وارد کردن عبارت `use strict` استفاده نمایید، نتیجه نخواهد داد.

<<<<<<< HEAD
راه حل قابل اتکا برای این موضوع آن است که به این شکل عبارت `use strict` را وارد نمایید :
=======
So, how to actually `use strict` in the console?

First, you can try to press `key:Shift+Enter` to input multiple lines, and put `use strict` on top, like this:

```js
'use strict'; <Shift+Enter for a newline>
//  ...your code
<Enter to run>
```

It works in most browsers, namely Firefox and Chrome.

If it doesn't, e.g. in an old browser, there's an ugly, but reliable way to ensure `use strict`. Put it inside this kind of wrapper:
>>>>>>> cd2c7ce3c8f033e6f7861ed1b126552e41ba3e31

```js
(function() {
  'use strict';

  // ...your code here...
})()
```

<<<<<<< HEAD
## همیشه از "use strict" استفاده کنید

ما همچنان باید به آموختن تفاوت‌های use strict و default mode ادامه دهیم.

در بخش‌های بعدی که با قابلیت‌های زبان جاوا اسکریپت آشنا می‌شویم، به تفاوت‌های بین strict mode و "default" mode اشاره خواهیم کرد و خواهیم دید که use strict چطور زندگی ما را راحت‌تر کرده است.

تا به اینجا کافیست بدانید :


1. عبارت `"use strict"` باعث فعال شدن حالت مدرن موتور جاوا اسکریپت می‌شود و رفتار برخی قابلیت‌های درونی موتور را تغییر می‌دهد.
2. این حالت با قرار دادن رشته `"strict mode"` در ابتدای اسکریپت یا فانکشن فعال می‌شود. برخی قابلیت‌های زبان از جمله "class" ها و "module" ها به صورت خودکار use strict را فعال می‌کنند.
3. Use strict توسط اکثر مرورگرهای مدرن پشتیبانی می‌شود.
4. ما توصیه می‌کنیم تا همیشه از `"use strict"` استفاده کنید. تمام مثال‌های این آموزش‌ها با `"use strict"` فعال انجام می‌شوند (مگر در موارد استثنایی که ذکر خواهند شد).
=======
## Should we "use strict"?

The question may sound obvious, but it's not so.

One could recommend to start scripts with `"use strict"`... But you know what's cool?

Modern JavaScript supports "classes" and "modules" - advanced language structures (we'll surely get to them), that enable `use strict` automatically. So we don't need to add the `"use strict"` directive, if we use them.

**So, for now `"use strict";` is a welcome guest at the top of your scripts. Later, when your code is all in classes and modules, you may omit it.**

As of now, we've got to know about `use strict` in general.

In the next chapters, as we learn language features, we'll see the differences between the strict and old modes. Luckily, there aren't many and they actually make our lives better.

All examples in this tutorial assume strict mode unless (very rarely) specified otherwise.
>>>>>>> cd2c7ce3c8f033e6f7861ed1b126552e41ba3e31
