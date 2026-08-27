# 💗 تطبيق هدية - ننو

تطبيق أندرويد بسيط اتعمل كهدية، بيعرض صور، غزل بالسوداني، وأغنية بتتشغل تلقائيًا،
مع رسوم متحركة رومانسية باسم "ننو"، "تاليه"، "بت الخالة".

**التطبيق يعمل بالكامل أوفلاين** — كل الصور، الأغنية، والمحتوى مضمّنة داخل الـ APK
نفسه (لا يحتاج إنترنت بعد التثبيت).

## كيف تحصل على ملف الـ APK الجاهز؟

الكود مبني بصيغة مشروع Android Gradle قياسي في مجلد [`android/`](./android).
عند كل Push لهذا المستودع، يقوم GitHub Actions تلقائيًا ببناء وتوقيع ملف الـ APK.

### تحميل الـ APK من GitHub Actions:

1. اذهب إلى تبويب **Actions** في المستودع على GitHub.
2. افتح آخر تشغيل ناجح لـ workflow باسم **"Build Nno Gift APK"**.
3. في أسفل الصفحة، تحت قسم **Artifacts**، حمّل الملف المضغوط **`nno-gift-apk`**.
4. فك الضغط، وستجد بداخله ملف `نو_هدية.apk` جاهز للتثبيت.

### أو ابنِه بنفسك محليًا (باستخدام Android Studio / Gradle):

```bash
cd android
gradle assembleRelease
# الناتج في: android/app/build/outputs/apk/release/app-release.apk
```

> ملاحظة: مفتاح التوقيع (`android/app/nno-release.keystore`) مُرفق داخل المستودع
> لتسهيل بناء نسخة موقّعة جاهزة للتثبيت مباشرة دون أي إعداد إضافي، لأن هذا تطبيق
> هدية شخصي وليس تطبيقًا سيُنشر على المتجر.

## هيكل المشروع

```
android/
  app/
    src/main/
      java/com/nno/habiba/MainActivity.java   # يعرض واجهة الويب + إشعار ترحيبي
      assets/
        index.html                            # كل واجهة التطبيق (صور/غزل/موسيقى) - أوفلاين بالكامل
        images/                                # صور ننو
        song.m4a                               # الأغنية
      res/
        mipmap-*/ic_launcher*.png              # أيقونة التطبيق بكل الأحجام
        values/strings.xml
      AndroidManifest.xml
    build.gradle
  build.gradle
  settings.gradle
.github/workflows/build-apk.yml                # بناء وتوقيع تلقائي عبر GitHub Actions
```

## تثبيت الـ APK على الهاتف

1. انقل ملف `نو_هدية.apk` إلى الهاتف.
2. فعّل خيار "التثبيت من مصادر غير معروفة" (Install unknown apps) في الإعدادات.
3. افتح الملف وثبّت التطبيق.
4. استمتعي 💗
