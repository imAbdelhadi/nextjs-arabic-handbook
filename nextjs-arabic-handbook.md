<div dir="rtl">
السلام عليكم ورحمة الله، أسعد الله صباحكم والمساء أحبتي الكرام.

## مقدمة المترجم

قبيل شهر رمضان الكريم 2021 كتبت على حسابي [بتويتر](https://twitter.com/elh4di) و[لينكدإن](https://www.linkedin.com/in/djafer/) أنني سأبدء نشر سلسلة مترجمة إلى العربية لإطار عمل Next.js التي عرفتها أكثر من سنة من الإستخدام وتطوير المشاريع الرقمية المختلفة. جلعتني أنتقل من بيئة رياكت الكلاسيكية إلى بيئة عمل مساعدة مختصرة للوقت والجهد، لست مضطراً مثلما كنت بالسابق إلى تجهيز بيئة التطوير يدوياً (create-react-app) وتنصيب مئات المكتبات الأخرى عدا مئات الأسطر لتعريف صفحات متداخلة ..إلى آخره من الشفرات المكررة في كل مشروع.

بعدما رأيت فوائدها على إنتاجيتي فكرت في كتابة مقال يتحدث عنها، ثم ما لبثت أن قررت ترجمة كتّيب حولها لتبقى مرجعاً للأمة العربية والإسلامية مثلما عملت مع [مكتبة Alpine.js](https://blog.abdelhadi.org/alpinejs-in-arabic/).

هذا الكتيّب يحوي 120 صفحة بعد ترخيص من كاتبها [فلافيُو كوبس](https://flaviocopes.com/page/nextjs-handbook/). كان قد شرحها مطلع سنة 2019 بنسخة Next.js إصدار 9 القديم. والآن وصل إصدار الإطار العمل إلى النسخة 10+ وقد ألغيت العديد من الخصائص والأدوات. فعمدت إلى تنقيحها وتحديثها من جديد كما عمدت إلى تعريف وشرح مصطلحات إضافية مثل "built-in" مثلا لم يشرحها الكاتب لمعرفتي بعدم توفّرها باللغة العربية.

يحوي الفهرس على 28 درس مختلف، كل درس يشرح ويناقش خصائص ومزايا معيّنة. هدف هذه السلسلة هي أخذ لفّة شاملة وافية حول الإطار ثم بعدها تكمل طريق تعلمك مباشرة من التوثيق للموقع الرسمي للإطار. وبإذن الله ستختصر عليك رحلة تعلّمها بشكل مفيد جداً.

أنوّه إلى من قام بمساعدتي الأخ الفاضل [عاطف بن علي](https://github.com/atefBB) من دولة تونس الشقيقة مبرمج ومطوّر ولديه فصاحة وتدقيق لغوي جيدّ سبق وأن ساعدني على تنقيح ترجمة [توثيق Alpine.js](https://blog.abdelhadi.org/alpinejs-in-arabic) كاملة. قد بدء العمل معي في الصفحات الأولى لهذا الكتيّب ثم لمشاغل لديه لم نكمل وسيعود باذن الله تعالى عن قريب.أسال الله له التوفيق والسلامة والعافية في الدنيا والآخرة.
  
> تحديث: (توفيت والدة عاطف بن علي، أدعوا لها بالرحمة والمغفرة)

### نماذج عربية

قمت ببناء مشاريع عربية كثيرة باستخدام Next.js منها [محرّر دوّن](https://dawin.io/) الذي بينته عبر سلسلة [تحدي بناء محرّر نصوص ماركداون عربي](https://blog.abdelhadi.org/building-in-public-arabic-Markdown-editor/) وهناك نماذج أخرى مثل مشروع [معجمي](https://mujami.alsharekh.org/) التابع لشركة صخر سبق وأن كتبت عنه بـ [مجتمع حسوب](https://io.hsoub.com/webdev/115922-%D8%A3%D8%AF%D8%A7%D8%A9-%D9%85%D8%B9%D8%AC%D9%85%D9%8A-%D8%A7%D9%84%D8%AC%D8%AF%D9%8A%D8%AF%D8%A9-%D9%85%D9%86-%D8%B4%D8%B1%D9%83%D8%A9-%D8%B5%D8%AE%D8%B1-%D8%A8%D9%86%D9%8A%D8%AA-%D8%A8%D8%A7%D8%B3%D8%AA%D8%AE%D8%AF%D8%A7%D9%85-nextjs-%D9%88-tailwind-%D9%88-context-api) وغيره [المعجم المعاصر](https://lexicon.alsharekh.org/).

## الفهرس

1. [المقدّمة.](#p1)
2. [مدخل إلى Next.js](#p2)
3. [الميزات الرئيسة التي تقدّمها Next.js](#p3)
4. [الفرق بين Next.js وGatsby وcreate-react-app](#p4).
5. [تنصيب Next.js](#p5)
6. [معاينة الشفرة المصدرية للتحقق من عمل SSR](#p6)
7. [حُزم التطبيق (The app bundles)](#p7)
8. [إلام يعني الرمز الذي يظهر أسفل يمين الصفحة؟](#p8)
9. [تنصيب إضافة (React DevTools)](#p9)
10. [تقنيات مختلفة يمكنك استعمالها لتنقيح الأخطاء البرمجية (Debugging Techniques)](#p10).
11. [إضافة صفحات ثانية للمشروع](#p11)
12. [ربط صفحتين مع بعض](#p12)
13. [المحتوى التفاعلي (Dynamic content) مع المُوجّه (Router)](#p13)
14. [التحضير المُسبق (Prefetching)](#p14)
15. [استخدام المُوجّه (Router) لتحديد الصفحة النَشِطة (Active Link)](#p15)
16. [استخدام next/router](#p16)
17. [استعلام البيانات عبر getInitialProp](#p17)
18. [التنسيق عبر CSS](#p18)
19. [استخدام وُسوم مخصّصة داخل Head](#p19)
20. [تصميم وتغليف مكوّنات الصفحة (Wrapper Component)](#p20)
21. [استعمال API Route](#p21)
22. [تشغيل التطبيق من جهة المستخدم (Client Side) أو من جهة الخادوم (Server Side)](#p22)
23. [نشر الإصدار النهائي](#p23)
24. [رفع التطبيق على Vercel](#p24)
25. [تحليل حُزم التطبيق (The App Bundles)](#p25)
26. [التحميل البطيء (Lazy loading) للوحدات](#p26)
27. [دليل مسارك القادم](#p27)

## المقدّمة <a id="p1"></a>

العمل بالمكتبات الجديدة مثل React أو أيّ مكتبات ثانية مدعومة بها أمر رائع، لكن تلك المكتبات لا تخلو من المشاكل المتعلّقة بعرض البيانات Rendering والمحتوى من جهة المستخدم.

أولاً، تستغرق الصفحة وقتًا أطول حتى تصبح مرئية للمستخدم، لأنه قبل تحميل المحتوى، يجب تحميل جميع شفرات الجافاسكريبت، ثم يقوم تطبيقك بتشغيل ما سيتم عرضه على الصفحة.

ثانيًا، إذا كنت تقوم بإنشاء موقع ويب مُتاح للجمهور، فستواجه مشكلة في تحسين أرشفة محركات البحث SEO لصفحات موقعك. صحيح أن محركات البحث تشغّل وتقرأ شفرات JavaScript لاستخلاص البيانات منها، ولكن من الأفضل أن نرسل لهم المحتوى بدلاً من السماح لهم بذلك.

الحل لكل من هاتين المشكلتين هو **العرض من جهة الخادوم (Server Rendering)** أو اختصارا **SSR**، ويسمى أيضًا العرض **المسبق الثابت (Static Pre-Rendering)** .

<a id="p2"></a>

[Next.js](https://nextjs.org/) هو واحد من أطر [React](https://nextjs.org/) التي تقوم بكل هذا بطريقة سهلة، ولا يقتصر على هذا فحسب بل لإنشاء تطبيق عليها لا تحتاج إلى أيّ **تكوّين مسبق zero-configuration** وبأمر واحد فقط **single-command toolchain**.

يوفر Next.js بنية مشتركة تسمح لك ببناء تطبيق React لواجهة تطبيقك الأمامية بسهولة، ويتعامل بشفافية مع العرض من جانب الخادوم نيابة عنك.

> **معلومة**: سلسلة الأدوات (tool-chain) تعني مجموعة أدوات تستخدم لأداء مهمّة بناء وتطوير المشاريع البرمجية.

## الميزات الرئيسة التي يقدّمها Next.js <a id="p3"></a>

فيما يلي قائمة غير شاملة لكل ميزات Next.js وسأسرد لك الرئيسة منها:

**1. إعادة التحميل الفوري للتغييرات (Hot Code Reloading):**

يقوم Next.js بإعادة تحميل الصفحة عندما يكتشف أي تغيير محفوظ حديثا.

**2. التوجيه التلقائي (Automatic Routing):**

أي رابط URL يتم تضمينه بنظام الملفات الموضوعة داخل `pages` لا تحتاج إلى أي تعريف أو تكوين.

**3. مكونات فردية (Single File Components):**

باستخدام `styled-jsx` -المتكامل مع Next.js تمامًا، والذي تم إنشاؤه من نفس الفريق- يَسهّل عليك إضافة أنماط محددة لكل مكوّن على حدة.

**4. العرض من جهة الخادوم(SSR أو Server Rendering):**

يمكنك تجهيز المحتوى وعرض المكوّنات قبل إرسال HTML إلى المستخدم.

**توافق النظام البيئي (Ecosystem Compatibility):**

يتوافق Next.js بشكل جيد مع باقي مكتبات وأنظمة JavaScript وNode وReact.

**5. التقسيم التلقائي للشفرة البرمجية (Automatic Code Splitting):**

يتم تحميل الصفحات التي يحتاجها الجافاسكربت فقط، فلا يقوم بتحميل كل شفرات الجافاسكربت في ملف واحد. يتولى Next.js التقسيم broken up تلقائياً لعدة مصادر مختلفة.

يفعل Next.js ذلك من خلال تحليل الوحدات المستوردة resources imported، على سبيل المثال لو قمت باستدعاء مكتبة Axios في صفحة واحدة من صفحات تطبيقك، فلا يتم تحميلها في كل الصفحات الثانية، بل يتم استدعاؤها لتلك الصفحة فقط.

وهذا يضمن أنه يتم تحميل الصفحة الأولى بأسرع ما يمكن، وأن عمليات تحميل الصفحة القادمة ستنفذ جافا سكريبت المطلوبة منها إلى المستخدم.

هناك استثناء واحد ملحوظ: في كثير من الأحيان يتم استخدام `imports` بشكل متكرر في حزمة JavaScript الرئيسة، إذا تم استخدامها بكثرة ستستدعى في نصف صفحات الموقع على الأقل.

**6. التحضير المُسبق (Prefetching):**

في الربط بين المكوّنات بـ `Link` -التي تستخدم لربط الصفحات ببعضها- تدعم التحضير المسبق prefetch الذي يقوم تلقائياً بإعداد موارد الصفحة مسبقاً بما في ذلك تضمين الشفرة المفقودة بسبب التقسيم التلقائي للشفرة البرمجية .

**7. المحتوى التفاعلي (Dynamic content):**

يمكنك استيراد وحدات الجافاسكربت ومكونات React ديناميكيًا.

**8. التصدير الساكن -الثابت- (Static Exports):**

باستخدام الأمر `next export`، يتيح لك Next.js تصدير موقع ثابت بالكامل من تطبيقك.

**9. دعم TypeScript**

تمت كتابة Next.js بلغة TypeScript وبهذا يأتي مع دعم TypeScript ممتاز.

## الفرق بين Next.js وGatsby وcreate-react-app <a id="p4"></a>

Next.js و[Gatsby](https://www.gatsbyjs.com/)، هما أداتان قويتان يمكننا استخدامها لبناء مشاريعنا، والقاسم المشترك بينهما أنهما تعملان تحت غطاء React. ويأتيان مجردان من مكتبة webpack وكل تلك الأدوات low-level التي كنا نجهّزها يدوياً في السابق.

`create-react-app` لا يساعدك في إنشاء تطبيق يتم عرضه من جانب الخادوم بسهولة. يتم توفير خصائص مثل: تحسين محركات البحث، السرعة ..إلخ، بواسطة أدوات مثل Next.js وGatsby.

**متى يكون Next.js أفضل من Gatsby؟**

يمكن لكليهما المساعدة **في العرض من جانب الخادوم SSR**، ولكن بطريقتين مختلفتين.

النتيجة النهائية لـGatsby هي مولد موقع ساكن/ثابت، دون خادوم. تقوم بإنشاء الموقع، ثم نشر تطبيقك بشكل ثابت على Netlify أو موقع استضافة تشابهها.

يوفر Next.js واجهة خلفية Back-end يمكنها من جانب الخادوم عمل SSR، مما يسمح لك بإنشاء موقع ويب تفاعلي، مما يعني أنك ستنشره على نظام أساسي يمكنه تشغيل Node.js.

يمكن لـ Next.js إنشاء موقع ثابت أيضًا، لكنني لا أفضّل ذلك وأستخدم Gatsby بدلا عنها.

إذا كان هدفي هو إنشاء موقع ثابت، فسأواجه صعوبة في الاختيار وربما يمتلك Gatsby نظامًا بيئيًا أفضل من المكونات الإضافية الجاهزة، بما في ذلك العديد من المدوّنات على وجه الخصوص.

يعتمد Gatsby أيضًا بشكل كبير على [GraphQL](https://graphql.org/)، وهو شيء قد تحبه أو [تكرهه](https://graphql.org/) اعتمادًا على آرائك واحتياجاتك.

## تنصيب Next.js <a id="p5"></a>

لتثبيت Next.js، يجب تثبيت Node.js.

تأكد من أن لديك أحدث إصدار من Node. تحقق من تنفيذ هذا الأمر `node -v` على جهازك، وقارنه بأحدث إصدار LTS مدرج في [https://nodejs.org/](https://nodejs.org/) .

بعد تثبيت Node.js، ستكون أوامر `npm` متاحة في سطر الأوامر Terminal.

يمكننا اختيار مسارين الآن: استخدام `create-next-app` أو الأسلوب التقليدي الذي يتضمن تثبيت وإعداد تطبيق Next يدويًا.

### باستخدام create-next-app

إذا كنت معتادًا على ذلك [`create-react-app`](https://nextjs.org/docs/api-reference/create-next-app), `create-next-app`فهذا هو الشيء نفسه -باستثناء أنه ينشئ تطبيق Next بدلاً من تطبيق React، كما يوحي الاسم.

أفترض أنك قمت بتثبيت Node.js سلفا، والذي يأتي مع الأمر [npx](https://docs.npmjs.com/cli/v7/commands/npx) بداية من الإصدار 5.2 مثلاً منذ أكثر من عامين في وقت كتابة هذا الكتيّب. تتيح لنا هذه الأداة المفيدة تنزيل أمر JavaScript وتنفيذه، وسنستخدمه على النحو التالي:

<div dir="ltr">

```bash
npx create-next-app
```
</div>

يطلب الأمر: اسم التطبيق وينشئ مجلدًا جديدًا لك بهذا الاسم نفسه، ثم يقوم بتنزيل جميع الحزم التي يحتاجها `react`, `react-dom`, `next` ، مجمّعة في ملف `package.json` كما توضحه الصورة التالية:

![20210407-18-15v95qx](https://i.suar.me/1X37G/l)

يمكنك تشغيل المشروع عن طريق اﻷمر `npm run dev`:

![image](https://i.suar.me/q281x/l)

وإليك النتيجة على [http: //localhost:3000](http://localhost:3000/) :

![20210407-18-17mz39x](https://i.suar.me/N40Y0/l)

هذه هي الطريقة المُوصى بها لبدء تطبيق Next.js، لأنها تمنحك هيكلًا ونموذجًا للتعليمات البرمجية الجاهزة. هناك أكثر من مجرد نموذج تطبيق افتراضي؛ يمكنك استخدام أي من الأمثلة المخزنة على [https://github.com/zeit/next.js/tree/canary/examples](https://github.com/zeit/next.js/tree/canary/examples) باستخدام الخيار<span dir ="ltr"> `--example` </span>. على سبيل المثال جرب:

<div dir="ltr">

```bash
npx create-next-app --example blog-starter
```
</div>

مما يمنحك نسخة افتراضية لمدونة جاهزة قابلة للاستخدام على الفور مع معاينة بالألوان أيضا syntax highlighting:

![20210407-18-upfd29](https://i.suar.me/dXGOz/l)

### إنشاء تطبيق Next.js يدويًا

يمكنك تجنب طريقة `create-next-app` إذا كنت ترغب في إنشاء تطبيق Next من البداية. وإليك الفكرة:

قم بإنشاء مجلد فارغ في أي مكان تريد على جهازك، على سبيل المثال في المجلد الرئيس الخاص بك، انتقل إليه عبر كتابة اﻷوامر التالية:

<div dir="ltr">

```bash
mkdir nextjs
cd nextjs
```
</div>

وأنشئ أول مجلّد لمشروعك:

<div dir="ltr">

```bash
mkdir firstproject
cd firstproject
```
</div>

الآن استخدم `npm` لتهيئة مشروع Node:

<div dir="ltr">

```bash
npm init -y
```
</div>


يشير الخيار<span dir ="ltr"> `-y` </span>لـ `npm` لاستخدام الإعدادات الافتراضية لمشروع ما، وملء نموذج `package.json` للملف.

![20210407-18-1g9hbcp](https://i.suar.me/8LZeE/l)

الآن قم بتثبيت Next وReact:

<div dir="ltr">

```bash
npm install next react react-dom
```
</div>

يجب أن يحتوي مجلد مشروعك الآن على ملفين:

**الأول:**

- `package.json` [تصفّح الدليل التوثيقي للحزم](https://docs.npmjs.com/cli/v7/configuring-npm/package-json/)
- `package-lock.json` [تصفّح الدليل التوثيقي حول قفل الحزمة](https://docs.npmjs.com/cli/v7/configuring-npm/package-lock-json)

**الثاني:**

- مجلد `node_modules`.

افتح مجلد المشروع باستخدام المحرر المفضل لديك. المحرر المفضل لدي هو [Vscode](https://code.visualstudio.com/). إذا كان برنامج vscode مثبتًا على جهازك، فيمكنك الأمر<span dir="ltr"> `code .` </span> في الطرفية من فتح المجلد الحالي في المحرر إذا كان الأمر لا يعمل، فراجع [هذا](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line).

ملف `package.json` يحتوي الآن على هذا المحتوى:

<div dir="ltr">

```json
{
  "name": "firstproject",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "next": "^10.1.1",
    "react": "^16.11.0",
    "react-dom": "^16.11.0"
  }
}
```
</div>

واستبدل جزء `scripts` بـ:

<div dir="ltr">

```json
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start"
}
```
</div>

لإضافة أوامر بناء وتصدير مشروعنا على Next.js، التي سنستخدمها قريبًا.

**نصيحة:** استخدم `"dev": "next -p 3001"`، لتغيير منفذ التشغيل، في هذا المثال، على المنفذ 3001.

![20210407-18-1jn8xh4](https://i.suar.me/mJ1zG/l)

الآن قم بإنشاء مجلد `pages` وإضافة ملف `index.js`.

في هذا الملف، لننشئ مكوّن React الأول. سنقوم بتصديره افتراضيا:

<div dir="ltr">

```js
const Index = () => (
  <div>
    <h1>Home page</h1>
  </div>
);

export default Index;
```
</div>

الآن باستخدام الطرفية Terminal، قم بتشغيل `npm run dev` لبدء خادوم التطوير Next.

سيتم تشغيل المشروع على منفذ 3000، على المضيف المحلي localhost.

![20210407-18-nl5tv9](https://i.suar.me/BZ10N/l)

افتح [http://localhost:3000](http://localhost:3000/) في متصفحك لرؤيته.

![20210407-18-1siohrc](https://i.suar.me/veMyw/l)

## معاينة الشفرة المصدرية للتحقق من عمل SSR <a id="p6"></a>

دعنا نتحقق من أن التطبيق يعمل، يمكن ملاحظة قوة Next.js عند استخدامها، حيث يقوم بعرض الصفحات من جانب الخادوم ويتم تسليم الـHTML إلى المتصفّح، والذي له ثلاث فوائد رئيسة:

- لا يحتاج متصفّح المستخدم إلى عرض React مما سيجعل التطبيق سريعاً.
- ستقوم محركات البحث بفهرسة الصفحات دون الحاجة إلى تشغيل JavaScript من جانب المستخدم. بدأت محركات Google بحلّ هذه المشكلة، ولكن اعترفت لاحقاً بأنها عملية بطيئة وتأخر الأرشفة كما يجب عليك بصفتك منشئا للتطبيق مساعدة Google قدر الإمكان، إذا كنت ترغب في الحصول على ترتيب بحث جيد.
- يمكنك الحصول على معاينات وصفية meta tags لمعلومات تطبيقك على مواقع التواصل الاجتماعي وتخصيص العنوان والوصف لأي من صفحاتك المشتركة على Facebook وTwitter وما إلى ذلك.

دعونا نلقي نظرة على مصدر التطبيق. باستخدام Chrome، يمكنك النقر بزر الفأرة الأيمن في أي مكان في الصفحة ، والضغط على "**عرض مصدر الصفحة"**.

![](https://i.suar.me/AAJeB/)

إذا قمت بعرض مصدر الصفحة ، فسترى `<div><h1>Home page</h1></div>` المقتطف في وسم HTML `body`، جنبًا إلى جنب مع مجموعة من ملفات JavaScript -حزم التطبيقات-.

لا نحتاج إلى إعدادات أخرى، فالعرض من جانب الخادوم SSR يعمل بالفعل.

سيتم تشغيل تطبيق React على متصفّح المستخدم، وسيكون هو أحد التفاعلات مثل النقر فوق الروابط. لكن إعادة تحميل الصفحة ستؤدي إلى إعادة تحميلها من جانب الخادوم. وباستخدام Next.js، يجب ألا يكون هناك اختلاف في النتيجة داخل المتصفح - يجب أن تبدو الصفحة التي يعرضها الخادوم تمامًا مثل الصفحة التي يعرضها المستخدم.

## حُزم التطبيق (The app bundles) <a id="p7"></a>

عندما استعرضنا مصدر الصفحة، رأينا مجموعة من ملفات الجافاسكربت تم تضمينها:

![](https://i.suar.me/vqadw/)

سنضع الشفرة المصدرية في [مُنسق HTML](https://htmlformatter.com/) لإظهاره بشكل أفضل، حتى نتمكن من فهمه:

<div dir="ltr">

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta
      name="viewport"
      content="width=device-width,minimum-scale=1,initial-scale=1"
    />
    <meta name="next-head-count" content="2" />
    <link
      rel="preload"
      href="/_next/static/development/pages/index.js?ts=1572863116051"
      as="script"
    />
    <link
      rel="preload"
      href="/_next/static/development/pages/_app.js?ts=1572863116051"
      as="script"
    />
    <link
      rel="preload"
      href="/_next/static/runtime/webpack.js?ts=1572863116051"
      as="script"
    />
    <link
      rel="preload"
      href="/_next/static/runtime/main.js?ts=1572863116051"
      as="script"
    />
  </head>

  <body>
    <div id="__next">
      <div>
        <h1>Home page</h1>
      </div>
    </div>
    <script src="/_next/static/development/dll/dll_01ec57fc9b90d43b98a8.js?ts=1572863116051"></script>
    <script id="__NEXT_DATA__" type="application/json">
      {
        "dataManager": "[]",
        "props": { "pageProps": {} },
        "page": "/",
        "query": {},
        "buildId": "development",
        "nextExport": true,
        "autoExport": true
      }
    </script>
    <script
      async=""
      data-next-page="/"
      src="/_next/static/development/pages/index.js?ts=1572863116051"
    ></script>
    <script
      async=""
      data-next-page="/_app"
      src="/_next/static/development/pages/_app.js?ts=1572863116051"
    ></script>
    <script
      src="/_next/static/runtime/webpack.js?ts=1572863116051"
      async=""
    ></script>
    <script
      src="/_next/static/runtime/main.js?ts=1572863116051"
      async=""
    ></script>
  </body>
</html>
```
</div>

لدينا 4 ملفات جافاسكريبت تم تحميلها مسبقا (preloaded) في `head`، باستخدام `rel="preload" as="script"`:

- <span dir="ltr"> `/_next/static/development/pages/index.js` 96 LOC </span>
- <span dir="ltr"> `/_next/static/development/pages/_app.js` 5900 LOC </span>
- <span dir="ltr"> `/_next/static/runtime/webpack.js` 939 LOC </span>
- <span dir="ltr"> `/_next/static/runtime/main.js` 12k LOC </span>

هذا يعني أن المتصفّح سيقوم بتحميل الملفات (load) في أقرب وقت ممكن قبل أن يتم عمل تدفق للبيانات. دون ذلك، سيتم تحميل ملفات الجافاسكربت مع تأخير إضافي، وهذا يحسّن أداء تحميل الصفحة.

ثم يتم تحميل هذه الملفات الأربعة في نهاية وسم `body`، جنبًا إلى جنب مع:

- <span dir ="ltr"> `/_next/static/development/dll/dll_01ec57fc9b90d43b98a8.js` </span>

ومقتطف JSON الذي يعيّن بعض الإعدادات الافتراضية لبيانات الصفحة:

<div dir="ltr">

```js
<script id="__NEXT_DATA__" type="application/json">
{
  "dataManager": "[]",
  "props": {
    "pageProps":  {}
  },
  "page": "/",
  "query": {},
  "buildId": "development",
  "nextExport": true,
  "autoExport": true
}
</script>
```
</div>

تقوم ملفات الحزم الأربعة التي تم تحميلها بتنفيذ ميزة واحدة تسمى **تقسيم الشفرة البرمجية**. و `index.js` يوفر ملف التعليمات البرمجية اللازمة لصفحة `index` الرئيسة، وإذا كانت لدينا المزيد من الصفحات سيكون لدينا المزيد من الحزم لكل صفحة، والتي ستقوم بتحميلها فقط إذا لزم الأمر واستعرض المستخدم تلك الصفحة -لتوفير وقت تحميل أسرع-

## إلام يعني الرمز الذي يظهر أسفل يمين الصفحة؟ <a id="p8"></a>

هل رأيت هذا الرمز الصغير في أسفل يمين الصفحة ، والذي يشبه البرق؟

![](https://i.suar.me/r214J/)

إذا قمت بتمرير الفأرة فوقها، فستظهر صفحة "معروضة مسبقًا (Prerendered Page)":

![](https://i.suar.me/xNEnr/)

يخبرك هذا الرمز، الذي يظهر فقط في وضع التطوير (development mode)، أن الصفحة مؤهلة للتحسين التلقائي الثابت، مما يعني بشكل أساسي أنها لا تعتمد على البيانات التي يتم جلبها في وقت الاستدعاء، ويمكن عرضها مسبقًا وبناء ملف HTML ثابت في وقت البناء عند تشغيل `npm run build`.

ويمكن تحديد هذا من خلال عدم وجود<span dir ="ltr"> `getInitialProps()` </span>&nbsp;المرفقة داخل مكوّن الصفحة.

في هذه الحالة، يمكن أن تكون صفحتنا أسرع لأنها ستُقدم ملف HTML ثابت بدلاً من المرور عبر خادوم Node.js الذي يولّد ملفات HTML.

وأحيانا قد يظهر مثلث صغير كأيقونة، أو الصفحات غير معروضة مسبقًا (non-prerendered pages) وتعني مؤشّر تجميع ويظهر عند حفظ الصفحة. يقوم Next.js عند الحفظ بالتحميل الفوري للتغييرات لإعادة تحميل الشفرة المضافة حديثاً في التطبيق تلقائيًا.

إنها طريقة رائعة حقًا لتحديد ما إذا كان التطبيق قد تم تجميعه بالفعل ويمكنك اختبار الجزء الذي تعمل عليه.

## تنصيب إضافة React DevTools <a id="p9"></a>

يعتمد Next.js على React، لذا فإن إحدى الأدوات المفيدة للغاية التي نحتاج إلى تثبيتها إذا لم تكن قد قمت بذلك هي أدوات React Developer.

تعد أدوات React Developer، المتوفرة لكل من [Chrome](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en) و [Firefox](https://addons.mozilla.org/en-US/firefox/addon/react-devtools/)، أداة أساسية يمكنك استخدامها لفحص تطبيق React.

الآن، أدوات تطوير React ليست خاصة بـ Next.js فحسب، لكنني أريد توضيحها لأنك قد لا تكون على دراية كاملة بجميع الأدوات التي توفرها React.

إنها توفر المعاين (Inspector) يكشف عن شجرة مكونات React التي تبني صفحتك، ولكل مكوّن يمكنك الانتقال والتحقق من الخاصيات Props والحالة State والخطافات Hooks وغير ذلك الكثير.

وبمجرد الانتهاء من تثبيت React DevTools، يمكنك فتح الإضافة من متصفحك بمتصفّح Chrome، بزر الفأرة الأيمن على الصفحة، انقر فوق `Inspect` وستجد نافذتين جديدتين: **المكونات (Components)** و **صفحة المحلّل (Profiler)** .

![](https://i.suar.me/zxBn4/)

إذا قمت بالنقر على نافذة المكونات، فسترى أنه في سيحدد المستعرض الأجزاء التي يتم تقديمها بواسطة هذا المكون.

ثم إذا حددت أي مكوّن في الشجرة، فستظهر لك لوحة اليمين مرجعًا **للمكوِّن الأصلي**، والخصائص الممرّرة إليه:

![](https://i.suar.me/ZjY2z/)

يمكنك التنقل بسهولة من خلال الضغط على أسماء المكوّنات.

وكذلك يمكنك النقر فوق رمز العين في شريط أدوات Developer Tools لفحص عنصر DOM. كما يمكنك استخدام رمز `bug` لتسجيل بيانات المكوّن في وحدة التحكم.

![](https://i.suar.me/GAWOd/)

هذا رائع جدًا لأنه بمجرد طباعة البيانات هناك، يمكنك النقر بزر الفأرة الأيمن فوق أي عنصر والضغط على "تخزين كمتغير عام". على سبيل المثال، قمت باستخدام خاصية `url`، وتمكّنت من فحصها في وحدة التحكم باستخدام المتغير المؤقت المخصص لها `temp1`:

![](https://i.suar.me/yxBnZ/)

باستخدام **خرائط المصدر (Source Maps)**، التي يتم تحميلها بواسطة Next.js تلقائيًا في وضع التطوير، من لوحة المكونات، يمكننا النقر فوق الرمز `<>` وسيتحول DevTools إلى لوحة المصدر (Source panel)، مع عرض الشفرة المصدرية للمكوّن:

![](https://i.suar.me/KEN36/)

تعد نافذة **المحلّل** أكثر روعة، يسمح لنا **بتسجيل التفاعلات** في التطبيق ومعرفة ما سيحدث. لا يمكنني عرض مثال الآن، لأنه يحتاج إلى مكونين على الأقل لإنشاء تفاعل، ولدينا عنصر واحد فقط الآن. سأتحدث عن هذا لاحقًا.

![img](https://i.suar.me/VPe6J/)

لقد عرضت جميع لقطات الشاشة لمتصفّح Chrome، لكن أدوات React Developer تعمل بنفس الطريقة في Firefox:

![img](https://i.suar.me/9XEe3/)

## تقنيات مختلفة يمكنك استعمالها لتنقيح الأخطاء البرمجية (Debugging Techniques) <a id="p10"></a>

بالإضافة إلى أدوات المطورين لـ React، والتي تعتبر ضرورية لبناء تطبيق Next.js، أودّ التأكيد على طريقتين لتصحيح أخطاء تطبيقات Next.js.

الأولى هي <span dir ="ltr">`console.log()`</span> وجميع أدوات [Console API](https://flaviocopes.com/console-api/). الطريقة التي تعمل بها تطبيقات Next ستجعل بيان السجل يعمل في وحدة تحكم المتصفح أو في الطرفية حيث بدأت باستخدام `npm run dev`.

على وجه الخصوص، إذا تم تحميل الصفحة من الخادوم، عندما توجه عنوان URL إليها، أو تضغط على زر التحديث / CMD / ctrl-R ، فإن أي تسجيل لوحدة التحكم يحدث في الجهاز.

أداة أخرى ضرورية هي دالة `debugger`. ستؤدي إضافة هذه العبارة إلى أحد المكونات إلى إيقاف عرض المتصفح للصفحة مؤقتًا:

![img](https://i.suar.me/6jaa5/)

رائعة حقًا لأنه يمكنك الآن استخدام مصحح أخطاء المتصفح لفحص القِيم وتشغيل تطبيقك سطرًا بسطر واحد في كل مرة.

يمكنك أيضًا استخدام المصحح في برنامج Vscode لتصحيح أخطاء التعليمات البرمجية من جانب الخادوم. [هذه مقاطع تعليمية](https://github.com/Microsoft/vscode-recipes/tree/master/Next-js) تشرح الأمر.

## إضافة صفحات ثانية للمشروع <a id="p11"></a>

الآن بعد أن أصبح لدينا فهم جيد للأدوات التي يمكننا استخدامها لمساعدتنا في تطوير تطبيقات Next.js، دعنا نواصل من حيث توقفنا بتطبيقنا الأول:

![img](https://i.suar.me/YjWaX/)

عندما أريد إضافة صفحة ثانية لتطبيقنا، مثلا صفحة عرض التدوينات <span dir ="ltr">`/blog`</span>، وفي الوقت الحالي سننشئ صفحة ثابتة بسيطة داخل مجلد `pages`، تمامًا مثل المكون الأول لدينا `index.js`:

![20210415-18-17461ob](https://i.suar.me/zxB6v/l)

بعد حفظ الملف الجديد، ننفّذ الأمر `npm run dev` ، إذا قمت بتشغيله سابقاً فلا حاجة لإعادة تشغيله.

![20210415-19-tc5irm](https://i.suar.me/ZjY1M/)

لاحظ ما أخبرتنا به الطرفية (Terminal):

![img](https://i.suar.me/GAW99/)

رابط الصفحة <span dir ="ltr">`/blog`</span> يعتمد على اسم الملف، و تموضعه داخل مجلد `pages`.

يمكنك إنشاء صفحة `pages/hey/ho`، وستظهر تلك الصفحة على شكل عنوان [http://localhost:3000/hey/ho](http://localhost:3000/hey/ho) .

حاول تصفح الصفحة الجديد وعرض مصدرها، عند تحميلها من الخادوم، سيتم إدراج الحزمة <span dir ="ltr"> `/_next/static/development/pages/blog.js`</span> كواحدة من الحزم المحملة، ولن تجد <span dir ="ltr">`/_next/static/development/pages/index.js`</span> كما هو الحال في الصفحة الرئيسة. هذا لأنه بفضل التقسيم التلقائي للشفرة البرمجية، لا نحتاج إلى الحزمة التي تخدم الصفحة الرئيسة. فقط الحزمة التي تخدم صفحة المدونة.

![img](https://i.suar.me/yxBQ7/)

يمكننا أيضًا تصدير وظيفة مجهولة الاسم من `blog.js`:

<div dir="ltr">

```js
export default () => (
  <div>
    <h1>Blog</h1>
  </div>
);
```
</div>

أو إذا كنت تفضل صيغة الوظيفة العادية:

<div dir="ltr">

```js
export default function () {
  return (
    <div>
      <h1>Blog</h1>
    </div>
  );
}
```
</div>

## ربط صفحتين مع بعض <a id="p12"></a>

إحدى مميزات Next.js تمكنك من ربط الصفحات مع بعضها البعض بحيث تكون أسهل وسريعة للغاية.

لو نستعمل الطريقة القديمة بالاسناد عبر `a tags` وتفحّصنا إضافة DevTool وفعّلنا زر PreserLog نجد أنه قام بتحميل جميع الحزم ولكن نحن لسنا بحاجة لجميع هذه، سنحتاج فقط إلى حزمة `blog.js`، لإصلاح هذه المشكلة سنستعمل مكتبة توفّرها Next تدعى Link.

نقوم باستيرادها:

<div dir="ltr">

```js
import Link from "next/link";
```
</div>

ثم نستخدمها بتضمين `a tags`، مثل هذه:

<div dir="ltr">

```js
import Link from "next/link";

const Index = () => (
  <div>
    <h1>Home page</h1>
    <Link href="/blog">
      <a>Blog</a>
    </Link>
  </div>
);

export default Index;
```
</div>

الآن إذا أعدنا محاولة فحص الصفحة مثلما فعلنا سابقًا، فستتمكن من رؤية أن صفحة `blog.js` يتم تحميل الحزمة الخاصة بها فقط:

![img](https://i.suar.me/EArYr/)

تم تحميل الصفحة بشكل أسرع، حتى أن أيقونة التحميل بأعلى صفحة التبويب لن تظهر.

ماذا لو ضغطت الآن على زر العودة؟ لن يتم تحميل أي شيء، لأن المتصفح لا يزال يحتوي على الحزمة القديمة `index.js`، وجاهزة لتحميل صفحة <span dir ="ltr">`/index`</span>. كل شيء تلقائي!

## المحتوى التفاعلي (Dynamic content) مع المُوجّه (Router )<a id="p13"></a>

رأينا في الفصل السابق كيفية ربط الصفحة الرئيسة بصفحة المدونة. والآن لو أردنا عرض روابط التدوينات بشكل ديناميكي. على سبيل المثال، قد تكون تدوينة بعنوان "Hello World" ورابطها <span dir ="ltr">`/blog/hello-world`</span>. وقد تكون تدوينة ثانية بعنوان "مشاركتي الثانية" <span dir ="ltr">`/blog/my-second-post`</span>.

يمكن لـ Next.js تقديم محتوى ديناميكي بناءً على **الروابط الديناميكية (dynamic URL)** .

نقوم بإنشاء رابط ديناميكي عن طريق إنشاء صفحة ديناميكية مع `[]`.

كيف؟ سنضيف ملف `pages/blog/[id].js`. وهذا الملف يتعامل مع كل الروابط الديناميكية تحت الرابط `/blog/`، مثل تلك التي أشرنا إليها أعلاه: <span dir ="ltr">`/blog/hello-world`</span> إلى آخره.

في اسم الملف، نضع المعرّف `[id]` داخل الأقواس المربعة وتعني أن أي شيء ديناميكي متغيّر سيتم وضعه داخل المعرّف `id` معلمة **لخاصية الاستعلام (query property)** الخاصة **بالمُوجّه (Router)** .

حسنًا، قد تحدثت عن أشياء كثيرة في وقت واحد.

ماذا أقصد **بالمُوجّه (Router)**؟

الموجه عبارة عن مكتبة مقدمة من Next.js. نستوردها من `next/router`:

<div dir="ltr">

```js
import { useRouter } from "next/router";
```
</div>

وبمجرد الانتهاء من ذلك نعرّف `useRouter`، بإنشاء مثيل لكائن الموجّه باستخدام:

<div dir="ltr">

```js
const router = useRouter();
```
</div>

بمجرد أن نعرّف كائن الموجّه هذا، يمكننا استخراج المعلومات منه.

على وجه المثال، يمكننا الحصول على الجزء الديناميكي من عنوان URL في ملف `[id].js` عن طريق الوصول إليه عبر `router.query.id`.

يمكن أن يكون الجزء الديناميكي أيضًا مجرد جزء من عنوان URL، مثل `post-[id].js`.

لذلك دعونا نستمر ونطبق كل هذه الأشياء عمليًا.

قم بإنشاء الملف على مسار `pages/blog/[id].js`

<div dir="ltr">

```js
import { useRouter } from "next/router";

export default () => {
  const router = useRouter();

  return (
    <>
      <h1>Blog post</h1>
      <p>Post id: {router.query.id}</p>
    </>
  );
};
```
</div>

الآن إذا تصفّحت الرابط `http://localhost:3000/blog/test` ، سترى هذه:

![img](https://i.suar.me/2je13/)

يمكننا استخدام المعرّف `id` لجلب تدوينة معيّنة من قائمة التدوينات بقاعدة البيانات، لتبسيط الأمور على سبيل المثال، سنضيف ملف `posts.json ` في المجلد الرئيسي للمشروع:

<div dir="ltr">

```json
{
  "test": {
    "title": "test post",
    "content": "Hey some post content"
  },
  "second": {
    "title": "second post",
    "content": "Hey this is the second post content"
  }
}
```
</div>

الآن يمكننا استيراده والبحث عن التدوينة من المعرّف `id`:

<div dir="ltr">

```js
import { useRouter } from "next/router";
import posts from "../../posts.json";

export default () => {
  const router = useRouter();

  const post = posts[router.query.id];

  return (
    <>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </>
  );
};
```
</div>

عند إعادة تحميل الصفحة المفروض ستظهر لنا هذه:

![img](https://i.suar.me/yxq82/)

لكنها ليست كذلك! بل حصلنا على خطأ في وحدة التحكم وخطأ في المتصفح أيضًا:

![img](https://i.suar.me/Q9x4p/)

لماذا؟ لأنه أثناء العرض، وعندما تتم تهيئة المكون، لم تجهّز البيانات بعد. سنرى كيفية توفير البيانات للمكون باستخدام `getInitialProps` في الدرس التالي.

في الوقت الحالي، أضف القليل من التحقق <span dir ="ltr">`if (!post) return <p></p>`</span> قبل إرجاع JSX:

<div dir="ltr">

```js
import { useRouter } from "next/router";
import posts from "../../posts.json";

export default () => {
  const router = useRouter();

  const post = posts[router.query.id];
  if (!post) return <p></p>;

  return (
    <>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </>
  );
};
```
</div>

الآن يجب أن تعمل الصفحة بشكل عادي. في البداية يتم تقديم المكون بدون إستعلام عن البيانات `router.query.id`. وبعد التقديم، يقوم Next.js بتشغيل تحديث بقيمة الاستعلام وتعرض الصفحة المعلومات الصحيحة.

وإذا عرضت المصدر، ستجد هذه العلامة الفارغة `<p>` في HTML:

![img](https://i.suar.me/pyzaA/)

سنقوم قريبًا بإصلاح هذه المشكلة التي تفشل في تنفيذ SSR وهذا يؤخر أوقات التحميل لمستخدمينا وتحسين محركات البحث كما تحدثنا سابقاً.

يمكننا إكمال مثال المدونة بإدراج تلك التدوينات في `pages/blog.js`:


<div dir="ltr">

```js
import posts from "../posts.json";

const Blog = () => (
  <div>
    <h1>Blog</h1>

    <ul>
      {Object.entries(posts).map((value, index) => {
        return <li key={index}>{value[1].title}</li>;
      })}
    </ul>
  </div>
);

export default Blog;
```
</div>

ويمكننا ربطهم بصفحات التدوينات فرادى، عن طريق إستيراد مكتبة `Link` منها `next/link` واستخدامها داخل حلقة التدوينات:

<div dir="ltr">

```js
import Link from "next/link";
import posts from "../posts.json";

const Blog = () => (
  <div>
    <h1>Blog</h1>

    <ul>
      {Object.entries(posts).map((value, index) => {
        return (
          <li key={index}>
            <Link href="/blog/[id]" as={"/blog/" + value[0]}>
              <a>{value[1].title}</a>
            </Link>
          </li>
        );
      })}
    </ul>
  </div>
);

export default Blog;
```
</div>

## التحضير المُسبق Prefetching<a id="p15"></a>

تحدثنا سابقاً عن `Link` أنها تربط الصفحات فيما بينها، وعندما تستخدمه، **يتعامل** Next.js **بشفافية مع توجيه صفحات العرض** لنا، لذلك عندما ينقر المستخدم على الرابط، تهتم الواجهة الأمامية بإظهار جديد الصفحة دون تشغيل طلب بين العميل والخادوم ودورة استجابة جديدة، كما يحدث عادةً مع صفحات الويب.

هناك شيء آخر يقدمه لك Next.js عندما تستخدم `Link`.

بمجرد ظهور عنصر مضمّن بداخله `<Link>` في العرض "viewport" (مما يعني أنه مرئي لمستخدم الموقع)، يقوم Next.js بإعداد عنوان URL الذي يشير إليه مسبقًا، طالما أنه رابط محلي (على موقع الويب الخاص بك)، مما يجعل التطبيق سريعًا للغاية للمشاهد.

يتم تشغيل هذا الأسلوب فقط في **وضع النشر أو الإنتاج (Production Mode)** (سنتحدث عن هذا بالتفصيل لاحقًا)، يعني أنه يجب عليك إيقاف التطبيق إذا كنت تقوم بتشغيله `npm run dev`، وتجميع حزمة الإنتاج الخاصة بك `npm run build` وتشغيلها `npm run start`.

باستخدام فاحص الشبكة (Network inspector) في DevTools، ستلاحظ أن جميع الروابط الموجودة في الجزء المرئي من الصفحة عند تحميلها ستبدأ في التحضير المُسبق فورًا بعد تشغيل حدث `load` على صفحتك (يتم تشغيله عند تحميل الصفحة بالكامل، ويحدث بعد `DOMContentLoaded`)

سيتم تحضير أي علامة `Link` أخرى غير موجودة في العرض مسبقًا عندما يقوم المستخدم بالتمرير.

يتم التحضير المسبق تلقائيًا في الاتصالات عالية السرعة (اتصالات Wifi و 3g +، ما لم يرسل المتصفح استعلام [`Save-Data` ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Save-Data) مع HTTP Header.

يمكنك إلغاء التحضير المسبق لروابط مخصّصة في `Link` عن طريق تعيين الخاصية `prefetch` كـ `false`:

<div dir="ltr">

```jsx
<Link href="/a-link" prefetch={false}>
  <a>A link</a>
</Link>
```
</div>

## استخدام المُوجّه Router لتحديد الصفحة النَشِطة (Active Link)<a id="p16"></a>

تتمثل إحدى الميزات المهمة جدًا عند العمل مع `Link` في تحديد عنوان رابط الصفحة النشطة بحيث يكون مختلفًا عن عناوين URL الأخرى.

هذا مفيد بشكل خاص في إذا أردنا تحديد لون مخصص للنافذة على سبيل المثال.

مكتبة `Link` على Next.js لا تفعل ذلك تلقائيًا. لذلك سننشئ مكوّن خاص بنا ونستدعي كل من مكتبة react و Link من `next/link` و useRouter من `next/router`.

داخل المكون، نحدد ما إذا كان اسم المسار الحالي للصفحة يطابق سمة `href` للمكون، فإن كان الأمر كذلك، سنخبره بإرفاق صنف (class) مثلا "selected".وأخيراً نعيدهم عبر <span dir ="ltr">`React.cloneElement()`</span>.

<div dir="ltr">

```js
import React from "react";
import Link from "next/link";
import { useRouter } from "next/router";

export default ({ href, children }) => {
  const router = useRouter();

  let className = children.props.className || "";
  if (router.pathname === href) {
    className = `${className} selected`;
  }

  return <Link href={href}>{React.cloneElement(children, { className })}</Link>;
};
```
</div>

## استخدام next/router <a id="p17"></a>

لقد رأينا بالفعل كيفية استخدام `Link` لإدارة التوجيه في تطبيقات Next.js. ومن السهل إدارة الموجّه في JSX، ولكن في بعض الأحيان تحتاج إلى إجراء تغيير في التوجيه برمجيًا.

في هذه الحالة، يمكنك الوصول إلى الموجّه Next.js مباشرةً، المتوفر في حزمة `next/router`، واستدعاء <span dir ="ltr">`push()`</span>.

فيما يلي مثال على الوصول إلى الموجّه:

<div dir="ltr">

```js
import { useRouter } from "next/router";

export default () => {
  const router = useRouter();
  //...
};
```
</div>

بعد تعريف كائن الموجّه <span dir ="ltr">`useRouter()`</span> يمكننا إستخدامه الآن.

هذا الموّجه يعمل من جهة المستخدم فقط أو الواجهة الأمامية، أسهل طريقة للتأكد من ذلك هي تضمينه داخل الخطاف <span dir ="ltr">`useEffect()`</span>، أو <span dir ="ltr">`componentDidMount()`</span> في الأسلوب القديم.

من المحتمل أنك تستخدم <span dir ="ltr">`push()`</span> و <span dir ="ltr">`prefetch()`</span> في أغلب الأحيان.

<span dir ="ltr">`push()`</span> تسمح لنا بتغيير الرابط برمجياً.

<div dir="ltr">

```js
router.push("/login");
```
</div>

<span dir ="ltr">`prefetch()`</span> يسمح لنا بالتحضير المسبق للعنوان، وهو مفيد عندما لا يكون لدينا وسم Link tag الذي يتعامل تلقائياً مع prefetching:

<div dir="ltr">

```js
router.prefetch("/login");
```
</div>

مثال كامل:

<div dir="ltr">

```js
import { useRouter } from "next/router";

export default () => {
  const router = useRouter();

  useEffect(() => {
    router.prefetch("/login");
  });
};
```
</div>

يمكنك أيضًا استخدام الموجّه للاستماع إلى [أحداث تغيير المسار ( route change events)](https://nextjs.org/docs#router-events) .

## استعلام البيانات عبر <span dir ="ltr"> getInitialProps() </span> <a id="p18"></a>

في المرة الماضية رأينا كيف استلمنا البيانات من ملف json ولكن ظهرت لنا مشكلة undefined.

<div dir="ltr">

```js
import { useRouter } from "next/router";
import posts from "../../posts.json";

export default () => {
  const router = useRouter();

  const post = posts[router.query.id];

  return (
    <>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </>
  );
};
```
</div>

الخطأ:

![img](https://i.suar.me/qLy3n/)

كيف يمكننا حل هذا؟ وكيف نجعل SSR يعمل بطريقة تلقائية؟

يجب علينا تزويد المكوّن بخصائص (props) باستخدام دالة خاصة تسمى <span dir ="ltr">`getInitialProps()`</span> ترفق بالمكون.

للقيام بذلك، نقوم أولاً بتسمية المكون:

<div dir="ltr">

```js
const Post = () => {  //...}export default Post
```
</div>

ثم نضيف الوظيفة إليها:

<div dir="ltr">

```js
const Post = () => {  //...}Post.getInitialProps = () => {  //...}export default Post
```
</div>

تحصل هذه الدالة على كائن كوسيط لها، والتي تحتوي على العديد من الخصائص. الشيء الذي نهتم به الآن هو أننا نحصل على `query` الكائن، الذي استخدمناه سابقًا للحصول على معرّف التدوينة.

لذلك يمكننا الحصول عليه باستخدام بناء جملة تفكيك البنية (_destructuring_ syntax) :

<div dir="ltr">

```js
Post.getInitialProps = ({ query }) => {  //...}
```
</div>

الآن يمكننا إعادة التدوينة من هذه الوظيفة:

<div dir="ltr">

```js
Post.getInitialProps = ({ query }) => {
  return { post: posts[query.id] };
};
```
</div>

ويمكننا أيضًا إزالة استيراد `useRouter`، ونحصل على التدوينة من خاصية `props` التي تم تمريرها إلى المكوّن `Post`:

<div dir="ltr">

```js
import posts from "../../posts.json";

const Post = (props) => {
  return (
    <div>
      <h1>{props.post.title}</h1>
      <p>{props.post.content}</p>
    </div>
  );
};

Post.getInitialProps = ({ query }) => {
  return {
    post: posts[query.id],
  };
};

export default Post;
```
</div>

الآن لن يكون هناك خطأ، وسيعمل SSR كما هو متوقع، كما ترى عند التحقق من عرض مصدر الصفحة:

![img](https://i.suar.me/OBqyw/)

عندما نستخدم `Link` للانتقال إلى صفحة جديدة، سيتم تنفيذ دالة getInitialProps من جانب الخادوم ومن جانب المستخدم.

من المهم ملاحظة أنه بالإضافة إلى كائن `query`، تحصل دالة `getInitialProps` أيضًا على الخصائص الأخرى التالية:

`pathname`: لـ `path` من الرابط.

`asPath`: تظهر عنوان الرابط الحالي (بما في ذلك الاستعلام) بالمتصفح.

في حالة استدعاء `http://localhost:3000/blog/test`، تكون النتائج كالتالي:

- <span dir ="ltr"> `/blog/[id]` </span>
- <span dir ="ltr"> `/blog/test` </span>

وفي حالة العرض من جانب الخادوم، سيتلقى أيضًا:

- <span dir ="ltr"> `req`: كائن الطلب HTTP. </span>
- <span dir ="ltr"> `res`: كائن الإستجابة HTTP. </span>
- <span dir ="ltr"> `err`: كائن الخطأ. </span>

إذا كنت قد أكملت تعلّم Node.js سابقاً، فستكون req و res مألوفة لك.

## التنسيق عبر CSS <a id="p19"></a>

كيف يمكننا تنسيق المكوّنات في Next.js؟

لدينا الكثير من الحرّية أو المكتبات التي نفضلها. لكن Next.js يأتي مدمجًا بـ [`styled-jsx`](https://github.com/zeit/styled-jsx)، لأن هذه مكتبة أنشأها نفس الأشخاص الذين يعملون على Next.js.

وهي مكتبة رائعة لأنها توفّر لنا صيانة سهلة ولا تؤثّر إلا على المكوّن الذي تم تنسيقه.

أعتقد أن هذا نهج جيد لكتابة CSS دون الحاجة إلى استيراد مكتبات أخرى أو معالجات ثانية تزيدها تعقيداً.

لإضافة CSS إلى مكون React في Next.js، نقوم بتضمينه داخل وسم في JSX، والذي يبدأ بـ:

<div dir="ltr">

```js
<style jsx>{`
```
</div>

وينتهي بـ:

<div dir="ltr">

```js
`}</style>
```
</div>

داخل هذه الشفرة الغريبة، نكتب تنسيق CSS عادي، تمامًا كما نفعل في ملف <span dir ="ltr">`.css`</span> :

<div dir="ltr">

```js
<style jsx>{`
  h1 {
    font-size: 3rem;
  }
`}</style>
```
</div>

فتصير:

<div dir="ltr">

```js
const Index = () => (
  <div>
    <h1>Home page</h1>

    <style jsx>{`
      h1 {
        font-size: 3rem;
      }
    `}</style>
  </div>
);

export default Index;
```
</div>

داخل block، يمكننا استخدام تضمين خصائص داخلها لتغيير القيمة ديناميكيًا. على سبيل المثال، نفترض هنا أن المكون الرئيسي يمرر خاصية `size` ويستخدمه في كتلة `style-jsx`:

<div dir="ltr">

```js
const Index = (props) => (
  <div>
    <h1>Home page</h1>

    <style jsx>{`
      h1 {
        font-size: ${props.size}rem;
      }
    `}</style>
  </div>
);
```
</div>

إذا كنت ترغب في تطبيق بعض تنسيقات CSS كعامة لجميع المكوّنات، فبدلاً من تقييدها أو تكرارها، يمكنك إضافة الكلمة الأساسية `global` إلى `style`:

<div dir="ltr">

```jsx
<style jsx global>{`
  body {
    margin: 0;
  }
`}</style>
```
</div>

إذا كنت تريد استيراد ملف CSS خارجي في مكون Next.js فقم باستدعائها مباشرة:

<div dir="ltr">

```js
import "../style.css";
```
</div>

## استخدام وُسوم مخصّصة داخل Head <a id="p20"></a>

في Next.js يمكنك إضافة وُسوم مخصّصة (head tags) مثل عنوان الصفحة (title) ووصف الصفحة (description) إلى آخره.

كيف يمكنك فعل ذلك؟

داخل كل مكون يمكنك استيراد `Head` الموجود بـ `next/head` وإدراجه في المكون JSX الخاص بك:

<div dir="ltr">

```js
import Head from "next/head";

const House = (props) => (
  <div>
    <Head>
      <title>The page title</title>
    </Head>
    {/* the rest of the JSX */}
  </div>
);

export default House;
```
</div>

يمكنك إضافة أي علامة HTML تريد أن تظهر في قسم الصفحة `<head>`.

عند تثبيت المكون، سيضمن Next.js إضافة العلامات الموجودة في إلى `Head`. نفس الشيء عند إلغاءها، سيهتم Next.js بإزالة تلك العلامات.

## تصميم وتغليف مكوّنات الصفحة (Wrapper Component) <a id="p21"></a>

عند تصميم الصفحة، عادة لدينا مكونات مختلفة مثل `nav` و `sidebar` ..إلى آخره.

فكيف تبني مثل هذا النظام في Next.js؟

هناك طريقتان. أحدهما يستخدم [المكونات ذات الترتيب الأعلى ( Higher Order Component)](https://flaviocopes.com/react-higher-order-components/)، عن طريق إنشاء مكون `components/Layout.js`:

<div dir="ltr">

```js
export default Page => {
  return () => (
    <div>
      <nav>
        <ul>....</ul>
      </hav>
      <main>
        <Page />
      </main>
    </div>
  )
}
```
</div>

هنا، يمكننا استيراد مكونات منفصلة للعنوان أو الشريط الجانبي، ويمكننا أيضًا إضافة جميع تنسيقات CSS التي نحتاجها.

ويمكنك استخدامه في كل صفحة مثل هذا:

<div dir="ltr">

```js
import withLayout from "../components/Layout.js";

const Page = () => <p>Here's a page!</p>;

export default withLayout(Page);
```
</div>

لكنني وجدت أن هذا ينطبق فقط على الحالات البسيطة، ولا تحتاج إلى استدعاء <span dir ="ltr">`getInitialProps()`</span> على الصفحة.

لماذا؟

لأنه يتم استدعاء <span dir ="ltr">`getInitialProps()`</span> في مكونات الصفحة فقط. ومع ذلك، إذا قمنا بتصدير المكونات ذات الترتيب الأعلى لـ <span dir ="ltr">`withLayout()`</span> من الصفحة، فلن يتم استدعاء <span dir ="ltr">`Page.getInitialProps()`</span> وستصبح <span dir ="ltr">`withLayout.getInitialProps()`</span>.

من أجل تجنب التعقيد غير الضروري لشفراتنا البرمجية، فإن البديل هو استخدام الخصائص (props):

<div dir="ltr">

```js
export default props => (
  <div>
    <nav>
      <ul>....</ul>
    </hav>
    <main>
      {props.content}
    </main>
  </div>
)
```
</div>

وفي صفحاتنا نستخدمها الآن على النحو التالي:

<div dir="ltr">

```js
import Layout from "../components/Layout.js";

const Page = () => <Layout content={<p>Here's a page!</p>} />;
```
</div>

تسمح لنا هذه الطريقة باستخدام <span dir ="ltr">`getInitialProps()`</span> من مكون الصفحة، والعيب الوحيد هو أنه يجب كتابة المكون JSX في خاصية `content`:

<div dir="ltr">

```js
import Layout from "../components/Layout.js";

const Page = () => <Layout content={<p>Here's a page!</p>} />;

Page.getInitialProps = ({ query }) => {
  //...
};
```
</div>

## مسارات API <a id="p22"></a>

بالإضافة إلى إنشاء **مسارات الصفحات (Page Routes)**، مما يعني أن الصفحات يتم تقديمها إلى المتصفح كصفحات ويب، يمكن لـ Next.js أيضًا إنشاء مسارات API.

هذه ميزة مثيرة للغاية لأنها تعني أنه يمكن استخدام Next.js لإنشاء واجهة أمامية للبيانات المخزنة والمسترجعة بواسطة Next.js نفسها، ولإرسال JSON من خلال طلبات get.

تجد توجيهات API ضمن المجلد `/pages/api/` ويتم تعيينها نقطة نهاية <span dir ="ltr">`/api`</span>.

هذه الميزة مفيدة للغاية عند تطوير التطبيقات.

في هذه المسارات، كتبنا كود Node.js (وليس كود React). أنت تنتقل من الواجهة الأمامية إلى الخلفية، ولكن بسلاسة تامة.

لنفترض أن لديك ملفًا <span dir ="ltr">`/pages/api/comments.js`</span> يتمثل هدفه في إرجاع تعليقات تدوينة بتنسيق JSON.

لنفترض أن لديك قائمة بالتعليقات مخزنة في ملف `comments.json`:

<div dir="ltr">

```json
[
  {
    "comment": "First"
  },
  {
    "comment": "Nice post"
  }
]
```
</div>

إليك نموذج التعليمات البرمجية، والذي يعود إلى المستخدم بقائمة التعليقات:

<div dir="ltr">

```js
import comments from "./comments.json";

export default (req, res) => {
  res.status(200).json(comments);
};
```
</div>

سيستمع إلى الرابط <span dir ="ltr">`/api/comments`</span>، ويمكنك محاولة مناداته (calling) به باستخدام متصفحك:

![](https://i.suar.me/lX3NN/)

يمكن لمسارات API أيضًا استخدام **التوجيه الديناميكي** مثل الصفحات، واستخدام البنية `[]` لإنشاء مسار API ديناميكي، مثل <span dir ="ltr">`/pages/api/comments/[id].js`</span> الذي سيسترد التعليقات الخاصة بمعرف التدوينة.

في الداخل، <span dir ="ltr">`[id].js`</span> يمكنك استرداد القيمة `id` من خلال البحث عنها داخل الكائن `req.query`:

<div dir="ltr">

```js
import comments from "../comments.json";

export default (req, res) => {
  res.status(200).json({ post: req.query.id, comments });
};
```
</div>

هنا، يمكنك أن ترى أن نتيجة الشفرة أعلاه:

![img](https://i.suar.me/er0LP/)

في الصفحات الديناميكية، ستحتاج إلى استيراد `useRouter` من `next/router`، ثم الحصول على كائن الموجّه باستخدام <span dir ="ltr">`const router = useRouter()`</span>، ومن ثم سنتمكن من الحصول على القيمة `id`باستخدام `router.query.id`.

في جانب الخادوم، يكون الأمر أسهل، حيث يتم إرفاق الاستعلام بكائن الطلب.

إذا قمت بتنفيذ طلب POST، فإن جميع الطلبات تعمل بنفس الطريقة - يتم تنفيذ جميع العمليات من خلال هذا التصدير الافتراضي.

لفصل POST عن GET وطرق HTTP الأخرى (PUT، DELETE)، ابحث عن القيمة `req.method`:

<div dir="ltr">

```js
export default (req, res) => {
  switch (req.method) {
    case "GET":
      //...
      break;
    case "POST":
      //...
      break;
    default:
      res.status(405).end(); //Method Not Allowed
      break;
  }
};
```
</div>

بالإضافة إلى req.query و req.method الذي رأيناه بالفعل، يمكننا أيضًا الوصول إلى ملفات تعريف الارتباط من خلال الرجوع إلى req.cookies (نص الطلب في req.body).

في الكواليس، يتم تشغيل كل هذا بواسطة [Micro](https://github.com/zeit/micro)، وهي مكتبة تعمل على تشغيل خدمات HTTP غير متزامنة، تم إنشاؤها بواسطة نفس الفريق الذي أنشأ Next.js.

يمكنك استخدام أي برنامج وسيط Micro في توجيه API الخاص بنا لإضافة المزيد من الميزات.

## تشغيل التطبيق من جهة المستخدم Client Side أو من جهة الخادوم Server Side) <a id="p23"></a>

في مكونات صفحات مشروعك، يمكنك تنفيذ التعليمات البرمجية فقط في جانب الخادوم أو من جانب المستخدم، عن طريق التحقق من الخاصية `window`.

هذه الخاصية موجودة فقط داخل المتصفح، لذا يمكنك التحقق منها:

<div dir="ltr">

```js
if (typeof window === "undefined") {
}
```
</div>

وقم بتضمين التعليمات البرمجية من جانب الخادوم داخل هذا الشرط.

وبالمثل، يمكنك فقط تنفيذ من جهة المستخدم فقط عن طريق التحقق

<div dir="ltr">

```js
if (typeof window !== "undefined") {
}
```
</div>

**خدعة JS**: نستخدم الدالة `typeof` هنا لأننا لا نستطيع اكتشاف القيم غير المعرفة بوسائل أخرى. إذا كان `if (window === undefined)`، فلن نتمكن من تنفيذه لأننا سنحصل على خطأ وقت تشغيل "window is not defined".

كتحسين لوقت بناء تطبيقك،، يزيل Next.js أيضًا الكود الذي يستخدم تلك التحققات من الحزم.  
لن تتضمن الحزمة من جانب المستخدم الشرط <span dir ="ltr">`if (typeof window === 'undefined') {}`</span>.

## تصدير النسخة النهائية <a id="p24"></a>

يتم دائمًا ترك طريقة تصدير التطبيق في آخر الدرس.

هنا أريد أن أقدمه مبكرًا، فقط لأنه من السهل جدًا تصدير تطبيق Next.js بحيث يمكننا الغوص فيه الآن، ثم الانتقال إلى مواضيع أخرى أكثر تعقيدًا لاحقًا.

تذكر في فصل "كيفية تثبيت Next.js" لقد أخبرتك بإضافة هذه الأسطر الثلاثة إلى القسم `package.json` `script`:

<div dir="ltr">

```json
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start"
}
```
</div>

حتى الآن، استخدمنا `npm run dev` لاستدعاء الأمر التالي المثبت محليًا في `node_modules/next/dist/bin/next`. يؤدي ذلك تشغيل التطبيق في وضع التطوير، الذي يوفر لنا معاينة المصدر وإعادة التحميل الفوري للتغييرات، وهما وظيفتان مفيدتان جدًا لتصحيح الأخطاء.

من خلال تشغيل `npm run build`، يمكنك استدعاء الأمر نفسه لإنشاء موقع ويب عبر `build` بعد ذلك، من خلال تشغيل `npm run start`، يمكن استخدام نفس الأمر لبدء تطبيق الإنتاج عبر `start`.

هذان الأمران يجب علينا تنفيذهما لنشر الإصدار النهائي من الموقع محليًا بنجاح. يتم تحسين الإصدار النهائي بشكل كبير ولا يأتي مع خرائط المصدر وأشياء أخرى مثل إعادة التحميل الفوري للتغييرات، والتي لا تفيد مستخدمينا النهائيين.

لذلك، دعونا نصدّر النسخة النهائية من تطبيقنا:

<div dir="ltr">

```bash
npm run build
```
</div>

![img](https://i.suar.me/grZaQ/)

يخبرنا ناتج هذا الأمر أن مسارات معينة `/` و <span dir ="ltr">`/blog`</span> يتم عرضها الآن بتنسيق HTML ثابت/ساكن، وسيتم تقديم <span dir ="ltr">`/blog/[id]`</span> بواسطة الواجهة الخلفية Node.js.

ثم يمكنك تشغيله `npm run start`:

<div dir="ltr">

```bash
npm run start
```
</div>

![img](https://i.suar.me/MGd3W/)

يمكننا الآن زيارة النسخة النهائية: [http://localhost:3000](http://localhost:3000/)

## رفع التطبيق على Vercel <a id="p25"></a>

في الفصل السابق، نشرنا تطبيق Next.js محليًا.

كيف ننشره على خادم ويب حقيقي حتى يتمكن الآخرون من الوصول إليه؟

إحدى أسهل الطرق لنشر تطبيقات Next هي من خلال منصة Vercel التي أنشأت مشروع Next.js. يمكنك استخدامه الآن لنشر تطبيقات Node.js ومواقع الويب الثابتة وما إلى ذلك.

الآن، أصبحت خطوات النشر والتوزيع للتطبيق بسيطة جدًا وسريعة للغاية. بالإضافة إلى تطبيقات Node.js، فهي تدعم أيضًا نشر Go و PHP و Python ولغات أخرى.

يمكنك التفكير في الأمر على أنه "سحابة" لأنك لا تعرف حقًا مكان نشر التطبيق، لكنك تعلم أنه سيكون لديك رابط يمكنك الوصول إليه من خلاله.

يمكنك الآن البدء في استخدام الخطة المجانية، والتي تتضمن حاليًا استضافة بسعة 100 جيجابايت، و 1000 عملية إنشاء شهريًا، وعرض النطاق الترددي 100 جيجابايت شهريًا، وموقع CDN. إذا كنت بحاجة إلى مزيد من الأسعار، فيمكن أن تساعدك [صفحة التسعير](https://vercel.com/pricing) في فهم التكلفة.

أفضل طريقة لبدء استخدام Vercel هي استخدام Vercel CLI الرسمي:

<div dir="ltr">

```
npm i -g vercel
```
</div>

ثم قم بتشغيل:

<div dir="ltr">

```bash
vercel login
```
</div>

إذا لم تسجل بعد، يرجى إنشاء حساب على https://vercel.com/signup قبل المتابعة، ثم إضافة البريد الإلكتروني إلى CLI client.

بعد الانتهاء من ذلك، قم بتشغيل المجلد لمشروع Next.js

<div dir="ltr">

```bash
vercel
```
</div>
وسيتم نشر التطبيق على الفور في سحابة Vercel، وستحصل على عنوانك الفريد للتطبيق.

## تحليل حُزم التطبيق (The App Bundles) <a id="p26"></a>

توفّر Next.js طريقة لتحليل الحزم التي أنشئت.

افتح ملف package.json للتطبيق وفي قسم scripts أضف هذه الأوامر الثلاثة الجديدة:

<div dir="ltr">

```json
"analyze": "cross-env ANALYZE=true next build",
"analyze:server": "cross-env BUNDLE_ANALYZE=server next build",
"analyze:browser": "cross-env BUNDLE_ANALYZE=browser next build"
```
</div>

مثل:

<div dir="ltr">

```json
{
  "name": "firstproject",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "next",
    "build": "next build",
    "start": "next start",
    "analyze": "cross-env ANALYZE=true next build",
    "analyze:server": "cross-env BUNDLE_ANALYZE=server next build",
    "analyze:browser": "cross-env BUNDLE_ANALYZE=browser next build"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "next": "^9.1.2",
    "react": "^16.11.0",
    "react-dom": "^16.11.0"
  }
}
```
</div>

ثم قم بتثبيت هاتين الحزمتين:

<div dir="ltr">

```bash
npm install --dev cross-env @next/bundle-analyzer
```
</div>

قم بإنشاء ملف `next.config.js` في المجلد الرئيسي للمشروع، بهذا المحتوى:

<div dir="ltr">

```js
const withBundleAnalyzer = require("@next/bundle-analyzer")({
  enabled: process.env.ANALYZE === "true",
});

module.exports = withBundleAnalyzer({});
```
</div>

الآن قم بتشغيل الأمر:

<div dir="ltr">

```bash
npm run analyze
```
</div>

![img](https://i.suar.me/43r7o/)

يجب أن يفتح هذا صفحتين في المتصفح. واحد لحزم المستخدم (client bundles) والآخر لحزم الخادوم (server bundles):

![img](https://i.suar.me/0mO3Z/)

![img](https://i.suar.me/AAxL0/)

هذا مفيد بشكل لا يصدق. يمكنك فحص ما يشغل أكبر مساحة في الحزم، ويمكنك أيضًا استخدام الشريط الجانبي لاستبعاد الحزم الصغيرة، من أجل تصور أسهل:

![img](https://i.suar.me/mVyxw/)

## التحميل البطيئ (Lazy loading) للوحدات <a id="p27"></a>

تعد القدرة على تحليل الحزمة بصريًا أمرًا رائعًا لأنه يمكننا تحسين تطبيقنا بسهولة بالغة.

لنفترض أننا بحاجة إلى تحميل مكتبة Moment في منشورات مدونتك:

<div dir="ltr">

```bash
npm install moment
```
</div>

الآن دعنا نحاكي حقيقة أننا نحتاجها في مسارين مختلفين: <span dir ="ltr">`/blog`</span>و <span dir ="ltr">`/blog/[id]`</span>.

نستورده في `pages/blog/[id].js`:

<div dir="ltr">

```jsx
import moment from 'moment'

...

const Post = props => {
  return (
    <div>
      <h1>{props.post.title}</h1>
      <p>Published on {moment().format('dddd D MMMM YYYY')}</p>
      <p>{props.post.content}</p>
    </div>
  )
}
```
</div>

سأضيف تاريخ اليوم،كمثال.

سيتم تضمين مكتبة Moment.js في حزم صفحة التدوينة، كما يتضح من تشغيل `npm run analytics`:

![img](https://i.suar.me/6jEVA/)

<span dir ="ltr">`/blog/[id]`</span> لاحظ أن رقم حجم الصفحة صار أحمر اللون، وهو المسار الذي أضفنا إليه Moment.js!

لقد انتقل من ~ 1 كيلو بايت إلى 350 كيلو بايت، وتعتبر صفحة كبيرة جدًا. وذلك لأن مكتبة Moment.js نفسها تبلغ 349 كيلوبايت.

يوضح تصوّر حزم العميل الآن أن الحزمة الأكبر هي الصفحة الأولى، والتي كانت قليلة جدًا من قبل. و 99٪ من حجمها هو Moment.js.

![img](https://i.suar.me/EA2l7/)

في كل مرة يتم فيها تحميل صفحة التدوينة، سنحمّل كل ه الحزمة إلى المستخدم. وهذه ليست مثالية.

تتمثل أحد الحلول في العثور على مكتبة أصغر، لأن Moment.js معروفة بحجمها الكبير، لكن دعنا نفترض كمثال، توجّب علينا استخدامها.

بدلاً من ذلك، ما يمكننا فعله هو فصل كل شفرات Moment في حزمة واحدة.

كيف؟ بدلاً من استيراد Moment على مستوى المكون، نقوم بإجراء استيراد غير متزامن داخل getInitialProps، ونحسب القيمة لإرسالها إلى المكون.
تذكر أنه لا يمكننا إرجاع كائنات معقدة داخل الكائن الذي تم إرجاعه <span dir ="ltr">`getInitialProps()`</span>، لذلك نحسب التاريخ بداخله:

<div dir="ltr">

```js
import posts from "../../posts.json";

const Post = (props) => {
  return (
    <div>
      <h1>{props.post.title}</h1>
      <p>Published on {props.date}</p>
      <p>{props.post.content}</p>
    </div>
  );
};

Post.getInitialProps = async ({ query }) => {
  const moment = (await import("moment")).default();
  return {
    date: moment.format("dddd D MMMM YYYY"),
    post: posts[query.id],
  };
};

export default Post;
```
</div>

لاحظ أننا استخدمنا .<span dir ="ltr">default()</span> بعد await import؟ لأنه من الضروري الإشارة إلى التصدير الافتراضي في الاستيراد الديناميكي (dynamic import). راجع <https://v8.dev/features/dynamic-import>

إذا قمنا الآن بتشغيل `npm run analyze` فسنرى:

![img](https://i.suar.me/WglYe/)

تعد حزمة <span dir ="ltr">`/blog/[id]`</span> صغيرة مرة أخرى لأن Moment انتقلت إلى ملف الحزمة الخاص بها وتحميلها بشكل منفصل بواسطة المتصفح.

## دليل مسارك القادم <a id="p28"></a>

هناك الكثير لتعرفه عن Next.js. لم أتحدث عن إدارة جلسات المستخدم مع تسجيل الدخول، وبدون خادم، وإدارة قواعد البيانات، وما إلى ذلك.

الغرض من هذا الدليل ليس تعليمك كل شيء، ولكن تعريفك بجميع ميزات Next.js خطوة بخطوة.

الخطوة التالية التي أوصي بها هي قراءة [المستندات الرسمية لـ Next.js جيدًا](https://nextjs.org/docs) لمعرفة المزيد حول جميع الميزات والوظائف التي لم أتحدث عنها، وإلقاء نظرة على جميع الوظائف الإضافية التي [قدمتها المكونات الإضافية Next.js](https://github.com/zeit/next-plugins)، بعضها مذهل جدًا.

</div>
