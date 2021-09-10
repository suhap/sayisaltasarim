# 3.1 Giriş
Son bölümde, birleşimsel mantığın nasıl analiz edilip tasarlanacağını gösterdik. Birleşimsel mantığın çıktısı yalnızca mevcut giriş değerlerine bağlıdır. Doğruluk tablosu veya Boole denklemi verildiğinde, gereklilikleri karşılamak için optimize edilmiş bir devre oluşturabiliriz. 

Bu bölümde, sıralı mantığı analiz edip tasarlayacağız. Sıralı mantığın çıktıları hem mevcut hem de önceki girdi değerlerine bağlıdır. Dolayısıyla, sıralı mantık hafızaya sahiptir. Sıralı mantık, önceki belirli girdileri açıkça hatırlayabilir veya önceki girdileri, sistemin durumu adı verilen daha küçük bir bilgi miktarına dömüştürür. Bir dijital sıralı devrenin durumu, devrenin gelecekteki davranışını açıklamak için gerekli geçmişle ilgili tüm bilgileri içeren, durum değişkenleri adı verilen bir bit kümesidir.

Bölüm, bir bitlik durumu depolayan basit ardışık devreler olan lacth ve flip-flop inceleyerek başlar. Genel olarak, sıralı devreleri analiz etmek karmaşıktır. Tasarımı basitleştirmek için, yalnızca kombinasyonel mantık ve devrenin durumunu içeren flip-flop sıralarından oluşan eşzamanlı sıralı devreler inşa etmek için kendimizi disipline ediyoruz. Bölüm, ardışık devreleri tasarlamanın kolay bir yolu olan sonlu durum makinelerini açıklamaktadır. Son olarak, sıralı devrelerin hızını analiz ediyoruz ve hızı artırmanın bir yolu olarak paralelliği tartışıyoruz.

# 3.2 Mandallar ve flip-flop lar
Belleğin temel yapı taşı, iki kararlı duruma sahip bir öğedir. Şekil sol, bir döngüye bağlanmış bir çift eviriciden oluşan basit bir iki durumlu elemanı göstermektedir. Şekil 3.1, simetriyi vurgulamak için aynı devreyi yeniden çizdi. tersleyiciler çapraz bağlanmıştır, yani I1'in girişi I2'nin çıkışıdır ve bunun tersi de geçerlidir. Devrenin girişi yoktur, ancak Q ve Q’ olmak üzere iki çıkışı vardır. Bu devreyi analiz etmek, döngüsel olduğu için kombinasyonel bir devreyi analiz etmekten farklıdır: Q, Q’ ya bağlıdır ve Q’, Q ya bağlıdır.

![şekil3.1](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-1.png)

İki durumu ele alalım, Q, 0 veya Q, 1'dir. Her bir durumun sonuçları üzerinde çalışarak, elimizde:

Durum I: Q = 0
Şekil 3.2 (a) 'da gösterildiği gibi, I2 bir YANLIŞ giriş, Q alır, bu nedenle Q’ üzerinde bir DOĞRU çıktı üretir: I1 bir DOĞRU girdi alır, Q’, bu nedenle Q üzerinde YANLIŞ çıktı üretir. Bu, orijinal varsayımla tutarlıdır. Bu Q = 0, dolayısıyla durumun kararlı olduğu söyleniyor.

Durum II: Q = 1
Şekil 3.2 (b) 'de gösterildiği gibi, I2 bir DOĞRU girdi alır ve bir Q' YANLIŞ çıktı: I1 bir YANLIŞ girdi alır ve bir DOĞRU üretir Q üzerinde çıktı. Bu yine kararlı.

![şekil3.2](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-2.png)


Çapraz bağlı invertörlerin iki kararlı durumu olduğundan, Q = 0 ve Q = 1, devrenin iki kararlı olduğu söylenir. İnce bir nokta, devrenin her iki çıkışının da yaklaşık olarak 0 ile 1 arasında üçüncü bir olası duruma sahip olmasıdır. Buna yarı kararlı durum denir ve Bölüm 3.5.4'te tartışılacaktır.

N kararlı duruma sahip bir eleman, log2N bit bilgi taşır, böylece iki durumlu bir eleman bir bit depolar. Çapraz bağlanmış eviricilerin durumu tek bir ikili durum değişkeni olan Q'da bulunur. Q'nun değeri bize devrenin gelecekteki davranışını açıklamak için gerekli olan geçmiş hakkında her şeyi anlatır. Spesifik olarak, eğer Q = 0 ise sonsuza kadar 0 olarak kalacak ve Q = 1 ise sonsuza kadar 1 kalacaktır. Devrenin başka bir Q’ düğümü vardır, ancak Q’ herhangi bir ek bilgi içermez çünkü Q biliniyorsa, Q’ da bilinir. Öte yandan Q’, durum değişkeni için de kabul edilebilir bir seçimdir.

Sıralı bir devreye güç ilk uygulandığında, başlangıç durumu bilinmemektedir ve genellikle öngörülemez. Devre her açıldığında farklılık gösterebilir.

Çapraz bağlanmış invertörler biraz bilgi depolayabilmesine rağmen, pratik değildir çünkü kullanıcının durumu kontrol etmek için herhangi bir girişi yoktur. Bununla birlikte, mandallar ve flip-floplar gibi diğer iki dengeli elemanlar, durum değişkeninin değerini kontrol etmek için girdiler sağlar. Bu bölümün geri kalanı bu devreleri ele almaktadır.

## 3.2.1 SR Latch
En basit sıralı devrelerden biri, Şekilde 3.3 gösterildiği gibi, iki çapraz bağlı NOR geçidinden oluşan SR mandalıdır. Mandalın S ve R olmak üzere iki girişi ve Q ve Q’ olmak üzere iki çıkışı vardır: SR mandalı çapraz bağlanmış invertörlere benzer, ancak durumu, Q çıkışını ayarlayan ve sıfırlayan S ve R girişleri aracılığıyla kontrol edilebilir. 

![şekil3.3](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-3.png)

Tanıdık olmayan bir devreyi anlamanın iyi bir yolu, doğruluk tablosunu çalışmaktır, böylece başladığımız yer burasıdır. Bir NOR geçidinin herhangi bir giriş TRUE olduğunda bir FALSE çıkışı ürettiğini hatırlayın. Olası dört R ve S kombinasyonunu düşünün.

Durum I: R = 1, S = 0
N1, en az bir DOĞRU girdi, R görür, bu nedenle Q'da YANLIŞ çıktı üretir. N2 hem Q hem de S YANLIŞ'ı görür, bu nedenle Q'  DOĞRU çıktı üretir:

Durum II: R = 0, S = 1
N1, 0 ve Q' girişlerini alıyor: Henüz Q' bilmediğimiz için, Q çıkışını belirleyemiyoruz. N2, en az bir DOĞRU girdi, S alıyor, bu nedenle Q' YANLIŞ bir çıktı üretiyor: Şimdi N1'i yeniden ziyaret edebiliriz , her iki girişin de YANLIŞ olduğunu bilerek, Q çıktısı DOĞRU'dur.

Durum III: R = 1, S = 1
N1 ve N2'nin her ikisi de en az bir DOĞRU girdi (R veya S) görür, bu nedenle her biri bir YANLIŞ çıktı üretir. Dolayısıyla Q ve Q'  ikisi de YANLIŞ.

Durum IV: R = 0, S = 0
N1, 0 ve Q' girdilerini alır: Henüz Q' bilmediğimiz için çıktıyı belirleyemiyoruz. N2, 0 ve Q girdilerini alır. Henüz Q bilmediğimiz için çıktıyı belirleyemiyoruz. Şimdi sıkıştık. Bu, çapraz bağlanmış invertörleri anımsatmaktadır. Ancak Q 0 veya 1 değerelerini aldığını biliyoruz. Dolayısıyla, bu alt durumların her birinde ne olduğunu kontrol ederek sorunu çözebiliriz.

Durum IVa: Q = 0
S ve Q YANLIŞ olduğundan, N2, Şekil 3.4 (a) 'da gösterildiği gibi, Q’ üzerinde bir DOĞRU çıktı üretir. Şimdi N1 bir DOĞRU girdi, Q’ alır, dolayısıyla çıktısı, Q, bizim varsaydığımız gibi YANLIŞ olur.

Durum IVb: Q = 1
Q DOĞRU olduğu için, N2, Şekil 3.4 (b) 'de gösterildiği gibi, Q’ üzerinde YANLIŞ bir çıktı üretir. Şimdi N1, R ve Q olmak üzere iki FALSE girdisi alıyor, dolayısıyla çıktısı, Q, varsaydığımız gibi DOĞRU.

![şekil3.4](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-4.png)

Tüm bunları bir araya getirerek, Q'nun bilinen bir önceki değerinin olduğunu varsayalım, Durum IV'e girmeden önce Qprev adını vereceğiz. Qprev 0 veya 1'dir ve sistemin durumunu temsil eder. R ve S 0 olduğunda, Q hatırlayacaktır bu eski değer, Qprev ve Q’ onun tamamlayıcısı olacaktır, Q’prev: Bu devre hafızaya sahiptir.

Şekil 3.5'teki doğruluk tablosu bu dört durumu özetlemektedir. S ve R girişleri Ayarla ve Sıfırla anlamına gelir. Bir bit ayarlamak, onu DOĞRU yapmak demektir. Bir biti sıfırlamak, YANLIŞ yapmak demektir. Çıktılar, Q ve Q’, normalde tamamlayıcıdır. R ileri sürüldüğünde, Q 0'a sıfırlanır ve Q’ bunun tersini yapar. S ileri sürüldüğünde, Q 1'e ayarlanır ve Q’ bunun tersini yapar. Her iki girdi de belirtilmediğinde, Q eski değeri olan Qprev'i hatırlar. Hem S hem de R'yi aynı anda ileri sürmek pek bir anlam ifade etmiyor çünkü bu, mandalın aynı anda ayarlanıp sıfırlanması gerektiği anlamına geliyor ki bu imkansız. Zayıf karışık devre, her iki çıkışı da 0 yaparak yanıt verir.

![şekil3.5](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-5.png)

SR mandalı, Şekil 3.6'daki sembol ile temsil edilmektedir. Sembolü kullanmak, soyutlama ve modülerliğin bir uygulamasıdır. Farklı mantık kapıları veya transistörler kullanmak gibi bir SR mandalı oluşturmanın çeşitli yolları vardır. Bununla birlikte, Şekil 3.5'teki doğruluk tablosu ve Şekil 3.6'daki sembol ile belirtilen ilişkiye sahip herhangi bir devre elemanına SR mandalı denir.

![şekil3.6](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-6.png)

Çapraz bağlanmış invertörler gibi, SR mandalı, Q'da depolanan bir bitlik durumu olan iki durumlu bir elemandır. Bununla birlikte, durum S ve R girişleri aracılığıyla kontrol edilebilir. R ileri sürüldüğünde, durum 0'a sıfırlanır. S ileri sürüldüğünde, durum 1'e ayarlanır. Hiçbiri ileri sürülmediğinde, durum eski değerini korur. Girişlerin tüm geçmişinin tek durum değişkeni Q tarafından açıklanabileceğine dikkat edin.Geçmişte hangi ayarlama ve sıfırlama modeli olursa olsun, SR mandalının gelecekteki davranışını tahmin etmek için gereken tek şey bunun en yakın zamanda olup olmadığıdır. ayarlayın veya sıfırlayın.

## 3.2.2 D Latch
SR mandalı gariptir çünkü hem S hem de R aynı anda öne sürüldüğünde garip davranır. Dahası, S ve R girişleri ne ve ne zaman meselelerini birleştirir. Girdilerden birini ileri sürmek sadece durumun ne olması gerektiğini değil, aynı zamanda ne zaman değişmesi gerektiğini de belirler. Bu sorular ne, ne zaman ayrıldığında devrelerin tasarlanması kolaylaşır. Şekil 3.7(a) ortadaki mandal bu sorunları çözer. İki girişi vardır. Veri girişi D, bir sonraki durumun ne olması gerektiğini kontrol eder. Saat girişi, CLK, durumun ne zaman değişmesi gerektiğini kontrol eder.

Yine, Şekil 3.7 (b) 'de verilen doğruluk tablosunu yazarak mandalı analiz ediyoruz. Kolaylık sağlamak için önce D, S ve R dahili düğümlerini ele alıyoruz. CLK = 0 ise, D'nin değerine bakılmaksızın hem S hem de R YANLIŞ'tır. CLK = 1 ise, D'nin değerine bağlı olarak bir AND geçidi DOĞRU ve diğeri YANLIŞ üretecektir. S ve R verildiğinde, Q ve Q’ Şekil 3.5 kullanılarak belirlenir. CLK = 0 olduğunda, Q'nun eski değeri olan Qprev'i hatırladığını gözlemleyin. CLK = 1 olduğunda, Q = D. Her durumda, mantıksal göründüğü gibi Q’, Q tamamlayıcısıdır. D mandalı, eşzamanlı olarak ileri sürülen R ve S girişlerinin garip durumunu önler.

Hepsini bir araya getirdiğimizde, verilerin mandaldan ne zaman aktığını saatin kontrol ettiğini görüyoruz. CLK = 1 olduğunda, mandal şeffaftır. D'deki veriler, sanki mandal sadece bir arabellekmiş gibi Q'ya akar. CLK = 0 olduğunda, mandal donuktur. Yeni verilerin Q'ya akmasını engeller ve Q eski değeri korur. Bu nedenle, D mandalı bazen şeffaf bir mandal veya seviyeye duyarlı bir mandal olarak adlandırılır. D mandalı sembolü Şekil 3.7 (c) 'de verilmiştir.

D mandalı, CLK = 1 iken durumunu sürekli olarak günceller. Bu bölümün ilerleyen kısımlarında, durumu yalnızca belirli bir zamanda güncellemenin faydalı olduğunu göreceğiz. Bir sonraki bölümde açıklanan D flip-flop tam da bunu yapıyor.

![şekil3.7](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-7.png)

## 3.2.3 D FIip-Flop
Bir D flip-flop, Şekil 3.8(a) gösterildiği gibi, tamamlayıcı saatler tarafından kontrol edilen iki arka arkaya D mandalından oluşturulabilir. İlk mandala, L1, ana olarak adlandırılır. İkinci mandala, L2, köle olarak adlandırılır. Aralarındaki düğüm N1 olarak adlandırılır. D flip-flopu için bir sembol Şekil 3.8(b) verilmiştir. Q’ çıktısına ihtiyaç duyulmadığında, sembol genellikle Şekil 3.8(c) olduğu gibi yoğunlaştırılır.

![şekil3.8](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-8.png)


CLK = 0 olduğunda, ana mandal şeffaftır ve ikincil kilit donuktur. Bu nedenle, D'deki değer ne olursa olsun N1'e yayılır. CLK = 1 olduğunda, master donuklaşır ve slave şeffaf hale gelir. N1'deki değer Q'ya yayılır, ancak N1, D'den kesilir. Bu nedenle, saat 0'dan 1'e yükselmeden hemen önce D'de olan değer, saat yükseldikten hemen sonra Q'ya kopyalanır. Diğer tüm zamanlarda, Q eski değerini korur, çünkü D ile Q arasındaki yolu her zaman kapatan donuk bir mandal vardır.

Başka bir deyişle, bir D flip-flopu, saatin yükselen kenarında D'yi Q'ya kopyalar ve diğer tüm zamanlarda durumunu hatırlar. Bu tanımı ezberleyene kadar yeniden okuyun; Yeni başlayan dijital tasarımcıların en yaygın sorunlarından biri, bir flip-flop un ne yaptığını unutmaktır. Saatin yükselen kenarı, kısalık için genellikle sadece saat kenarı olarak adlandırılır. D girişi, yeni durumun ne olacağını belirtir. Saat kenarı, durumun ne zaman güncellenmesi gerektiğini gösterir.

Bir D flip-flop aynı zamanda bir master-slave flip-flop, bir edge tetiklemeli flip-flop veya bir pozitif kenar-tetiklemeli flip-flop olarak da bilinir. Sembollerdeki üçgen, kenarla tetiklenen bir saat girişini belirtir. Q’ çıktısı genellikle ihtiyaç duyulmadığında ihmal edilir.

Örnek 3.1 DÖNER FLOP TRANSİSTÖR SAYISI
Bu bölümde açıklanan D flip-flop'u oluşturmak için kaç transistöre ihtiyaç vardır?

Çözüm: Bir NAND veya NOR geçidi dört transistör kullanır. NOT geçidi iki transistör kullanır. Bir AND geçidi bir NAND ve bir NOT'dan oluşturulur, bu nedenle altı transistör kullanır. SR mandalı iki NOR geçidi veya sekiz transistör kullanır. D mandalı bir SR mandalı, iki AND geçidi ve bir NOT geçidi veya 22 transistör kullanır. D flip-flopu iki D mandalı ve bir NOT geçidi veya 46 transistör kullanır. Bölüm 3.2.7, iletim kapılarını kullanan daha verimli bir CMOS uygulamasını açıklar.

## 3.2.4 Register / Sakslayıcı
Bir N-bit saklayıcı, ortak bir CLK girişini paylaşan bir N flip-flop bankasıdır, böylece yazmacın tüm bitleri aynı anda güncellenir. Saklayıcılar, çoğu ardışık devrenin temel yapı taşıdır. Şekil 3.9, D3: 0 girişleri ve Q3: 0 çıkışları ile dört bitlik bir yazmaç için şematik ve sembolü göstermektedir. D3: 0 ve Q3: 0'ın her ikisi de 4 bit veri yoludur.

![şekil3.9](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-9.png)

## 3.2.5 Enabled Flip-Flop
Etkinleştirilmiş bir flip-flop, verilerin saat kenarında yüklü olup olmadığını belirlemek için EN veya ENABLE adlı başka bir giriş ekler. EN DOĞRU olduğunda, etkinleştirilen flip-flop sıradan bir D flip-flopu gibi davranır. EN FALSE olduğunda, etkinleştirilen flip-flop saati yok sayar ve durumunu korur. Etkin flip-floplar, her saat kenarı yerine, her zaman bir flip-flop'a yeni bir değer yüklemek istediğimizde kullanışlıdır.

Şekil 3.10, bir D flip-flop ve ekstra bir kapıdan etkinleştirilmiş bir flip-flop oluşturmanın iki yolunu göstermektedir. Şekil 3.10 (a) 'da, bir giriş çoklayıcı, EN DOĞRU ise D'deki değerin geçip geçmeyeceğini veya EN YANLIŞ ise eski durumu Q'dan geri dönüştürmeyi seçer. Şekil 3.10 (b) 'de saat kapılıdır. EN DOĞRU ise, flip-flopun CLK girişi normal olarak değişir. EN YANLIŞ ise, CLK girişi de YANLIŞ'tır ve flip-flop eski değerini korur. CLK = 1 iken EN'nin değişmemesi gerektiğine dikkat edin, flip flop bir saat arızası görmesin (yanlış bir zamanda geçiş yapın). Genellikle, saat üzerinde mantık yürütmek kötü bir fikirdir. Saat geçitleme, saati geciktirir ve Bölüm 3.5.3'te göreceğimiz gibi zamanlama hatalarına neden olabilir, bu nedenle bunu yalnızca ne yaptığınızı bildiğinizden eminseniz yapın. Etkinleştirilmiş bir flip-flop için sembol Şekil 3.10 (c) 'de verilmiştir.

![şekil3.10](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-10.png)

## Resetlenebilir Flip-Flop
Sıfırlanabilir bir flip-flop, RESET adı verilen başka bir giriş ekler. SIFIRLA YANLIŞ olduğunda, sıfırlanabilir flip-flop sıradan bir D flip-flopu gibi davranır. SIFIRLA DOĞRU olduğunda, sıfırlanabilir flip-flop D'yi yok sayar ve çıkışı 0'a sıfırlar. Sıfırlanabilir flip-floplar, bilinen bir durumu (yani, 0) ilk kez bir sistemdeki tüm flip-flop'lara zorlamak istediğimizde kullanışlıdır.

Bu tür parmak arası terlikler eşzamanlı veya eşzamansız olarak sıfırlanabilir. Eşzamanlı olarak sıfırlanabilen parmak arası terlikler kendilerini yalnızca CLK'nın yükselen kenarında sıfırlar. Zaman uyumsuz olarak sıfırlanabilen parmak arası terlikler, CLK'dan bağımsız olarak RESET TRUE olur olmaz kendilerini sıfırlar.

Şekil 3.11 (a), sıradan bir D flip-flop ve bir AND geçidinden senkronize olarak sıfırlanabilir bir flip-flopun nasıl oluşturulacağını gösterir. SIFIRLAMA YANLIŞ olduğunda, AND geçidi, flip-flop'un girişine 0'ı zorlar. RESET TRUE olduğunda, AND geçidi D'yi flip-flop'a geçirir. Bu örnekte RESET, aktif bir düşük sinyaldir, yani sıfırlama sinyali 1 değil 0 olduğunda işlevini yerine getirir. Bir invertör ekleyerek devre bunun yerine aktif bir yüksek sıfırlama sinyalini kabul edebilirdi. Şekil 3.11 (b) ve 3.11 (c), aktif yüksek sıfırlamalı sıfırlanabilir flip-flop için sembolleri gösterir.

![şekil3.11](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-11.png)

Tahmin edebileceğiniz gibi, zaman zaman ayarlanabilir parmak arası terlikler de kullanılmaktadır. SET öne sürüldüğünde flip-flop'a bir 1 yüklerler ve onlar da senkronize ve asenkron aromalarda gelirler. Sıfırlanabilir ve ayarlanabilir flip-floplar ayrıca bir etkinleştirme girişine sahip olabilir ve N-bit kayıtları halinde gruplanabilir.

## 3.2.7 Transistör Seviyesinde Latch ve Flip-Flop Tasarımları
Örnek 3.1, mandalların ve flip-flopların mantık kapılarından yapıldığında çok sayıda transistör gerektirdiğini gösterdi. Ancak bir flip-flop un temel rolü, tıpkı bir anahtar gibi şeffaf veya opak olmaktır. Bölüm 1.7.7'den bir iletim geçidinin bir CMOS anahtarı oluşturmanın etkili bir yolu olduğunu hatırlayın, bu nedenle transistör sayısını azaltmak için iletim kapılarından faydalanabileceğimizi bekleyebiliriz.

Şekil 3.12(a)'da gösterildiği gibi, tek bir iletim kapısından kompakt bir D mandalı oluşturulabilir. CLK = 1 ve CLK = 0 olduğunda, iletim kapısı AÇIK'tır, bu nedenle D, Q'ya akar ve mandal şeffaftır. CLK = 0 ve CLK = 1 olduğunda, iletim kapısı KAPALI, dolayısıyla Q, D'den yalıtılır ve mandal opaktır. Bu mandal iki ana sınırlamadan muzdariptir:

- Kayan çıktı düğümü: Mandal opak olduğunda, Q hiçbir kapı tarafından değerinde tutulmaz. Böylece Q, yüzen veya dinamik bir düğüm olarak adlandırılır. Bir süre sonra gürültü ve şarj sızıntısı Q değerini bozabilir.

- Arabellek yok: Tampon eksikliği, birkaç ticari çipte arızalara neden oldu. D'yi negatif bir voltaja çeken bir gürültü artışı, nMOS transistörünü açarak, CLK = 0 olduğunda bile mandalı şeffaf hale getirebilir. Benzer şekilde, VDD'nin üzerindeki D'deki bir artış, CLK = 0 olduğunda bile pMOS transistörünü açabilir. Ve iletim kapısı simetriktir, bu nedenle Q üzerindeki gürültü D girişini etkilerken geriye doğru sürülebilir. Genel kural, ne iletim kapısının girişinin ne de sıralı devrenin durum düğümünün dış dünyaya maruz kalmaması gerektiğidir. gürültünün muhtemel olduğu yer.

Şekil 3.12(b), modern ticari çiplerde kullanılan daha sağlam bir 12 transistörlü D mandalını göstermektedir. Hala saatli bir iletim kapısı etrafında inşa edilmiştir, ancak giriş ve çıkışı tamponlamak için I1 ve I2 invertörlerini ekler. Mandalın durumu N1 düğümünde tutulur. Evirici I3 ve üç durumlu arabellek, T1, N1'i statik bir düğüme dönüştürmek için geri bildirim sağlar. CLK = 0 iken N1'de az miktarda gürültü oluşursa, T1, N1'i geçerli bir mantık değerine geri götürür.

![şekil3.12](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-12.png)

Şekil 3.13, CLK ve CLK tarafından kontrol edilen iki statik mandaldan yapılmış bir D parmak arası terlik göstermektedir. Bazı yedekli dahili invertörler kaldırılmıştır, bu nedenle flip-flop sadece 20 transistör gerektirir.

![şekil3.13](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-13.png)

## 3.2.8 Tümden inceleme
Mandallar ve flip-floplar, sıralı devrelerin temel yapı taşlarıdır. Bir D mandalının seviyeye duyarlı olduğunu, oysa bir D flip-flopunun kenarla tetiklendiğini unutmayın. D mandalı, CLK = 1 olduğunda saydamdır ve D girişinin Q çıkışına akmasına izin verir. D flip-flopu, CLK'nın yükselen kenarında D'yi Q'ya kopyalar. Diğer tüm zamanlarda, mandallar ve flip-floplar eski durumlarını korurlar. Saklayıcı ise ortak bir CLK sinyalini paylaşan birkaç D flip-flop'tan oluşan bir bankadır.

Örnek 3.2 : Ben Bitdiddle, Şekil 3.14 gösterilen D ve CLK girişlerini bir D mandalı ve bir D flip-flopuna uygular. Her cihazın Q çıktısını belirlemesine yardımcı olun.

![şekil3.14](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-14.png)

Çözüm: Şekil 3.15, Q'nun giriş değişikliklerine yanıt vermesi için küçük bir gecikme olduğu varsayılarak çıkış dalga biçimlerini gösterir. Oklar, bir çıktı değişikliğinin nedenini gösterir. Q'nun başlangıç değeri bilinmemektedir ve yatay çizgi çiftiyle gösterildiği gibi 0 veya 1 olabilir. İlk önce mandalı düşünün. CLK'nın ilk yükselen kenarında, D = 0, dolayısıyla Q kesinlikle 0 olur. CLK = 1 iken D her değiştiğinde, Q da onu takip eder. CLK = 0 iken D değiştiğinde, dikkate alınmaz. Şimdi flip-flop'u düşünün. CLK'nın her yükselen kenarında D, Q'ya kopyalanır. Diğer tüm zamanlarda, Q durumunu korur.

![şekil3.15](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-15.png)

# 3.3 Senkron Lojik Tasarım
Genel olarak, sıralı devreler, kombinasyonel olmayan, yani çıkışı sadece akım girişlerine bakılarak belirlenemeyen tüm devreleri içerir. Bazı sıralı devreler sadece tuhaftır. Bu bölüm, bu ilginç devrelerden bazılarını inceleyerek başlar. Daha sonra senkron ardışık devreler kavramını ve dinamik disiplini tanıtır. Kendimizi senkron ardışık devrelere disipline ederek, sıralı sistemleri analiz etmek ve tasarlamak için kolay, sistematik yollar geliştirebiliriz.

Örnek 3.3: Alyssa P. Hacker, Şekil 3.16'da gösterildiği gibi, kendilerini bir döngüye bağlamış üç yanlış yazılmış evirici ile karşılaşır. Üçüncü inverterin çıkışı birinci invertere geri beslenir. Her inverterin 1 ns yayılma gecikmesi vardır. Devrenin ne yaptığını belirleyin

![şekil3.16](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-16.png)

Çözüm: X düğümünün başlangıçta 0 olduğunu varsayalım. Sonra Y = 1, Z = 0 ve dolayısıyla X = 1, bu bizim orijinal varsayımımızla tutarsız. Devrenin kararlı durumu yoktur ve kararsız veya kararsız olduğu söylenir. Şekil 3.17 devrenin davranışını göstermektedir. X 0 zamanında yükselirse, Y 1 ns'de düşecek, Z 2 ns'de yükselecek ve X 3 ns'de tekrar düşecek. Sırayla, Y 4 ns'de yükselecek, Z 5 ns'de düşecek ve X tekrar 6 ns'de yükselecek ve ardından model tekrar edecek. Her düğüm, 6 ns'lik bir periyotla (tekrar süresi) 0 ile 1 arasında salınır. Bu devreye halka osilatör denir.

![şekil3.17](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-17.png)

Halka osilatör periyodu, her bir inverterin yayılma gecikmesine bağlıdır. Bu gecikme, inverterin nasıl üretildiğine, güç kaynağı voltajına ve hatta sıcaklığa bağlıdır. Bu nedenle, halka osilatör periyodunu doğru bir şekilde tahmin etmek zordur. Kısacası, halka osilatör, sıfır girişli ve periyodik olarak değişen bir çıkışlı sıralı bir devredir.

Örnek 3.4: Yarış durumu
Ben Bitdiddle, daha az kapı kullandığı için Şekil 3.7'dekinden daha iyi olduğunu iddia ettiği yeni bir D mandalı tasarladı. İki girdi (D ve CLK) ve mandalın eski durumu Qprev verilen Q çıktısını bulmak için doğruluk tablosunu yazdı. Bu doğruluk tablosuna dayanarak Boole denklemlerini türetmiştir. Qprev çıktısını Q çıktısını geri besleyerek elde eder. Tasarımı Şekil 3.18'de gösterilmektedir. Mandalı, her kapının gecikmesinden bağımsız olarak doğru çalışıyor mu?

![şekil3.18](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-18.png)

Çözüm: Şekil 3.19, devrenin, belirli kapılar diğerlerinden daha yavaş olduğunda devre dışı kalmasına neden olan bir yarış koşuluna sahip olduğunu göstermektedir. CLK = D = 1 varsayalım. Mandal şeffaftır ve Q = 1 yapmak için D'den geçer. Şimdi, CLK düşer. Mandal, Q = 1'i koruyarak eski değerini hatırlamalıdır. Bununla birlikte, inverterin CLK'dan CLK'ya olan gecikmesinin AND ve OR geçitlerinin gecikmelerine kıyasla oldukça uzun olduğunu varsayalım. O zaman N1 ve Q düğümlerinin her ikisi de CLK yükselmeden önce düşebilir. Böyle bir durumda N2 asla yükselmez ve Q 0'da takılı kalır.

Bu, çıkışların doğrudan girişlere geri beslendiği bir asenkron devre tasarımı örneğidir. Asenkron devreler, devrenin davranışının, mantık kapılarından geçen iki yoldan hangisinin en hızlı olduğuna bağlı olduğu yarış koşullarına sahip oldukları için meşhurdur. Bir devre çalışabilirken, biraz farklı gecikmelere sahip kapılardan yapılmış görünüşte aynı olan bir devre çalışmayabilir. Veya devre, yalnızca gecikmelerin tam olarak doğru olduğu belirli sıcaklıklarda veya voltajlarda çalışabilir. Bu arızaların izini sürmek son derece zordur
