## ماذا سنتعلم في هذا الفصل؟

في هذا الفصل، سنتعرف على:

- ما هو الـ ConfigMap؟ ولماذا نحتاجه؟
- كيف ننشئ ConfigMap من ملف أو متغيرات مباشرة؟
- كيف نربط القيم الموجودة في ConfigMap مع الـ Pods:
  - كمتغيرات بيئية (Environment Variables)
  - أو كملفات داخل الحاويات (Volumes)
- كيف نُحدث ConfigMap دون الحاجة لإعادة نشر التطبيق يدويًا.
- ما هي أفضل الممارسات في التعامل مع ConfigMaps عبر بيئات متعددة مثل dev/staging/prod؟
- وأخيرًا، سنتعلم عمليًا كيف نستخدمه ونختبره داخل الكلاستر.

## ما هو الـ ConfigMap؟

**ConfigMap** هو مورد في Kubernetes يُستخدم لتخزين **إعدادات غير حساسة** (مثل ملفات config، متغيرات البيئة، قيم ثابتة...) بطريقة مستقلة عن التطبيق نفسه.

يمكنك التفكير فيه كـ:

> "مخزن خارجي للقيم التي قد تتغير من بيئة لأخرى دون الحاجة لإعادة بناء التطبيق."


## لماذا نستخدمه؟

1. **فصل الإعدادات عن الكود**:
   - الكود لا يتغير، لكن الإعدادات تختلف حسب البيئة (dev, staging, prod).
2. **سهولة التعديل بدون إعادة بناء الصورة**:
   - إذا أردت تغيير اسم قاعدة البيانات أو عنوان API، يمكنك تعديل الـ ConfigMap فقط.
3. **إعادة استخدام القيم بين عدة Pods**:
   - بدلاً من تكرار نفس القيمة في كل ملف YAML، تضعها في ConfigMap مشترك.
4. **دعم لعدة طرق للإدخال والاستخدام**:
   - من ملفات YAML.
   - من متغيرات بيئية.
   - من ملفات `env`.
   - وربط مباشر مع الـ Pod.



## 📚 مصادر خطة الدراسة - الفصل 8: ConfigMaps

### 🔹 المفاهيم الأساسية
- <a href="https://kubernetes.io/docs/concepts/configuration/configmap/" target="_blank">📖 Kubernetes Concepts: ConfigMap</a>  
- <a href="https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/" target="_blank">📖 كيفية استخدام ConfigMaps مع Pods</a>  

### 🔹 إنشاء ConfigMaps
- <a href="https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#create-configmaps" target="_blank">📖 إنشاء ConfigMap من ملفات أو متغيرات بيئية</a>  
- <a href="https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#define-container-environment-variables-using-configmap-data" target="_blank">📖 حقن القيم في الحاويات عبر Env Variables</a>  

### 🔹 تحديث وإعادة التحميل
- <a href="https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#update-configmap" target="_blank">📖 تحديث ConfigMaps</a>  
- <a href="https://github.com/stakater/Reloader" target="_blank">📖 أداة Reloader لإعادة تحميل Pods عند تغيير ConfigMaps/Secrets</a>  

### 🔹 أفضل الممارسات
- <a href="https://kubernetes.io/docs/concepts/configuration/overview/" target="_blank">📖 أفضل الممارسات في إدارة الإعدادات</a>  
- <a href="https://cloud.google.com/architecture/best-practices-for-kubernetes" target="_blank">📖 Google Cloud: أفضل الممارسات لإدارة ConfigMaps و Secrets</a>  

✅ هذه المصادر ستساعدك على:  
1. فهم مفهوم **ConfigMap** ولماذا نحتاجه في Kubernetes.  
2. إنشاء ConfigMaps من ملفات أو متغيرات بيئة.  
3. حقن القيم داخل الـ Pods باستخدام **Env** أو **Mounted Files**.  
4. تحديث ConfigMaps وإعادة التحميل بشكل عملي.  
5. الالتزام بأفضل الممارسات لتجنب الأخطاء الشائعة.  

