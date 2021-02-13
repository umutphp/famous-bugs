# famous-bugs :bug: :honeybee: :ant: :beetle:

![Markdown Linter](https://github.com/umutphp/famous-bugs/workflows/.github/workflows/markdown-linter-action.yml/badge.svg?branch=master) [](./.github/CODE_OF_CONDUCT.md)![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)

Geliştiricilerin faydalı bulabileceği, derlenmiş problemler ve hatalar listesi.

[Çeviriler](#translations) : [🇹🇷](https://github.com/umutphp/famous-bugs/blob/master/README-tr.md)

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->

<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

## İçindekiler

- [Giriş](#introduction)
- [Problemler](#problems)
    - [Instagram'ın Justin Bieber Sorunu](#justin-bieber-problem-of-instagram)
    - [Gangnam Style YouTube'u Bozdu](#gangnam-style-broke-youtube)
    - [Wikimedia'da Bir Çiçek Resmine Gelen Gizemli Trafik](#mysterious-traffic-of-a-flower-image-on-wikimedia)
    - [2000 Yılı Problemi](#year-2000-problem)
    - [NPM Leftpad Olayı](#npm-leftpad-breakage)
    - [Heathrow Terminal 5 Opening](#heathrow-terminal-5-opening)
    - [20 Temmuz 2016 Stack Overflow'un Çöküşü](#stack-overflow-outage-on-july-20-2016)
    - [N+1 Sorgu Problemi](#n1-query-problem)
- [Bugs](#bugs)
    - [The First Bug](#the-first-bug)
    - [The Explosion of the Ariane 5](#the-explosion-of-the-ariane-5)
    - [NASA'nın Mars İklim Uydusunda Metrik Sistem Karmaşası](#metric-system-mess-of-nasas-mars-climate-orbiter)
    - [The Morris Worm](#the-morris-worm)
    - [BT Yüzünden Ölmek](#death-by-it)
    - [The 1990 AT&amp;T Network Collapse](#the-1990-att-network-collapse)
    - [ILOVEYOU Worm](#iloveyou-worm)
    - [The Zune Bug](#the-zune-bug)
- [Translations](#translations)
- [Katkıda Bulunmak İçin](#contributing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

## Introduction

Yazılım geliştiricileri olarak işimizi basitçe hataları düzeltmek ve sorunlara çözüm geliştirmek olarak tanımlayabiliriz. Bu liste, geliştiricilerin yararlı bulabileceği, derlenmiş problemler ve hatalar listesidir. Umarım daha büyük bir değer yaratmak için topluluk odaklı bir liste olur.

## Problems

### Justin Bieber Problem of Instagram

> Bieber bir fotoğraf paylaşırdı ve pek çok takipçisi, Instagram'ın sunucularının yetişemeyeceği şekilde "Like" düğmesine basarlardı.
>
> [Wired.com](https://www.wired.com/2015/11/how-instagram-solved-its-justin-bieber-problem/)

Justin Bieber bir fotoğraf yayınladığında, pek çok "Belieber" fotoğrafı "Beğenecektir" ve bu da çok fazla sayıda bildirim, sorgu ve işleme neden olur . Instagram ekibinin karşılaştığı bu sorun aslında [saldıran sürü sorununun](https://en.wikipedia.org/wiki/Thundering_herd_problem) çok güzel bir örneğidir. Bu sorunun tekrar olmasını önlemek için birçok iyileştirme yaptılar ve bunu bu [makalede](https://instagram-engineering.com/instagration-pt-2-scaling-our-infrastructure-to-multiple-data-centers-5745cbad7834) açıkladılar.

Ek kaynaklar:

- [Saldıran sürü sorunu](https://www.wikiwand.com/en/Thundering_herd_problem)
- [How Instagram Solved Its Justin Bieber Problem](https://www.wired.com/2015/11/how-instagram-solved-its-justin-bieber-problem/)

### Gangnam Style YouTube'u Bozdu

> Bir videonun 32 bitlik bir tam sayıdan büyük sayılarda izleneceğini asla düşünmemiştik.
>
> YouTube

YouTube'un izlenme sayacı daha önce 32 bitlik bir tamsayı kullanıyordu, bu da sayabileceği maksimum olası görüntülemenin 2.147.483.647 olduğu anlamına geliyordu. Ve " [Gangnam Style](https://www.youtube.com/watch?v=9bZkp7q19f0) " 2 milyarlık görüntüleme sayısını aştı. YouTube'da, bir videonun alabileceği maksimum görüntüleme sayısı artık 9,223,372,036,854,775,808 olacak şekilde 64 bit tam sayıya yükseltildi.

### Wikimedia'da Bir Çiçek Resmine Gelen Gizemli Trafik

> 20% of all requests to one of our data centers for media are for this image of a flower. Nobody knows why.
>
> [Chris Albon](https://twitter.com/chrisalbon/status/1358890731981611009)

3 Şubat 2021'de, Wikimedia teknoloji ekibi Hindistan'daki çeşitli ISS'lerden günde yaklaşık 90 milyon istek aldıklarını fark etti. İsteklerin tümü bir resim dosyası içindir (aşağıya bakın). Bunun bu resmi açılış ekranına koymuş bir mobil uygulama olabileceğini varsaydılar. Wikimedia uygulamayı açıklamadı, ancak bunun TikTok yerine kullanılabilecek bir uygulama olabileceğini düşünüldü. Çünkü, Hindistan o sırada TikTok'u tamamen yasaklama kararı almıştı ve bu da insanları alternatif uygulamalar kullanmaya yönlendirmişti. Bu kararla başlayan kelebek etkisi, bunu Wikimedia ve gizemli uygulamanın ekipleri için unutulmayacak bir anıya dönüştürdü.

[](https://en.wikipedia.org/wiki/Symphyotrichum_novi-belgii#/media/File:AsterNovi-belgii-flower-1mb.jpg)

Ek kaynaklar:

- [Phabricator Post](https://phabricator.wikimedia.org/T273741)

### Year 2000 Problem

> ... 2000 yılını 1900 yılından ayırt edilemez hale getiriyor.

2000 Yılı sorunu (Y2K sorunu, Millennium hatası, Y2K hatası, Y2K hatası veya Y2K olarak da bilinir), 2000 yılından başlayan tarihler için takvim verilerinin biçimlendirilmesi ve depolanması nedeniyle oluşan sorunları ifade eder. Bu sorun tüm dünyada yaşandı ve belgelendi. İşte bazı örnekler:

- 1 Ocak 1999'da Singapur'da taksi sayaçları çalışamaz hale geldi.
- 1 Ocak 2000'de Japonya, Onagawa'da, gece yarısından iki dakika sonra bir nükleer santralde alarm çaldı.
- On 1 March 2000, In the United States, the Coast Guard's message processing system was affected.
- Norway and Finland had to change their national identification number, to indicate correctly the century in which a person was born.

Ek kaynaklar:

- [Year 2000 Problem at Wikipedia](https://en.wikipedia.org/wiki/Year_2000_problem)

### NPM Leftpad Olayı

> Github'da yalnızca 10 yıldızlı left-pad olarak adlandırılan 11 satırlık bir npm paketi yayınlanmadı ...  npm'deki en önemli paketlerden bazılarını hata vermeye başladı.
>
> [Reddit](https://www.reddit.com/r/programming/comments/4bjss2/an_11_line_npm_package_called_leftpad_with_only/)

[Azer Koçulu](https://kodfabrik.com/) npm'ye yazdığı basit bir kodu yayınladı ve bu çok popüler oldu. Pek çok proje bu paketi bağımlılık olarak kullandı. 11 Mart'ta, bir mesajlaşma uygulaması olan Kik için çalışan patent ve ticari marka temsilcisinden bir e-posta aldı. KiK ayrıca onun başka bir paketinin adıydı. Kik paketini yeniden adlandırmasını istediler ancak Azer bunu kabul etmedi. Sonra ajans NPM'i bunu yapmaya zorladı ve bunda başarılı oldu. NPM'nin kararından sonra Azer Koçulu, left-pad dahil tüm paketlerini sildi. Daha sonra, dünyadaki birçok JavaScript programcısı "npm ERR! 404 'left-pad' npm is not in the npm registry" hata mesajını almaya başladı.

Ek kaynaklar:

- [Modüllerimi Az Önce Özgürleştirdim](https://kodfabrik.com/journal/i-ve-just-liberated-my-modules)
- [kik, left-pad ve npm](https://blog.npmjs.org/post/141577284765/kik-left-pad-and-npm)

### Heathrow Terminal 5 Opening

> ... herhangi bir nedenle test edilmeyen basit ve gerçek senaryolar.

Heathrow Terminal 5 resmi olarak 14 Mart 2008'de açıldı. Açılış gününde planlandığı gibi çalışmadı, bu nedenle British Airways 34 uçuşu iptal etmek ve bagaj kontrolünü askıya almak zorunda kaldı.

Yeni bagaj taşıma sistemi yazılımı, bazı nedenlerden dolayı test edilmeyen gerçek senaryoları kaldıramadı. Örneğin, mal sahibi bir şeyi unuttuğu için bir bagaj manuel olarak geri taşındı. Bu durumda, program çöktü ve eşya kaydedilmedi. Bagaj işleme her zaman bu tür küçük ayrıntılarla kesintiye uğrardı.

During the following ten days, around 42,000 items weren’t delivered to owners, and over 500 flights were canceled. Check-in to other flights became temporarily unavailable.

Ek kaynaklar:

- [Technical glitches hit T5 opening](http://news.bbc.co.uk/2/hi/uk_news/7314816.stm)
- [Heathrow Terminal 5](https://en.wikipedia.org/wiki/Heathrow_Terminal_5#Opening) at Wikipedia

### 20 Temmuz 2016 Stack Overflow'un Çöküşü

> Regular expression şuydu: ^[\ s\u200c]+|[\ s\u200c]+$ ...
>
> [Çöküş Raporu - 20 Temmuz 2016](https://stackstatus.net/post/147710624694/outage-postmortem-july-20-2016)

20 Temmuz 2016'da StackOverflow, regular expression'lardan birinin Stack Overlfow web sunucularında yüksek CPU tüketmesine neden olan hatalı biçimlendirilmiş bir gönderi nedeniyle 34 dakikalık bir kesinti yaşadı. Bu çok tipik bir regular expression hizmet reddi (ReDoS) saldırısıydı, ancak hatalı biçimlendirilmiş gönderinin bir süre ana sayfada görüntülenmesi nedeniyle gerçekleşti. Dolayısıyla, regular expression kontrolleri (eşleşme veya uyumsuzluk) işlemci kaynaklarını tamamen tüketi. Ana sayfa yük dengeleyiciler tarafından sağlık kontrolü için kullanıldığından, sitenin tamamı kullanılamaz hale geldi.

Ek kaynaklar:

- [Normal İfade Hizmet Reddi (ReDoS) cheat-sheet sayfası](https://levelup.gitconnected.com/the-regular-expression-denial-of-service-redos-cheat-sheet-a78d0ed7d865)
- [Çöküş Raporu - 20 Temmuz 2016](https://stackstatus.net/post/147710624694/outage-postmortem-july-20-2016)

### N+1 Query Problem

> ... öğe n tane ilişkili öğe içerdiğinde n+1 isteğe dönüşür.
>
> [InfoQ](https://www.infoq.com/articles/N-Plus-1/)

N + 1 problemi, kod bir ana öğenin çocuklarını bir ilişkide yüklemeye çalıştığında ortaya çıkar (örneğin, bire çok ilişkiler). Hemen hemen tüm ORM'ler, varsayılan olarak tembel yüklemeyi etkinleştirir. İlişkilerle beraber gelen verilerle bir kayıt listesi oluşturmak istediğinizi varsayın. Ana öğeleri getirmek için bir sorgu ve N ana öğe alt kayıtları için N sorgu (ilişkiden verileri almak için her biri için bir sorgu) yapılır. Tahmin edebileceğiniz gibi, tek bir sorgu yerine N+1 sorguları yapmak, veritabanınızı sorgularla doldurur, bu da kaçınmamız gereken bir şeydir. Çok şükür ki, ORM'ler sorunu oldukça uzun süredir biliyorlar ve buna yerleşik çözümleri vardır. Çözüm aslında basit: geliştirme sırasında, ORM'ye önceden ek verilere ihtiyacınız olduğunu söylemelisiniz (önyükleme).

Ek kaynaklar:

- [N+1 Queries and How to Avoid Them!](https://medium.com/@bretdoucette/n-1-queries-and-how-to-avoid-them-a12f02345be5)

## Bugs

### İlk Hata (Bug)

> First actual case of bug being found.
>
> [Grace Murray Hopper](https://en.wikipedia.org/wiki/Grace_Hopper)

9 Eylül 1947'de [Mark II](https://en.wikipedia.org/wiki/Harvard_Mark_II) (Harvard Üniversitesi'nde) bozuldu. Mühendisler nedeni araştırdılar ve teşhis ettiler. Makineye bir güve girmiş ve Panel F'nin 70 numaralı rölesini kısa devre yapmıştı. Hatayı sayfaya "İlk gerçek hata (bug) bulundu" notuyla eklediler. Bug terimi bu şekilde doğdu.

![First Bug](./assets/images/first_bug.jpg)

Bu sayfa hala Washington'daki [Smithsonian Enstitüsü Ulusal Amerikan Tarihi Müzesi'nde](https://americanhistory.si.edu/collections/search/object/nmah_334663) tutuluyor.

Ek kaynaklar:

- [Harvard Mark II](https://en.wikipedia.org/wiki/Harvard_Mark_II)
- [Grace Hopper](https://en.wikipedia.org/wiki/Grace_Hopper)

### The Explosion of the Ariane 5

> ... 64 bitlik bir real sayı ... 16 bitlik işaretli bir tam sayıya dönüştürüldü.

4 Haziran 1996'da, Avrupa Uzay Ajansı tarafından fırlatılan Ariane 5 roketi, havalanmasından sadece kırk saniye sonra patladı. Roket, 7 milyar dolara mal olan on yıllık bir geliştirme sürecinin ardından ilk yolculuğuna çıkmıştı. İmha edilen roket ve kargosunun değeri 500 milyon dolardı. Kaza, Avrupa'nın uzay programı için önemli bir engeldi.

The horizontal velocity of the rocket with respect to the platform was larger than 32,767, the largest integer storeable in a 16 bit signed integer, and thus the conversion failed.

Ek kaynaklar:

- [Report: Software Design Errors Caused Ariane 5 Explosion](https://apnews.com/article/1d85f290e31cad8532636fcb576f4788)

### NASA'nın Mars İklim Uydusunda Metrik Sistem Karmaşası

Mars İklim Uydusu, 11 Aralık 1998'de Mars iklimini incelemek için NASA tarafından fırlatılan bir robotik uzay misyonuydu. Navigasyon ekibi, hesaplamalarında metrik sistemi kullanırken, uzay aracını tasarlayan ve inşa eden ekip ivme verilerini İngiliz metrik sisteminde sağladı. Newton saniye^2 adı verilen bir kuvvet için ivme okumaları pound-saniye^2 cinsinden ölçülmüştü. Bir anlamda uzay aracı çeviride kayboldu.

Ek kaynaklar:

- [Mars_Climate_Orbiter#Cause_of_failure](https://en.wikipedia.org/wiki/Mars_Climate_Orbiter#Cause_of_failure)

### The Morris Worm

> This was a design flaw ...

Yaratıcısı [Robert Tappan Morris'e göre](https://en.wikipedia.org/wiki/Robert_Tappan_Morris) , zarar vermek için değil, güvenlik açıklarını vurgulamak için yazılmıştı. [Sendmail](https://en.wikipedia.org/wiki/Sendmail) , [finger](https://en.wikipedia.org/wiki/Finger_protocol) , [rsh/rexec](https://en.wikipedia.org/wiki/Berkeley_r-commands) ve zayıf şifrelerde oluşan güvenlik açıklarından yararlanmak için programlanmıştır. Solucanı yaratırken Robert sistem yöneticilerinin solucanı yenmeye çalışmasını önlemek için kendini %14 oranında kopyalayacak ve bilgisayara yanlış pozitif geri bildirim yapacak şekilde programladı. Bu bir tasarım kusuruydu ve etkilenen bilgisayarda kopyalanma bombardımanı ve çökmeler yarattı.

Morris Worm, İnternet üzerinden dağıtılan ilk bilgisayar solucanlarından biri olarak kabul edildi ve ana akım medyanın dikkatini çeken ilk bilgisayar solucanı oldu. Morris Solucanının kaynak kodunu içeren bir disket [Bilgisayar Tarihi Müzesi'nde](https://computerhistory.org/) tutulmaktadır.

Ek kaynaklar:

- [Morris Worm](https://en.wikipedia.org/wiki/Morris_worm)
- [Robert Tappan Morris](https://en.wikipedia.org/wiki/Robert_Tappan_Morris)

### BT Yüzünden Ölmek

> Hastaların "eve taburcu edildiğini" ya da "öldüğünü" belirtmek için bilgisayar kodunda bir rakam kullanıldı.
>
> [Apnews](https://apnews.com/article/6870c9bd785360007b5981f0d5443b19#:~:text=A%20computer%20error%20at%20Saint,of%20other%20patients%20as%20deceased.&text=The%20glitch%20happened%20during%20a,told%20The%20Grand%20Rapids%20Press.)

2002 yılında, Grand Rapids'deki St. Mary's Mercy Tıp Merkezi hatalı bir şekilde 8500 hastanın hasta yönetim yazılımındaki bir aksaklık nedeniyle öldüğünü bildirdi. Yalancı ölüm raporları sadece hastalara değil, sigorta şirketlerine ve sosyal güvenlik bürolarına da gönderildi. Sorunun nasıl giderildiğine dair net bir şekilde belirtildi ancak yönetim yazılımı yine de değiştirildi.

Ek kaynaklar:

- [Hospital Revives Its "Dead" Patients](https://www.baselinemag.com/c/a/Projects-Networks-and-Storage/Hospital-Revives-Its-QTEDeadQTE-Patients)

### The 1990 AT&amp;T Network Collapse

> Sadece bir satır koddaki hata, AT&amp;T'nin ağını birkaç saatliğine kapattı.
>
> [MakeUseOf](https://www.makeuseof.com/tag/worst-programming-mistakes-in-history/)

Bu çöküşten önce, AT&amp;T'nin uzun mesafe ağı güvenilir ve güçlü olarak kabul edilirdi. Ülkenin uzun mesafe trafiğinin %70'inden fazlasını taşıyor ve 115 milyondan fazla telefon görüşmesi yapıyordu. Bu çöküş, AT&amp;T müşterilerinin 75 milyon cevapsız <br>aramaları ve 200.000 havayolu ve otel rezervasyonları iptali nedeniyle telefon ağına güvenen işletmelerin 60 milyon dolarlık kaybıyla sonuçlandı.

Hata, güncellenmiş kurtarma yazılımındaki bir switch ifadesindeki olan if ifadesindeki bir break komutu nedeniyle oluştu. Bütün switch'ler, komşu switch'lerin güvenilir olup olmadığını belirlemeye çalışırken aynı anda hepsi erişilemez hale geldi.

```bash
1  while (ring receive buffer not empty  and side buffer not empty) DO
2    Initialize pointer to first message in side buffer or ring receive buffer
3    get copy of buffer
4    switch (message)
5       case (incoming_message):
6             if (sending switch is out of service) DO
7                 if (ring write buffer is empty) DO
8                     send "in service" to status map
9                 else
10                    break
11            END IF
12            process incoming message, set up pointers to optional parameters
13            break
14      END SWITCH
15   do optional parameter work
```

Ek kaynaklar:

- [The 1990 AT&amp;T Long Distance Network Collapse](https://jonhtaylor.com/the-1990-att-long-distance-network-collapse/)
- [All Circuits are Busy Now: The 1990 AT&amp;T Long Distance Network Collapse](https://users.csc.calpoly.edu/~jdalbey/SWE/Papers/att_collapse.html)

### ILOVEYOU Worm

> The events inspired the song "E-mail" on the Pet Shop Boys' UK top-ten album of 2002, Release, the lyrics of which play thematically on the human desires which enabled the mass destruction of this computer infection.
>
> [Wikipedia](https://en.wikipedia.org/wiki/ILOVEYOU#Impact)

ILOVEYOU solucanı, Onel de Guzman (Manila Filipinler'de bir üniversite öğrencisi) tarafından yaratıldı ve 4 Mayıs 2000'den sonra on milyondan fazla Windows kişisel bilgisayarına bulaştı. Amacı, hizmet için ödeme yapmadan diğer kullanıcıların internet hesaplarını kullanabilmek için şifrelerini çalmaktı. Windows 95'te e-posta eklentilerinde kod çalıştıran bir hata olduğu için solucanı yaratmanın çok kolay olduğunu belirtti.

Başlangıçta, solucanı yalnızca Manila'da çalışacak şekilde tasarladı. Meraktan, bu coğrafi kısıtlamayı kaldırdı ve solucanın dünya çapında yayılmasına izin verdi. Elbette bunun dünya çapında yayılmasını beklemiyordu. Solucan önce Hong Kong'a, sonra Avrupa'ya ve son olarak da Amerika Birleşik Devletleri'ne bulaştı. On gün içinde, elli milyondan fazla bulaşma (dünyadaki internete bağlı bilgisayarların% 10'u) rapor edildi. Pentagon, CIA, Britanya Parlamentosu ve bir çok büyük şirket kendilerini korumak için posta sistemlerini tamamen kapatmaya karar verdi.

Solucan, kullanıcılara kodu değiştirmenin bir yolunu sağladı ve bu, her biri farklı türde zararlar veren yirmi beşten fazla ILOVEYOU varyasyonunun internete yayılmasına izin verdi.

This worm created a public awareness of the real threat of malwares and antivirus software providers entered a golden era of distribution. Aditionally, It helped many people to be more skeptical of emails which were the classic virus delivery systems.

Ek kaynaklar:

- [ILOVEYOU at Wikipedia](https://en.wikipedia.org/wiki/ILOVEYOU)
- [A decade on from the ILOVEYOU bug](https://www.bbc.com/news/10095957)

### The Zune Bug

> Judgment day has arrived for owners of 30GB Zunes...
>
> [ArsTechnica](https://arstechnica.com/information-technology/2008/12/30gb-zunes-prepare-for-new-year-by-locking-up/)

31 Aralık 2008'de birçok Zune Player sahibi, oyuncunun donmaya başladığını bildirmeye başladı. Microsoft'un yanıtı, ertesi güne kadar beklemekti ve donma kendi kendine çözülecek. Nedeni, artık yıllarda sonsuz döngüye neden olan basit bir döngüdü. Artık yıllara bakılmaksızın kodlanmış basit bir döngü kontrol ifadesi bu karışıklığa neden oluyordu.

Here is the problematic loop;

```bash
year = ORIGINYEAR;
while (days > 365)
{
    if (IsLeapYear(year))
    {
        if (days > 366)
        {
            days -= 366;
            year += 1;
        }
    }
    else
    {
        days -= 365;
        year += 1;
    }
}
```

Ek kaynaklar:

- [The Zune Bug](http://bit-player.org/2009/the-zune-bug) At Bit-Player

## Translations

Bu belge birkaç dilde mevcuttur.

| Language | Maintainer | |----------|-----------|--------| | [🇹🇷 Türkçe / Turkish](https://github.com/umutphp/famous-bugs/blob/master/README-tr.md) | [Umut Işık](https://github.com/umutphp) |

Bir çeviriyi güncellemek veya yeni bir dil eklemek isterseniz, [bir PR açmanız yeterlidir](https://github.com/umutphp/famous-bugs/pulls) .

## Katkıda Bulunmak İçin

Lütfen katkıda bulunun! :pray:

Bir hata bildirmek için ya da ekleme yapılması için [Issue](https://github.com/umutphp/famous-bugs/issues/new) açın. Kendiniz yapmak isterseniz [pull request](https://github.com/umutphp/famous-bugs/pulls) açabilirsiniz.

Please read the [Contributing Guidelines](./.github/contributing.md) and the [Code of Conduct](./.github/CODE_OF_CONDUCT.md) documents.
