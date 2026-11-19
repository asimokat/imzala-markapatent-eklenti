---
name: marka-patent-arastirma
description: 6769 sayılı Sınai Mülkiyet Kanunu (SMK), TÜRKPATENT resmî bülten yayım ve itiraz süreleri, YİDK kararının iptali, iltibas, tanınmış marka, hükümsüzlük ve tecavüz uyuşmazlıklarında imzala.net arşiviyle araştırma yöntemi.
---

# Marka, Patent ve Sınai Mülkiyet Araştırması

Bu skill, marka ve patent vekilleri ile fikrî ve sınaî haklar avukatlarının `imzala-markapatent` bağlayıcısındaki aletlerle TÜRKPATENT bültenlerini ve yargı kararlarını nasıl araştıracağını düzenler.

## 1. TÜRKPATENT Bülten Tarihi ve İtiraz Süresi Sorgulama

Bülten sayısı, yayım tarihi veya itirazın son günü sorulduğunda **asla hafızadan tarih tahmin etme**; doğrudan `turkpatent_bulten_ara` (veya `veri_getir` içinde `tur="bulten"`) aletini çağır:

- **Resmî Marka Bülteni (`tur="marka"`):** 6769 s. SMK m. 18/1 uyarınca yayım tarihinden itibaren **2 ay**.
- **Resmî Tasarım Bülteni (`tur="tasarim"`):** 6769 s. SMK m. 59/2 uyarınca yayım tarihinden itibaren **3 ay**.
- **Resmî Coğrafi İşaret ve Geleneksel Ürün Adı Bülteni (`tur="cografi-isaret"`):** 6769 s. SMK m. 38/2 uyarınca yayım tarihinden itibaren **3 ay**.
- **Resmî Patent ve Faydalı Model Bülteni (`tur="patent"`):** 6769 s. SMK m. 97/2 uyarınca patent verilmesi kararının Bültende yayımlanmasından itibaren **6 ay** (SMK m. 96/2 araştırma raporu yayımından inceleme talebi/üçüncü kişi görüşü süresi: **3 ay**).
- **Resmî İlanen Tebligat Bülteni (`tur="ilanen-tebligat"`):** 7201 s. Tebligat Kanunu m. 31 ve SMK m. 160 uyarınca son ilan tarihinden itibaren **7 gün sonra** tebliğ edilmiş sayılır; üzerine işlem türüne göre kanuni itiraz süresi (2 ay) eklenir.

**Kritik Usul Kuralı:** TÜRKPATENT nezdindeki idari itiraz süreleri idari süre olup **adli tatile (HMK m. 102-104) tabi değildir**; Temmuz-Ağustos aylarında işlemeye ve sona ermeye devam eder. Yalnızca son gün Cumartesi, Pazar veya ulusal/dini bayram tatiline rastlarsa izleyen ilk iş günü mesai bitimine uzar (`turkpatent_bulten_ara` bu tatil kaydırmasını otomatik hesaplayarak verir). Buna karşılık YİDK kararının iptali davası süresi (tebliğden itibaren 2 ay, 5000 s.K. m. 15/C) mahkeme nezdinde hak düşürücü dava açma süresi olduğundan HMK hükümlerine tabidir.

## 2. İçtihat Araştırması (Yargıtay 11. HD, HGK ve FSHHM)

1. **Kelime ve anlam aramasını birlikte çalıştır:**
   - `ictihat_ara`: kısa terim ve süzgeç (`daire="11. Hukuk Dairesi"` veya `daire="Hukuk Genel Kurulu"`, `atif="smk 6"` gibi). Örnek sorgular:
     - `"iltibas karıştırılma ihtimali"`
     - `"YİDK kararının iptali tanınmış marka"`
     - `"ciddi kullanım def'i beş yıl"`
     - `"marka başvurusu kötüniyet tescil"`
     - `"patent hükümsüzlük buluş basamağı"`
   - `ictihat_semantik`: olayı doğal Türkçe cümleyle anlat (Türkçe harfleri koru).
2. **Kararı okumadan atıf yapma:** `karar_getir` ile kararın hüküm veya tam metnini aç. Özellikle:
   - Karşılaştırılan markaların tescilli olduğu **Nice sınıflarını** (ör. 5, 29, 30, 35. sınıf),
   - İbarenin **asli ve tali (ayırt edici ve tanımlayıcı) unsurlarını**,
   - **Ortalama tüketicinin** algısını ve görsel/işitsel/anlamsal benzerlik değerlendirmesini metinden kontrol et.
3. **Künyeyi doğrula:** Metne girecek her Yargıtay, HGK veya BAM karar künyesini `kunye_dogrula` ile doğrula.
4. **Kapsamlı uyuşmazlıklarda derin araştırma:** Çok sınıflı iltibas, seri marka, eskiye dayalı kullanım (SMK m. 6/3), tanınmışlık kriterleri veya tecavüz/tazminat hesaplamalarında `arastirma_baslat` + `arastirma_sonuc` kullan.
