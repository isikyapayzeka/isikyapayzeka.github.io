# Kulüp link sayfası: kurulum ve güncelleme

Yaka kartlarındaki QR kod `https://isikyapayzeka.github.io` adresine gider. Bu adres hiç değişmez. Sayfadaki linkler ve etkinlik bilgisi ise istediğiniz zaman güncellenebilir.

Sayfanın tamamı tek bir dosyadır: `index.html`. Kod bilmeniz gerekmez. Yalnızca dosyanın en üstündeki **CONFIG** bloğunu düzenlersiniz.

---

## Bölüm 1: İlk kurulum (bir kez yapılır)

### 1. GitHub hesabı açın
Hesabınız yoksa https://github.com/signup adresinden ücretsiz bir hesap açın.

### 2. Kulüp organizasyonunu oluşturun
1. GitHub'a giriş yaptıktan sonra https://github.com/account/organizations/new?plan=free adresine gidin.
2. **Free** planın seçili olduğunu kontrol edin.
3. Organizasyon adına `isikyapayzeka` yazın. QR kodun adresi bu ada bağlı, farklı bir ad yazmayın.
4. İletişim e-postası olarak kulübün e-postasını yazın ve "My personal account" seçeneğini işaretleyin.
5. Kurulumu bitirin. İsterseniz yönetimdeki diğer kişileri **People → Invite member** ile davet edin. Böylece tek bir kişiye bağlı kalmazsınız.

### 3. Depoyu oluşturun
1. Organizasyon sayfasında **Repositories → New repository** düğmesine basın.
2. Owner olarak `isikyapayzeka` seçili olsun.
3. Repository name alanına tam olarak şunu yazın: `isikyapayzeka.github.io`
4. **Public** seçin.
5. **Create repository** düğmesine basın.

### 4. Dosyayı yükleyin
1. Yeni deponun sayfasında **uploading an existing file** linkine basın.
2. `index.html` dosyasını sürükleyip bırakın.
3. Aşağıdaki **Commit changes** düğmesine basın.

### 5. Sayfayı yayına alın
1. Depoda **Settings → Pages** bölümüne gidin.
2. **Source** altında **Deploy from a branch** seçin.
3. **Branch** olarak `main` ve `/ (root)` seçip **Save** düğmesine basın.
4. 1–2 dakika bekleyin. Sayfa şu adreste açılır: https://isikyapayzeka.github.io

Telefonla bir yaka kartının QR'ını okutarak sayfanın açıldığını kontrol edin.

---

## Bölüm 2: Sayfayı güncelleme

1. https://github.com/isikyapayzeka/isikyapayzeka.github.io adresine gidin.
2. `index.html` dosyasına tıklayın.
3. Sağ üstteki **kalem simgesine** (Edit this file) basın.
4. En üstteki `SAYFA AYARLARI (CONFIG)` bloğunda istediğiniz değeri değiştirin.
5. **Commit changes...** düğmesine basın, açılan pencerede yine **Commit changes** deyin.
6. 1–2 dakika içinde sayfa güncellenir. Telefonda eski hâli görürseniz sayfayı yenileyin.

### Yazım kuralları
- Her değer çift tırnak içinde yazılır: `"https://..."`
- Satır sonlarındaki virgülleri silmeyin.
- Bir butonu gizlemek için değerini boşaltın: `""`
- `AYARLARIN SONU` satırının altına dokunmayın.

### Sık yapılan değişiklikler

**Bir link eklemek** (örnek: üye formu hazır oldu):
```
uyeFormu: "https://forms.gle/....",
```

**E-posta eklemek:** `mailto:` yazmanıza gerek yok, adres yeterli.
```
eposta: "kulup@ornek.edu.tr",
```
`sponsorIletisim` alanına da bir e-posta adresi ya da bir form linki yazabilirsiniz.

**WhatsApp:** Kulübün topluluk veya kanal davet linkini yazın. Kişisel telefon numarası yazmayın.

**Yaklaşan etkinlik eklemek:**
```
etkinlik: {
  baslik: "Yapay Zekaya Giriş Atölyesi",
  baslikEn: "Intro to AI Workshop",
  baslangic: "2026-11-05 18:00",
  bitis: "2026-11-05 20:00",
  yer: "Şile Kampüsü, Konferans Salonu",
  yerEn: "Şile Campus, Conference Hall",
  kayitLinki: "https://forms.gle/....",
  aciklama: "",
  aciklamaEn: ""
},
```
- Tarihleri Türkiye saatiyle, `YIL-AY-GÜN SAAT:DAKİKA` biçiminde yazın.
- "Takvime ekle" ve "Google Takvim" butonları bu bilgilerden kendiliğinden oluşur.
- Bitiş saati geçince kart kendiliğinden kalkar ve etkinlik "Geçmiş etkinlikler" listesine linksiz olarak eklenir.
- `etkinlik` alanı bir seferde tek etkinlik tutar. Yeni etkinliği yazmadan önce eskisini aşağıdaki `gecmisEtkinlikler` listesine, Instagram ya da LinkedIn gönderisinin linkiyle ekleyin. Aynı etkinlik iki yerde birden yazılı kalırsa listede yine bir kez görünür.
- Etkinlik yoksa `baslik: ""` yapın, kart görünmez.

**Geçmiş etkinlik eklemek:**
```
gecmisEtkinlikler: [
  { baslik: "Yapay Zekaya Giriş Atölyesi", baslikEn: "Intro to AI Workshop", tarih: "2026-11-05", link: "https://www.instagram.com/p/..." },
  { baslik: "Welcome Etkinliği", baslikEn: "Welcome Event", tarih: "2026-10-08", link: "https://www.instagram.com/reel/..." },
]
```
- Başlıkları kısa tutun, telefonda tek satıra sığsın.
- Sıralama önemli değil, sayfa etkinlikleri en yeniden eskiye kendisi dizer.
- `link` boş bırakılabilir. O zaman satır tıklanmaz, sadece tarih ve başlık görünür.
- Liste boşken "Geçmiş etkinlikler" butonu görünmez.

**İngilizce alanlar:** Sonu `En` ile biten alanlar (`baslikEn`, `yerEn`, `aciklamaEn`) sayfa İngilizce açıldığında görünür. Boş bırakılırsa İngilizce sayfada Türkçesi gösterilir. Butonların ve başlıkların İngilizcesi kodun içinde hazır, onlar için bir şey yapmanız gerekmez.

**Dönem değişince:** `donem: "2027–28",`

### Bir şey bozulursa
Depoda `index.html` → **History** bölümünden önceki sürümü açıp içeriğini geri kopyalayabilirsiniz. Sayfa boş görünüyorsa büyük ihtimalle bir tırnak ya da virgül eksik kalmıştır. Son değiştirdiğiniz satırı kontrol edin.

---

## Notlar
- Sayfa ilk açılışta dil sorar (Türkçe / English). Seçim o telefonda hatırlanır, sağ üstteki düğmeyle değiştirilebilir.
- Google Formlar ve WhatsApp grubu tek dilli kalır. Gerekirse formlara İngilizce açıklama eklenebilir.
- Logolar dosyanın içine gömülüdür, ayrıca yüklemeniz gerekmez.
- Aynı link iki kez yazılırsa sayfada yalnızca bir kez görünür.
- `konum` alanı şu an Google Haritalar'da "Işık Üniversitesi Şile Kampüsü" aramasını açar. Kesin bir konum linkiniz varsa onunla değiştirin.
