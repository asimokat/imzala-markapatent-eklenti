---
name: yayina-ve-yidka-itiraz
description: TÜRKPATENT Resmî Bülten yayınına itiraz dilekçesi, YİDK (Yeniden İnceleme ve Değerlendirme Kurulu) karara itiraz dilekçesi ve FSHHM nezdinde YİDK kararının iptali / marka-patent hükümsüzlük davası dilekçesi yazarken uygulanır.
---

# Yayına İtiraz, YİDK İtirazı ve FSHHM Dava Dilekçesi Yazımı

Bu skill; TÜRKPATENT Markalar / Tasarımlar / Patent Dairesi Başkanlığına sunulan **yayına itiraz**, **YİDK nezdinde karara itiraz** ve Fikrî ve Sınaî Haklar Hukuk Mahkemesi'nde (**FSHHM**) açılan **YİDK kararının iptali / hükümsüzlük** dilekçelerinde uygulanır.

## 1. Bülten Künyesi ve Süre Denetimi (Zorunlu İlk Adım)

İtiraz dilekçesine başlamadan önce bülten numarasını `turkpatent_bulten_ara` ile sorgula:
- Bültenin **resmî yayım tarihini** (`GG.AA.YYYY`),
- 6769 s. SMK uyarınca **itirazın son gününü** (tatil kaydırması dahil) doğrula ve dilekçenin "Süresinde İtiraz" bölümüne bülten sayısı ve yayım tarihiyle birlikte yaz.

## 2. TÜRKPATENT Yayına İtiraz / YİDK İtiraz Dilekçesi İskeleti

1. **Başlık:** `TÜRK PATENT VE MARKA KURUMU / MARKALAR DAİRESİ BAŞKANLIĞINA` (karara itirazda: `YENİDEN İNCELEME VE DEĞERLENDİRME KURULU BAŞKANLIĞINA`).
2. **Dosya Künyesi:**
   - İtiraz Edilen Başvuru No / Bülten Sayısı ve Yayım Tarihi / İtiraz Edilen Sınıflar
   - İtiraz Eden (Önceki Hak Sahibi) ve Vekili
   - Mesnet (Dayanak) Markaların Tescil Numaraları ve Sınıfları
3. **Hukuki Sebepler ve İnceleme Sırası (6769 s. SMK):**
   - **SMK m. 6/1 (İltibas / Karıştırılma İhtimali):**
     - *İşaretlerin Benzerliği:* Görsel, işitsel (fonetik) ve anlamsal (kavramsal) benzerliği ayrı alt başlıklarda karşılaştır; bütüncül izlenim ve ayırt edici (baskın) unsuru ortaya koy.
     - *Mal/Hizmetlerin Aynı veya Benzer Türde Olması:* Nice sınıflarını ve alt gruplarını somut olarak eşleştir (dağıtım kanalları, hedef tüketici kitlesi, ikame/tamamlayıcı nitelik).
     - *İlişkilendirilme İhtimali:* Başvurunun müvekkilin seri markalarından biri veya yeni bir ticari uzantısı sanılacağı riskini açıkla.
   - **SMK m. 6/3 (Tescilsiz Marka / Ticaret Unvanı / Önceki Kullanım):** Başvuru tarihinden önce Türkiye'de ciddi ve yoğun ticari kullanım ile ayırt edicilik kazanıldığını fatura, katalog, alan adı ve reklam delilleriyle göster.
   - **SMK m. 6/4 ve 6/5 (Tanınmış Marka):** Paris Sözleşmesi 1. Mükerrer 6. madde ve SMK m. 6/5 kapsamında tanınmışlığın haksız avantaj sağlayacağı, itibara zarar vereceği veya ayırt edici karakteri zedeleyeceği (sulandırma) unsurlarını ayrı ayrı tartış.
   - **SMK m. 6/9 (Kötüniyet):** Başvuru sahibinin önceki markadan haberdar olduğunu, sektörel yakınlığı, ticari ilişkiyi veya sistematik taklit kastını somut olgularla ortaya koy.
4. **Ciddi Kullanım Def'i (SMK m. 19/2 ve m. 9) Uyarısı:**
   - İtiraz eden vekiliysen: Mesnet markanın tescil tarihinden itibaren 5 yıl geçmişse, karşı tarafın kullanım ispatı talebine karşı son 5 yıllık fatura, katalog ve ticari kullanım delillerinin hazır bulundurulması gerektiğini kullanıcıya hatırlat.
   - Başvuru sahibi (itiraza cevap veren) vekiliysen: İtiraz edenin mesnet markası itiraz edilen başvurunun başvuru/rüçhan tarihinde Türkiye'de en az 5 yıldır tescilliyse, **SMK m. 19/2 uyarınca açıkça kullanım ispatı talebini** dilekçenin en başında ileri sür.

## 3. İçtihat Kullanımı ve Alıntı Kuralı

- Gerekçe paragrafı ile içtihat paragrafı ayrı durur. İçtihat cümlenin içine sıkıştırılmaz; hemen altında italik blok olarak verilir:
  > *Yargıtay 11. Hukuk Dairesi'nin GG.AA.YYYY tarihli ve YYYY/NNNN E., YYYY/NNNN K. sayılı kararı: "…kararın kendi metninden birebir alıntı…"*
- `karar_getir` ile okunmamış ve `kunye_dogrula` ile doğrulanmamış hiçbir karar dilekçeye yazılmaz.
- FSHHM dava dilekçeleri (YİDK kararının iptali, hükümsüzlük, tecavüzün ref'i) UYAP'a sunulacağından `dilekce-yazimi` kurallarına uygun olarak `.udf` biçiminde de üretilebilir.
