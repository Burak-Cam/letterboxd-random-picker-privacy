**[English](#english)** · **[Türkçe](#turkce)**

<a id="english"></a>

# Privacy Policy — Cinespin

Cinespin is an independent Chrome extension that picks a film for you from posters you
tick on Letterboxd pages. It is not affiliated with, endorsed by, or connected
to Letterboxd.

**Effective date:** 2026-09-14

This page describes everything the extension does with information while it runs in your
browser — including the handling that happens entirely on your own device. None of it is sent
to the developer or to any third party.

## In short

- The extension has **no server, no analytics, no telemetry and no third parties**. It sends
  nothing to the developer or to anyone else; its only network requests are the
  `letterboxd.com` film-page requests described below, made from your browser to Letterboxd.
- The **developer sees nothing**. There is no channel — technical or otherwise — through which
  your films, filters or picks could reach the developer.
- It is **read-only** towards your Letterboxd account: it never writes, rates, logs, likes or
  changes anything there.

## What the extension reads

When you activate it on a Letterboxd page (from the toolbar popup or from the one-time setup
tip, or automatically if you turned on *Always enable on Letterboxd*), the extension reads the poster grid that Letterboxd
has already shown you: each film's Letterboxd identifier, its address on `letterboxd.com`,
its title and its poster image address. Building your selection pool this way costs **zero**
network requests — the checkboxes read the page and nothing else.

Before you activate it, the only visible thing the extension does on a supported page is show a
one-time setup tip at the bottom of the page. The tip reads nothing from the page and makes no
requests.

To tell which kind of Letterboxd page is open (a watchlist, a list, a filmography and so on),
the extension looks at the page's address. On a member's pages that address includes the
member's username — yours, on your own watchlist. The extension only compares that part of the
address against a fixed list of Letterboxd section names; it never stores your username and
never sends it anywhere. The extension's code never reads your Letterboxd password or cookies.

## Requests to letterboxd.com/film/*

Only when you actually use a metadata filter (year, runtime, genre or rating), the extension
fetches the film pages it needs from `letterboxd.com/film/*` to learn those four values.

- These requests are sent **from your own browser, with your own Letterboxd session
  cookies**, exactly as when you open those film pages yourself. The browser attaches your
  existing session; the extension's code does not read it.
- Because of this, the requests are attributed to **your own account**, not to the developer.
  To Letterboxd they look like you visiting those film pages. Letterboxd's own privacy policy
  governs what Letterboxd does with page visits.
- Nothing about these requests, or their results, is forwarded anywhere else.

The request budget is an ethical limit, written against your account's interests:

- building the pool costs **0** requests;
- metadata is fetched only when a metadata filter is actually used;
- fetching uses **rejection sampling** — it stops at the first film that matches, rather than
  fetching the whole pool;
- at most **3** concurrent requests, at least **300 ms** apart, and at most **50** requests per
  spin;
- paths disallowed in Letterboxd's `robots.txt` are never requested.

## What is stored, and where

**Film metadata — `chrome.storage.local`.** The year, runtime, genres and Letterboxd rating
fetched for a film are written **only** to `chrome.storage.local`, the extension's private
storage inside your browser profile. Each film has its own entry, keyed by its Letterboxd
identifier, together with the time it was saved (used to refresh the rating after 30 days).
This cache exists so the same film page is not requested twice. It is never sent anywhere.

**Two settings — `chrome.storage.local`.** (1) Whether *Always enable on Letterboxd* is on, and
(2) whether the one-time setup tip has already been answered (you enabled the extension from it
or chose *Don't show again*). Each is a single true/false value.

**Your selection pool and filter values — the tab's session storage.** The films you tick
(identifier, address, title, poster address) and the filter values you set are kept in the
`sessionStorage` of that Letterboxd tab, so they survive navigation within the tab.
**The pool resets when the tab is closed** — it is not permanent and is never written to
`chrome.storage.local`. It contains only what the Letterboxd page itself already displayed.

Nothing else is stored.

## What is never done

- Apart from the `letterboxd.com` film-page requests described above, no request is made to
  any server. No data is sent to the developer, an analytics service, an advertising
  platform, a data broker or any other third party. There is no backend.
- No data is sold, transferred or used for any purpose other than picking a film from your
  pool — the extension's single purpose.
- No data is used for creditworthiness or lending purposes.
- No code is loaded from outside the extension package.

## Permissions

The extension asks for as little as possible, and anything absent from its manifest is absent
on purpose:

- `permissions` is exactly `storage` — used only for the metadata cache and the two settings
  described above;
- no `host_permissions` entry; host access comes only from the content-script match on
  letterboxd.com;
- no background service worker;
- a single narrow content-script match: `https://letterboxd.com/*` and
  `https://www.letterboxd.com/*`.

## How to delete your data

- **Clear the cache:** open the extension's toolbar popup and click *Clear metadata cache*.
- **Remove everything:** uninstalling the extension deletes its `chrome.storage.local` area —
  the whole metadata cache and both settings.
- **The pool:** close the Letterboxd tab. The pool is limited to the lifetime of the tab.

## Statistics the Chrome Web Store provides

Like every Chrome Web Store item, the developer can see aggregate statistics that Google's
store produces (for example, install counts). They come from the Chrome Web Store, not from the
extension, and contain nothing about your Letterboxd activity.

## Changes to this policy

If this policy changes, the new version will be published at this same address with a new
effective date.

## Contact

Questions about this policy: burakcam.dev@gmail.com

## Support

Bug reports and support: <https://github.com/Burak-Cam/letterboxd-random-picker-privacy/issues>

## Limited Use

The use of information received by Cinespin complies with the Chrome Web Store
User Data Policy, including the Limited Use requirements.

---

<a id="turkce"></a>

# Gizlilik Politikası — Cinespin

Cinespin, Letterboxd sayfalarında işaretlediğin posterler arasından senin için bir film seçen
bağımsız bir Chrome eklentisidir. Letterboxd ile bir bağlantısı, ondan bir
onayı yoktur.

**Yürürlük tarihi:** 2026-09-14

Bu sayfa, eklentinin tarayıcında çalışırken bilgilerle yaptığı her şeyi anlatır — tamamen
kendi cihazında gerçekleşen işlemler dahil. Bunların hiçbiri geliştiriciye ya da herhangi bir
üçüncü tarafa gönderilmez.

## Kısaca

- Eklentinin **sunucusu, analitiği, telemetrisi ve üçüncü tarafı yoktur**. Geliştiriciye ya
  da başka birine hiçbir şey göndermez; attığı tek ağ istekleri, aşağıda anlatılan ve
  tarayıcından Letterboxd'a giden `letterboxd.com` film sayfası istekleridir.
- **Geliştirici hiçbir şey görmez.** Filmlerinin, filtrelerinin ya da seçimlerinin
  geliştiriciye ulaşabileceği teknik ya da başka bir kanal yoktur.
- Letterboxd hesabına karşı **okuma-yalnızcadır**: orada hiçbir şey yazmaz, puanlamaz,
  günlüğe eklemez, beğenmez ya da değiştirmez.

## Eklenti neyi okur

Bir Letterboxd sayfasında eklentiyi etkinleştirdiğinde (araç çubuğu açılır penceresinden ya da
tek seferlik kurulum ipucundan, veya *Letterboxd'da her zaman etkin* seçeneğini açtıysan
kendiliğinden), eklenti Letterboxd'un sana
zaten gösterdiği poster ızgarasını okur: her filmin Letterboxd kimliği, `letterboxd.com`
üzerindeki adresi, adı ve poster görselinin adresi. Havuzu bu şekilde kurmak **sıfır** ağ
isteği maliyetlidir — onay kutuları yalnızca sayfayı okur.

Etkinleştirmeden önce eklentinin desteklenen bir sayfada yaptığı tek görünür şey, sayfanın
altında tek seferlik bir kurulum ipucu göstermektir. İpucu sayfadan hiçbir şey okumaz ve hiçbir
istek atmaz.

Hangi tür Letterboxd sayfasının açık olduğunu (watchlist, liste, filmografi vb.) anlamak için
eklenti sayfanın adresine bakar. Bir üyenin sayfalarında bu adres o üyenin kullanıcı adını
içerir — kendi watchlist'inde seninkini. Eklenti adresin bu kısmını yalnızca Letterboxd'un
sabit bölüm adlarından oluşan bir listeyle karşılaştırır; kullanıcı adını asla saklamaz ve
hiçbir yere göndermez. Eklentinin kodu Letterboxd parolanı ya da çerezlerini asla okumaz.

## letterboxd.com/film/* istekleri

Eklenti, yalnızca bir metadata filtresini (yıl, süre, tür ya da puan) gerçekten kullandığında,
bu dört değeri öğrenmek için ihtiyaç duyduğu film sayfalarını `letterboxd.com/film/*`
adresinden çeker.

- Bu istekler **senin kendi tarayıcından, senin kendi Letterboxd oturum çerezlerinle** gider —
  tıpkı o film sayfalarını kendin açtığında olduğu gibi. Mevcut oturumunu isteğe tarayıcı
  ekler; eklentinin kodu onu okumaz.
- Bu yüzden istekler geliştiricinin değil, **senin kendi hesabına** yazılır. Letterboxd'un
  gözünde bunlar senin o film sayfalarını ziyaret etmen gibi görünür. Letterboxd'un sayfa
  ziyaretleriyle ne yaptığı Letterboxd'un kendi gizlilik politikasına tabidir.
- Bu isteklerle ya da sonuçlarıyla ilgili hiçbir şey başka bir yere iletilmez.

İstek bütçesi bir etik sınırdır; hesabının çıkarı gözetilerek yazılmıştır:

- havuz kurmak **0** istek maliyetlidir;
- metadata ancak bir metadata filtresi gerçekten kullanıldığında çekilir;
- çekim **rejection sampling** (reddetme örneklemesi) ile yapılır — havuzun tamamını değil,
  uyan ilk filmi bulana kadar çeker;
- en fazla **3** eşzamanlı istek, aralarında en az **300 ms**, çevirme başına en fazla **50**
  istek;
- Letterboxd'un `robots.txt` dosyasında Disallow olan yollar hiç çağrılmaz.

## Ne saklanır, nerede

**Film metadata'sı — `chrome.storage.local`.** Bir film için çekilen yıl, süre, türler ve
Letterboxd puanı **yalnızca** `chrome.storage.local`'a, yani eklentinin tarayıcı profilindeki
kendine ait depolama alanına yazılır. Her filmin Letterboxd kimliğiyle anahtarlanmış ayrı bir
kaydı vardır; kayıtla birlikte kaydedildiği an da tutulur (puanı 30 gün sonra tazelemek için).
Bu önbellek, aynı film sayfasının iki kez istenmemesi için vardır. Hiçbir yere gönderilmez.

**İki ayar — `chrome.storage.local`.** (1) *Letterboxd'da her zaman etkin* seçeneğinin açık olup
olmadığı ve (2) tek seferlik kurulum ipucunun yanıtlanıp yanıtlanmadığı (eklentiyi ondan
etkinleştirdin ya da *Bir daha gösterme*'yi seçtin). Her biri tek bir doğru/yanlış değeridir.

**Seçim havuzun ve filtre değerlerin — sekmenin oturum deposu.** İşaretlediğin filmler
(kimlik, adres, ad, poster adresi) ve ayarladığın filtre değerleri o Letterboxd sekmesinin
`sessionStorage` alanında tutulur; böylece sekme içinde gezinirken kaybolmazlar.
**Havuz sekme kapanınca sıfırlanır** — kalıcı değildir ve `chrome.storage.local`'a asla
yazılmaz. Yalnızca Letterboxd sayfasının zaten gösterdiği bilgileri içerir.

Başka hiçbir şey saklanmaz.

## Asla yapılmayanlar

- Yukarıda anlatılan `letterboxd.com` film sayfası istekleri dışında hiçbir sunucuya istek
  atılmaz. Hiçbir veri geliştiriciye, bir analitik hizmetine, reklam platformuna, veri
  simsarına ya da başka herhangi bir üçüncü tarafa gönderilmez. Backend yoktur.
- Hiçbir veri satılmaz, aktarılmaz ya da havuzundan bir film seçmek dışında — eklentinin tek
  amacı — bir amaçla kullanılmaz.
- Hiçbir veri kredi değerliliği ya da borç verme amacıyla kullanılmaz.
- Eklenti paketinin dışından hiçbir kod yüklenmez.

## İzinler

Eklenti mümkün olan en az şeyi ister; manifest'te olmayan her şey bilerek yoktur:

- `permissions` tam olarak `storage` — yalnızca yukarıda anlatılan metadata önbelleği ve iki
  ayar için kullanılır;
- `host_permissions` girdisi yoktur; host erişimi yalnızca letterboxd.com content script
  eşleşmesinden gelir;
- arka plan service worker'ı yoktur;
- tek ve dar bir content script eşleşmesi: `https://letterboxd.com/*` ve
  `https://www.letterboxd.com/*`.

## Verini nasıl silersin

- **Önbelleği temizle:** eklentinin araç çubuğu penceresini aç ve *Önbelleği temizle*'ye bas.
- **Her şeyi kaldır:** eklentiyi kaldırmak `chrome.storage.local` alanını siler — tüm
  metadata önbelleğini ve iki ayarı da.
- **Havuz:** Letterboxd sekmesini kapat. Havuz sekmenin ömrüyle sınırlıdır.

## Chrome Web Store'un sağladığı istatistikler

Her Chrome Web Store öğesinde olduğu gibi geliştirici, Google'ın mağazasının ürettiği toplu
istatistikleri (örneğin kurulum sayısı) görebilir. Bunlar eklentiden değil Chrome Web
Store'dan gelir ve Letterboxd etkinliğine dair hiçbir şey içermez.

## Bu politikadaki değişiklikler

Bu politika değişirse yeni sürüm aynı adreste, yeni bir yürürlük tarihiyle yayımlanır.

## İletişim

Bu politikayla ilgili sorular: burakcam.dev@gmail.com

## Destek

Hata bildirimi ve destek: <https://github.com/Burak-Cam/letterboxd-random-picker-privacy/issues>

## Limited Use

Cinespin tarafından alınan bilgilerin kullanımı, Limited Use şartları dahil olmak üzere
Chrome Web Store Kullanıcı Verileri Politikası'na uygundur.
