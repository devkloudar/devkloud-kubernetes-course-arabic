# نظرة عامة على الفصل

هذا الفصل يمثل النقلة من إدارة Pod واحد إلى إدارة تطبيق كامل بشكل احترافي.

###  ماذا سنتعلم في هذا الفصل؟

- كيفية إنشاء أول Deployment لتشغيل تطبيقك على الكلاستر.
- طريقة تحديث التطبيق وإرسال إصدار جديد بدون Downtime.
- التحكم في عدد النسخ (Replicas) وتشغيل أكثر من نسخة لتوفير التوافر العالي.
- تنفيذ استراتيجيات نشر مثل RollingUpdate و Recreate.
- فهم دور الـ ReplicaSet وكيفية ارتباطه بالـ Deployment.
- تنفيذ تحديثات واسترجاع النسخ السابقة عند الفشل (Rollbacks).
- تجربة عملية متكاملة تغطي كل المفاهيم السابقة.

> هذه الوحدة جوهرية وأساسية لأي مطور أو مهندس يعمل على Kubernetes في بيئة إنتاج.

##  لماذا نستخدم Deployment بدلًا من Pod؟

في الإنتاج، لا يكفي تشغيل Pod واحد فقط. نحتاج إلى:

- **التوافر العالي (High Availability)**: أكثر من نسخة (Replica) للتطبيق.
- **التحديث بدون توقف (Rolling Update)**.
- **التعافي الذاتي (Self-healing)**: إذا تعطل Pod يُعاد تشغيله تلقائيًا.
- **إدارة الإصدارات والتاريخ (Revision History)**.

بالتالي، الـ Deployment يوفر:

> 🔁 ReplicaSet + التحكم في التحديث + إدارة التوافر

# Rolling Updates و Rollbacks

###  مقدمة

في البيئات الإنتاجية، لا يمكننا إيقاف التطبيق لتحديثه. لهذا السبب، يوفر Kubernetes آلية **Rolling Update** لتحديث التطبيقات تدريجيًا بدون توقف للخدمة.  
وإذا حدث خلل أثناء التحديث، يمكننا استخدام **Rollback** للرجوع بسهولة إلى النسخة السابقة المستقرة.



## التحديث التدريجي

###  ما هو Rolling Update؟
هو أسلوب يقوم Kubernetes من خلاله بتحديث الـ Pods تدريجيًا:
- يوقف **عدد قليل من الـ Pods القديمة**.
- يُنشئ **Pods جديدة بالإصدار الجديد**.
- يكرر العملية حتى يتم استبدال كل الـ Pods بالنسخة الجديدة.

###  المميزات:
- لا يحدث Downtime.
- يسمح بمراقبة التحديث خطوة بخطوة.
- يمكن تخصيص سلوكه عبر `maxSurge` و `maxUnavailable`.


## مصادر خطة الدراسة للفصل 7

###  المصادر الرسمية

1. **📄 وثائق Kubernetes الرسمية عن Deployment**
   - الرابط: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
   - تحتوي على شرح شامل لكل خصائص الـ Deployment، مع أمثلة تفصيلية.

2. **📄 وثائق Rolling Updates و Rollbacks**
   - الرابط: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#rolling-update-deployment
   - توضح كيفية تنفيذ تحديثات تدريجية وكيفية الرجوع إلى الإصدارات السابقة.

3. **📄 استراتيجيات النشر في Kubernetes**
   - الرابط: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#strategy
   - شرح YAML للحقل `strategy` وأنواع التحديث: `Recreate` و `RollingUpdate`.

---

###  مستودعات GitHub وأمثلة عملية

- [kubernetes/examples](https://github.com/kubernetes/examples/tree/master/staging/deployment)
  - يحتوي على ملفات YAML جاهزة لعدة سيناريوهات مع شرح مبسط.
  
- [Learnk8s Blue-Green & Canary Examples](https://learnk8s.io/blog/kubernetes-deployment-strategies)
  - مقال تطبيقي مفصل مع رسوم توضيحية.

---

###  أدوات للمحاكاة والاختبار

- **Play with Kubernetes**
  - https://labs.play-with-k8s.com/
  - بيئة سحابية مجانية لاختبار الأكواد مباشرة دون تثبيت محلي.

- **Katacoda (deprecated)** أو بديله [killercoda.com](https://killercoda.com)
  - يقدم سيناريوهات تفاعلية ممتازة في إدارة الـ Deployments.

---

### 📚 كتب وأدلة مقترحة

- "Kubernetes Up & Running" (الفصل الخاص بـ Deployments وReplicaSets)
- "The Kubernetes Book" - الفصل الخاص بالتحديثات والإدارة.

---

###  ماذا تفعل بعد هذا الفيديو؟

- راجع ملفات YAML التي أنشأناها في العروض العملية.
- جرّب تعديل نسخ الصور، واستكشاف ما يحدث في الكلاستر.
- تمرّن على تنفيذ Rollback لتثبيت الفهم.
- جرّب اللعب بمعايير الاستراتيجية (maxSurge و maxUnavailable).

---

###  الخاتمة

استيعاب مفهوم الـ Deployment هو خطوة أساسية في مسارك الاحترافي مع Kubernetes، فهو المسؤول الأول عن التحكم في إصدارات التطبيق، التحديثات، واستقرار الخدمة.

واصل التعلّم، وابدأ بتجربة ما تعلمته محليًا قبل أن تنتقل إلى بيئات الإنتاج الحقيقية.

