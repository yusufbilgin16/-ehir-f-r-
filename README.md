# Şehir Şoförü – Android projesi

Bu klasör, oyunu telefona kurulabilen bir APK'ya çeviren hazır Android projesidir.
Oyun `app/src/main/assets/index.html` dosyasındadır. 3D motoru (Three.js) derleme sırasında
otomatik indirilip uygulamanın içine konur, bu yüzden oyun telefonda internetsiz de açılır.

## Yol 1: Android Studio ile (önerilen)

1. https://developer.android.com/studio adresinden Android Studio'yu indirip kur.
2. Bu zip'i aç, Android Studio'da **Open** deyip `SehirSoforu` klasörünü seç.
3. İlk açılışta gerekli parçaları kendisi indirir (birkaç dakika sürebilir, internet gerekir).
4. Menüden **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
5. Bitince sağ altta çıkan **locate** bağlantısına tıkla. APK burada:
   `app/build/outputs/apk/debug/app-debug.apk`
6. Bu dosyayı telefona at ve aç. Telefon "bilinmeyen kaynak" izni isterse ver.

## Yol 2: Bilgisayara hiçbir şey kurmadan (GitHub)

1. github.com'da ücretsiz hesap aç, yeni bir depo (repository) oluştur.
2. Bu klasördeki tüm dosyaları depoya yükle (gizli `.github` klasörü dahil).
3. Depoda **Actions** sekmesine gir. "APK oluştur" işi kendiliğinden çalışır (yaklaşık 5 dakika).
4. Bitince işin sayfasındaki **Artifacts** bölümünden `SehirSoforu-apk` dosyasını indir, içindeki APK'yı telefona kur.

## Oyunu güncellemek

Oyunda bir değişiklik yapınca yeni `index.html` dosyasını `app/src/main/assets/` içine koyup
APK'yı yeniden derlemen yeterli. Sürümü artırmak için `app/build.gradle` içinde `versionCode`
ve `versionName` değerlerini bir yükselt.

## Play Store'a koymak için

Play Store, debug APK yerine kendi anahtarınla imzalanmış **App Bundle (.aab)** ister:
Android Studio'da **Build → Generate Signed App Bundle / APK** ile bir anahtar oluşturup imzala.
Bu anahtarı kaybetme; güncellemeleri hep aynı anahtarla imzalaman gerekir.
Çocuklara yönelik uygulamalar için Play Console'da "Aileler" politikalarını doldurman gerekir.
