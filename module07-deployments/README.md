 مصادر خطة الدراسة للوحدة 7

### 🎯 مقدمة

بعد ما أنجزنا في هذه الوحدة وتعلمنا كل ما يتعلق بـ Deployments — من إنشائها، تحديثها، إدارتها، واستراتيجيات النشر — حان الوقت نراجع أهم المصادر التي ستساعدك على التعمق أكثر، سواء من الوثائق الرسمية أو الأدوات العملية التي يمكن تجربتها بنفسك.

---

### 📘 المصادر الرسمية

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

### 📦 مستودعات GitHub وأمثلة عملية

- [kubernetes/examples](https://github.com/kubernetes/examples/tree/master/staging/deployment)
  - يحتوي على ملفات YAML جاهزة لعدة سيناريوهات مع شرح مبسط.
  
- [Learnk8s Blue-Green & Canary Examples](https://learnk8s.io/blog/kubernetes-deployment-strategies)
  - مقال تطبيقي مفصل مع رسوم توضيحية.

---

### 🧪 أدوات للمحاكاة والاختبار

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

### 🧠 ماذا تفعل بعد هذا الفيديو؟

- راجع ملفات YAML التي أنشأناها في العروض العملية.
- جرّب تعديل نسخ الصور، واستكشاف ما يحدث في الكلاستر.
- تمرّن على تنفيذ Rollback لتثبيت الفهم.
- جرّب اللعب بمعايير الاستراتيجية (maxSurge و maxUnavailable).

---

### 🎬 الخاتمة

استيعاب مفهوم الـ Deployment هو خطوة أساسية في مسارك الاحترافي مع Kubernetes، فهو المسؤول الأول عن التحكم في إصدارات التطبيق، التحديثات، واستقرار الخدمة.

واصل التعلّم، وابدأ بتجربة ما تعلمته محليًا قبل أن تنتقل إلى بيئات الإنتاج الحقيقية.

