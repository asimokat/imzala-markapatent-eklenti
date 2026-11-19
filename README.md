# imzala.net Marka & Patent — Claude Plugin

**GÜNLÜK GÜNCELLENİR, HEP TAZE.** Marka ve patent vekilleri ile fikrî ve sınaî haklar avukatları için **TÜRKPATENT Resmî Bültenleri** (Marka, Tasarım, Patent ve Faydalı Model, Coğrafi İşaret, İlanen Tebligat) ve **11,6 milyonluk Türk yargı arşivi** (Yargıtay 11. Hukuk Dairesi, Hukuk Genel Kurulu, Bölge Adliye Mahkemeleri FSHHD ve Fikrî ve Sınaî Haklar Hukuk/Ceza Mahkemeleri) bağlayıcısı.

## Neler Yapar?

1. **TÜRKPATENT Resmî Bülten Takvimi ve 6769 s. SMK İtiraz Süresi Hesabı (`turkpatent_bulten_ara`, `veri_getir`):**
   - 919 resmî bültenin (349 Marka, 274 Tasarım, 140 Patent/Faydalı Model, 135 Coğrafi İşaret, 21 İlanen Tebligat) yayım tarihini, 6769 sayılı Sınai Mülkiyet Kanunu'na göre kesin yayına itiraz son gününü (hafta sonu ve resmî tatil kaydırmalarıyla birlikte; idari süreler adli tatile tabi değildir) ve doğrudan resmî PDF indirme bağlantısını verir:
     - **Resmî Marka Bülteni:** SMK m. 18/1 uyarınca yayım tarihinden itibaren **2 ay**
     - **Resmî Tasarım Bülteni:** SMK m. 59/2 uyarınca yayım tarihinden itibaren **3 ay**
     - **Resmî Coğrafi İşaret ve Geleneksel Ürün Adı Bülteni:** SMK m. 38/2 uyarınca yayım tarihinden itibaren **3 ay**
     - **Resmî Patent ve Faydalı Model Bülteni:** SMK m. 97/2 uyarınca patent verilmesi kararının yayımından **6 ay** (SMK m. 96/2 araştırma raporu yayımından inceleme talebi/görüş: **3 ay**)
     - **Resmî İlanen Tebligat Bülteni:** 7201 s. Tebligat K. m. 31 ve SMK m. 160 uyarınca ilandan **7 gün sonra** tebliğ edilmiş sayılır (+2 ay itiraz süresi)
2. **Bülten Tam Metin Araması (`turkpatent_bulten_ara`):**
   - Coğrafi İşaret ve İlanen Tebligat bültenlerinin tamamında ve indekslenen Marka/Tasarım/Patent bültenlerinde başvuru numarası, ibare, vekil veya başvuru sahibi araması yapar.
3. **Sınai Mülkiyet İçtihat Arşivi (`ictihat_ara`, `ictihat_semantik`, `karar_getir`, `kunye_dogrula`):**
   - Yargıtay 11. Hukuk Dairesi, HGK, BAM ve FSHHM kararlarında iltibas (SMK m. 6/1), tanınmış marka (SMK m. 6/4-5), kötüniyet (SMK m. 6/9), ciddi kullanım def'i (SMK m. 9 ve m. 19/2), YİDK kararının iptali, hükümsüzlük (SMK m. 25), tecavüz ve tazminat (SMK m. 149-151) emsallerini bulur ve her künyeyi doğrular.

## Kurulum

### Claude Code / Claude Desktop
```bash
claude mcp add --transport http imzala-markapatent https://mcp.imzala.net/mcp
```

Veya `.mcp.json` / `claude_desktop_config.json` içine:
```json
{
  "mcpServers": {
    "imzala-markapatent": {
      "type": "http",
      "url": "https://mcp.imzala.net/mcp"
    }
  }
}
```

## İçerdiği Skill'ler

- `marka-patent-arastirma`: TÜRKPATENT bülten takvimi, 6769 s. SMK süre hesabı ve Yargıtay 11. HD / HGK / FSHHM içtihat araştırması yöntemi.
- `yayina-ve-yidka-itiraz`: TÜRKPATENT nezdinde yayına itiraz dilekçesi, YİDK (Yeniden İnceleme ve Değerlendirme Kurulu) itirazı ve FSHHM'de YİDK kararının iptali / hükümsüzlük davası dilekçesi yazım kuralları.

## Web Kapısı

- Portal: [marka.imzala.net](https://marka.imzala.net) / [turkpatent.imzala.net](https://turkpatent.imzala.net)
- Bülten & Süre Sorgulama: [marka.imzala.net/turkpatent](https://marka.imzala.net/turkpatent)
