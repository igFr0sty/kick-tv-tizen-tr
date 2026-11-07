# Kick TV TR

**Türkçe** · [English](README.en.md)

Tizen işletim sistemli Samsung TV'ler için resmi olmayan Kick uygulaması. [corekill'in Kick TV uygulamasına](https://github.com/corekill/kick-tv-tizen) takip ekranı ve Türkçe desteği ekler.

> Bu proje Kick, 7TV veya Samsung ile bağlantılı değildir, onlar tarafından desteklenmez. Topluluk çatallamasıdır.

## Bu sürümün eklediği özellikler

- **Takip Edilenler ekranı:** İlk açılan bölümdür. Yalnızca canlı kanalları gösterir ve izleyici sayısına göre sıralar.
- **Hesap eşitleme (isteğe bağlı):** Takip listeni Kick hesabından alır ve kendiliğinden yeniler.
- **Yerel liste:** Hesap bağlamadan kanalları **+ Takip et** ile kendin ekleyebilirsin.
- **Türkçe arayüz:** TV dili Türkçeyse Türkçe, değilse İngilizce açılır.
- **Türkçe yayın filtresi:** Dil seçeneklerine eklendi. Türkçe TV'lerde varsayılan olarak seçili gelir.
- **Otomatik seçim:** Açılışta ilk canlı kanal seçili gelir.

Oynatma, kalite seçimi, arama, canlı sohbet ve 7TV emojileri orijinal projeden gelir.

## Orijinalden farkları

- Ayrı bir uygulama olarak kurulur (`KckTvTr001.KickTVTR`), yani orijinalin yanında durabilir.
- Orijinaldeki hesap girişi, kullanım sayacı ve tanılama kaldırıldı, çünkü bunlar orijinal yazarın sunucusunu kullanıyor. Bu sürümün kendi sunucusu yoktur.

## Kurulum

1. TV'de **Uygulamalar**'ı aç, **123** tuşuna bas ve `12345` gir.
2. **Geliştirici Modu**'nu aç, **Host PC IP** alanına bilgisayarının yerel IP adresini yaz.
3. Samsung logosu çıkana kadar güç tuşuna basılı tutarak TV'yi yeniden başlat.
4. [Sürümler](../../releases/latest) sayfasından `KickTV.wgt` dosyasını indir.
5. [Apps2Samsung](https://github.com/Apps2Samsung/Apps2Samsung)'da **Custom WGT File**'ı seç, dosyayı ve TV'ni seç, **Download & Install**'a bas.

## Kick hesabını bağlama (isteğe bağlı)

**Önce bunu oku.** Kick'in resmi API'sinde takip listesi yok ([açık talep](https://github.com/KickEngineering/KickDevDocs/issues/87)). Bu yüzden hesap eşitleme, Kick'in belgelenmemiş bir adresini ve tarayıcı oturum anahtarını kullanır.

- Oturum anahtarı Kick hesabına tam erişim sağlar. Kimseyle paylaşma, hiçbir siteye yapıştırma.
- Anahtar TV'de düz metin olarak saklanır ve yalnızca `kick.com`'a gönderilir.
- Kick bu adresi her an değiştirebilir. O zaman uygulama güncellenene kadar eşitleme durur.
- Bu yöntem Kick tarafından resmi olarak desteklenmez. Sorumluluk sana aittir.

Bağlamak için:

1. Bilgisayarda tarayıcıdan kick.com'a giriş yap.
2. `F12` tuşuna bas, **Application → Cookies → https://kick.com** yolunu izle.
3. `session_token` satırının **Value** değerini kopyala.
4. Uygulamada **Düzenle**'ye bas, anahtarı **Kick oturum anahtarı** alanına gir ve **Hesabı bağla**'ya bas.

USB klavye bu işi çok kolaylaştırır. TV'yi başkasına vermeden önce **Bağlantıyı kes**'e bas.

## Derleme

```bash
./scripts/build.sh
```

Paket `dist/KickTV.wgt` olarak oluşur. TV'ye özel imzalanması gerekir; Apps2Samsung bunu kurulum sırasında yapar.

## Emeği geçenler ve lisans

Bu proje, corekill ve katkıda bulunanların hazırladığı [corekill/kick-tv-tizen](https://github.com/corekill/kick-tv-tizen) üzerine kuruludur. Lütfen orijinal projeyi de destekle.

MIT Lisansı; ayrıntılar için [LICENSE](LICENSE) dosyasına bak. Kick, 7TV ve Samsung adları ile markaları sahiplerine aittir ve bu lisansın kapsamında değildir.
