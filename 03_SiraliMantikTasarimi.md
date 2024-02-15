# 3.1 Giriş
Önceki bölümde, doğruluk tabloları veya boolean denklemleri kullanılarak optimize edilmiş bir devrenin nasıl oluşturulabileceği üzerinde durulmuştur. Dolayısıyla çıkışları girişler işlem yapılan andaki durumlarına göre belirlenen birleşik mantık devrelerinin nasıl tasarlanacağı anlatılmaktadır. 

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

![şekil3.19](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-19.png)

Bu, çıkışların doğrudan girişlere geri beslendiği bir asenkron devre tasarımı örneğidir. Asenkron devreler, devrenin davranışının, mantık kapılarından geçen iki yoldan hangisinin en hızlı olduğuna bağlı olduğu yarış koşullarına sahip oldukları için meşhurdur. Bir devre çalışabilirken, biraz farklı gecikmelere sahip kapılardan yapılmış görünüşte aynı olan bir devre çalışmayabilir. Veya devre, yalnızca gecikmelerin tam olarak doğru olduğu belirli sıcaklıklarda veya voltajlarda çalışabilir. Bu arızaların izini sürmek son derece zordur

## 3.3.2 Senkron Ardısık Devreler
Önceki iki örnek, çıkışların doğrudan girişlere geri beslendiği, döngüsel yollar adı verilen döngüler içerir. Kombinasyon devrelerinden ziyade sıralı devrelerdir. Kombinasyonel mantığın döngüsel yolları ve yarışları yoktur. Girişler birleşimsel mantığa uygulanırsa, çıkışlar her zaman bir yayılma gecikmesi içinde doğru değere oturacaktır. Bununla birlikte, döngüsel yollara sahip sıralı devreler, istenmeyen yarışlara veya kararsız davranışlara sahip olabilir. Bu tür devreleri problemler için analiz etmek zaman alıcıdır ve birçok zeki insan hata yapmıştır.

Bu sorunlardan kaçınmak için tasarımcılar, yolun herhangi bir yerine kayıtlar ekleyerek döngüsel yolları kırarlar. Bu, devreyi bir kombinasyonel mantık ve kayıtlar koleksiyonuna dönüştürür. Kayıtlar, yalnızca saat kenarında değişen sistemin durumunu içerir, bu nedenle durumun saatle senkronize olduğunu söylüyoruz. Saat, tüm kayıtlara girişler bir sonraki saat kenarından önce yerleşmek üzere yeterince yavaşsa, tüm yarışlar elenir. Geri besleme yolundaki her zaman yazmaçları kullanma disiplinini benimsemek, bizi bir senkron sıralı devrenin resmi tanımına götürür.

Bir devrenin giriş ve çıkış terminalleri ve işlevsel ve zamanlama özellikleri ile tanımlandığını hatırlayın. Sıralı bir devrenin sonlu ayrık durumları {S0, S1,…, Sk−1} vardır. Bir senkron ardışık devre, yükselen kenarları durum geçişlerinin meydana geldiği bir dizi zamanı gösteren bir saat girişine sahiptir. Sistemin o andaki durumunu, bir sonraki saat kenarında gireceği durumdan ayırt etmek için genellikle mevcut durum ve sonraki durum terimlerini kullanırız. İşlevsel belirtim, bir sonraki durumu ve mevcut durum ve giriş değerlerinin olası her bir kombinasyonu için her bir çıkışın değerini ayrıntılarıyla belirtir. Zamanlama belirtimi, saatin yükselen kenarından çıkış değişene kadar geçen süre için bir üst sınır, tpcq ve bir alt sınırdan, tccq ve ayrıca girişlerin ne zaman olduğunu gösteren kurulum ve tutma süreleri, tsetup ve thold'dan oluşur. saatin yükselen kenarına göre sabit olmalıdır.

Senkron ardışık devre kompozisyonunun kuralları bize, bir devrenin, birbirine bağlı devre elemanlarından oluşuyorsa, senkron ardışık bir devre olduğunu öğretir.

- Her devre elemanı ya bir kayıt ya da birleşimsel devredir.
- En az bir devre elemanı bir kayıttır
 - Tüm kayıtlar aynı saat sinyalini alır
- Her döngüsel yol en az bir kayıt içerir.

Senkron olmayan sıralı devrelere asenkron denir.

Bir flip-flop, en basit senkron ardışık devredir. Bir girişi, D, bir saati, CLK, bir çıkışı, Q ve iki durumu, {0, 1} vardır. Bir flip-flop için işlevsel belirtim, Şekil 3.20'de gösterildiği gibi, sonraki durumun D olması ve Q çıktısının mevcut durum olmasıdır.

![şekil3.20](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-20.png)

Sıklıkla mevcut durum değişkenini S ve sonraki durum değişkenini S' olarak adlandırırız. Bu durumda, S'den sonraki asal bir sonraki durumu belirtir, tersine çevirmeyi değil. Sıralı devrelerin zamanlaması Bölüm 3.5'te analiz edilecektir.

Senkron ardışık devrelerin diğer iki yaygın türü, sonlu durum makineleri ve boru hatları olarak adlandırılır. Bunlar bu bölümde daha sonra ele alınacaktır.

Örnek 3.5 SENKRON SIRALI DEVRELER
Şekil 3.21'deki devrelerden hangileri senkron ardışıl devrelerdir?

![şekil3.21](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-21.png)

Çözüm: Devre (a) birleşimseldir, sıralı değildir, çünkü kaydı yoktur. (b) geri beslemesi olmayan basit bir ardışık devredir. (c) ne birleşimsel devre ne de senkron ardışık devredir, çünkü ne yazmaç ne de birleşimsel devre olan bir mandalı vardır. (d) ve (e) senkron ardışık mantıktır; bunlar, Bölüm 3.4'te tartışılan iki sonlu durumlu makine biçimidir. (f) ne birleşimsel ne de senkron ardışık değildir, çünkü birleşimsel mantığın çıkışından aynı mantığın girişine kadar döngüsel bir yola sahiptir, ancak yolda kayıt yoktur. (g) Kısım 3.6'da inceleyeceğimiz bir ardışık düzen şeklinde senkron ardışık mantıktır. (h) kesinlikle senkron ardışık devre değildir, çünkü ikinci kayıt birinciden farklı bir saat sinyali alır, iki invertör gecikmesi tarafından geciktirilir.

## 3. 3. 3 Senkron ve Asenkron Devreler
Teoride asenkron tasarım, senkronize tasarımdan daha geneldir, çünkü sistemin zamanlaması saatli kayıtlarla sınırlı değildir. Analog devreler herhangi bir voltajı kullanabildikleri için analog devrelerin dijital devrelerden daha genel olması gibi, asenkron devreler de her türlü geri beslemeyi kullanabildikleri için senkron devrelerden daha geneldir. Bununla birlikte, dijital devrelerin analog devrelerden daha kolay olması gibi, senkron devrelerin tasarımı ve kullanımının asenkron devrelerden daha kolay olduğu kanıtlanmıştır. Asenkron devreler üzerinde onlarca yıllık araştırmalara rağmen, neredeyse tüm dijital sistemler esasen senkronizedir.

Elbette, farklı saatlere sahip sistemler arasında iletişim kurarken veya rastgele zamanlarda girişler alırken, sürekli voltajların gerçek dünyası ile iletişim kurarken analog devrelerin gerekli olması gibi, zaman uyumsuz devreler bazen gereklidir. Ayrıca, asenkron devrelerdeki araştırmalar, bazıları senkron devreleri de geliştirebilecek ilginç bilgiler üretmeye devam ediyor.

# 3.4 Sonlu Durum Makinaları
Şekilde 3.22 gösterilen senkron sıralı devreler sonlu durum makineleri (FSM'ler) denir. Sonlu durum makinelerinde k yazmaçlı bir devre sonlu sayıdaki (2k) durumlardan birinde olabilir. Bir FSM'nin M girişi, N çıkışı ve k bit durumu bir saat ve isteğe bağlı olarak bir reset (sıfırlama) sinyali alır. FSM, iki kombinasyonel mantık bloğu, bir sonraki durum mantığı ve çıkış mantığı ve durumu depolayan bir yazmaçtan oluşur. Her bir saat kenarında, FSM mevcut  İşlevsel özellikleri ile karakterize edilen iki sonlu durum makinesi sınıfı vardır.  Moore makinelerinde, çıktılar yalnızca makinenin mevcut durumuna bağlıdır. Mealy makinelerinde çıktılar hem mevcut duruma hem de girişlerine bağlıdır. Sonlu durum makineleri, özellikleri verilen eşzamanlı sıralı devreleri tasarlamak için sistematik bir yol sağlar. Bu yöntem, bir örnekle başlayarak bu bölümün geri kalanında açıklanacaktır. 

![şekil3.22](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-22.png)

## 3.4.1 Sonlu Durum Makinaları Örnegi
FSM'lerin tasarımını göstermek için, kampüsteki yoğun bir kavşakta trafik ışığı için bir kontrolör tasarlayalım. Mühendislik öğrencileri, yurtları ile Academic Ave'deki laboratuarlar arasında dolaşırlar. En sevdikleri ders kitaplarında FSM'ler hakkında okumakla meşguller ve nereye gittiklerine bakmıyorlar. Futbolcular atletik alanlar ve Bravado Bulvarı'ndaki yemek salonu arasında koşuşturuyor. Topu ileri geri fırlatıyorlar ve nereye gittiklerine de bakmıyorlar. Bu iki yolun kesişme noktasında çok sayıda ciddi yaralanma meydana geldiğinden Dekan, ölümler olmadan önce bir trafik ışığı takmasını istiyor. 

Ben, sorunu bir FSM ile çözmeye karar verir. Academic Ave. ve Bravado Blvd.'ye sırasıyla TA ve TB olmak üzere iki trafik sensörü kuruyor. Her sensör, öğrenciler mevcutsa DOĞRU, cadde boşsa YANLIŞ gösterir. Ayrıca trafiği kontrol etmek için LA ve LB olmak üzere iki trafik lambası kuruyor. Her ışık, yeşil, sarı veya kırmızı dijital girişleri alır. Dolayısıyla, FSM'sinin TA ve TB olmak üzere iki girişi ve LA ve LB  olmak üzere iki çıkışı vardır. Işıklar ve sensörler Şekil 2.23 gösterilmektedir. Ben, 5 saniyelik periyotlu bir saati vardır. Her saat işaretinde (yükselen kenar), ışıklar trafik sensörlerine göre değişebilir. Ayrıca, Fiziksel Tesis teknisyenlerinin denetleyiciyi açtıklarında bilinen bir başlangıç durumuna getirebilmeleri için bir sıfırlama düğmesi vardır. Şekilde 3.24, durum makinesinin kara kutu görünümünü göstermektedir. 

![şekil3.23](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-23.png)

![şekil3.24](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-24.png)

Ben'in bir sonraki adımı, sistemin tüm olası durumlarını ve bu durumlar arasındaki geçişleri göstermek için Şekil 3.25 gösterilen durum geçiş diyagramını çizmektir. Sistem sıfırlandığında, ışıklar Academic Ave'de yeşil ve Bravado Blvd'de kırmızıdır. Her 5 saniyede bir kontrolör trafik düzenini inceler ve daha sonra ne yapılacağına karar verir. Academic Ave.'de trafik olduğu sürece ışıklar değişmez. Academic Ave.'de artık trafik olmadığında, Academic Ave.'deki ışık kırmızıya ve Bravado Bulvarı'nın ışığı yeşile dönmeden önce 5 saniye boyunca sarıya döner. Benzer şekilde, Bravado Blvd. Bulvarda trafik olduğu sürece ışık yeşil kalır, ardından sarıya ve sonunda kırmızıya döner.

![şekil3.25](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-25.png)

Bir durum geçiş diyagramında, daireler ile temsil eder ve yaylar durumlar arasındaki geçişleri temsil eder. Geçişler saatin yükselen kenarında gerçekleşir; saati diyagram üzerinde gösterme zahmetine girmeyiz, çünkü her zaman eşzamanlı sıralı bir devrede mevcuttur. Dahası, saat basitçe geçişlerin ne zaman gerçekleşmesi gerektiğini kontrol ederken, diyagram hangi geçişlerin gerçekleştiğini gösterir. Dış dünya S0 durumuna işaret eden yay, sistemin, önceki durumdan bağımsız olarak, sıfırlama üzerine bu duruma girmesi gerektiğini belirtir. Bir durumda birden fazla yay varsa, yaylar, hangi giriş tarafından tetiklediğini göstermek için etiketlenir. Örneğin, S0 durumunda iken, TA TRUE ise sistem bu durumda kalacak ve TA FALSE ise S1'e geçecektir. Bir durumdan çıkan tek bir yaya sahipse, bu geçiş her zaman girişlerden bağımsız olarak gerçekleşir. Örneğin, S1 durumunda, sistem her zaman S2'ye geçecektir. Çıkışların belirli bir durumdayken sahip olduğu değer, durumda belirtilir. Örneğin, S2 durumunda, LA kırmızıdır ve LB yeşildir.

Ben, durum geçiş diyagramını bir durum geçiş Tablo 3.1 olarak yeniden yazar; bu, her durum ve giriş için bir sonraki durum olan S'nin ne olması gerektiğini gösterir. Tabloda, sonraki durum belirli bir girdiye bağlı olmadığında, önemsiz semboller (X) kullanıldığına dikkat edin. Ayrıca Reset tablodan çıkarıldığını unutmayın. Bunun yerine, girişlerden bağımsız olarak, sıfırlama sırasında her zaman S0 durumuna giden sıfırlanabilir flip flop kullanıyoruz.

![Tablo3.1](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T1.png)

Durum geçiş diyagramı, {S0, S1, S2, S3} etiketli durumları ve {kırmızı, sarı, yeşil} etiketli çıktıları kullandığından soyuttur. Gerçek bir devre oluşturmak için, durumlara ve çıkışlara ikili kodlamalar atanmalıdır. Ben, Tablo 3.2 ve 3.3 verilen basit kodlamaları seçer. Her durum ve her çıkış iki bit ile kodlanır: S1:0, LA1:0 ve LB1:0. 

![Tablo3.2](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T2.png)

![Tablo3.3](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T3.png)

Ben, Tablo 3.4 gösterildiği gibi bu ikili kodlamaları kullanmak için durum geçiş tablosunu günceller. Revize edilmiş durum geçiş tablosu, bir sonraki durum mantığını belirten bir doğruluk tablosudur. Sonraki durumu, S ′, mevcut durum, S ve girişlerin bir fonksiyonu olarak tanımlar.

![Tablo3.4](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T4.png)

Bu tablodan, bir sonraki durum için Boole denklemlerini çarpımları toplamı biçiminde okumak kolaydır.

S1' = S1'S0 +S1S0'TB' +S1S0'TB
S0' = S1'S0'TA' +S1S0'TB'

Denklemler, Karnaugh haritaları kullanılarak basitleştirilebilir, ancak genellikle bunu elle yapmak daha kolaydır. Örneğin, S1′ denklemindeki TB ve (TB)’ terimleri açıkça gereksizdir. Böylece S1′, bir XOR işlemine indirgenir. Aşağıdaki, basitleştirilmiş bir sonraki durum denklemlerini verir.

Denklem 3.2
S1' = S1 ⊕ S0
S0' = S1'S0'TA' +S1S0'TB'    

Benzer şekilde, Ben her durum için çıktının o durumda ne olması gerektiğini gösteren bir çıktı tablosu (Tablo 3.5) yazar. Yine, çıktılar için Boole denklemlerini okumak ve basitleştirmek kolaydır. Örneğin, LA1'in yalnızca S1'in TRUE olduğu satırlarda TRUE olduğunu gözlemleyin.

![Tablo3.5](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T5.png)

Denklem 3.3
LA1 = S1
LA0 = S1'S0
LB1 = S1'
LB0 = S1S0

Son olarak Ben, Moore FSM'sini Şekil 3.22(a) şeklinde çiziyor. İlk olarak, Şekil 3.26(a)'da gösterildiği gibi 2 bitlik durum kaydını çizer. Her saat kenarında, durum kaydı, S1:0 durumu olmak için sonraki durumu S1:0 ′ kopyalar. Durum kaydı, başlangıçta FSM'yi başlatmak için senkron veya asenkron bir sıfırlama alır. Ardından, Şekil 3.26(b)'de gösterildiği gibi, mevcut durum ve girdilerden sonraki durumu hesaplayan Denklem 3.2'ye dayalı olarak bir sonraki durum mantığını çizer. Son olarak, Şekil 3.26(c)'de gösterildiği gibi, mevcut durumdan çıktıları hesaplayan Denklem 3.3'e dayalı olarak çıktı mantığını çizer.

![şekil3.26](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-26.png)

Şekil 3.27, bir dizi durumdan geçen trafik ışığı kontrolörünü gösteren bir zamanlama diyagramını göstermektedir. Diyagramda CLK, Reset, TA ve TB girişleri, sonraki S' durumu, S durumu ve LA ve LB çıkışları gösterilmektedir. Oklar nedenselliği gösterir; örneğin, durumu değiştirmek çıktıların değişmesine ve girdilerin değiştirilmesi bir sonraki durumun değişmesine neden olur. Kesikli çizgiler, durum değiştiğinde CLK'nın yükselen kenarlarını gösterir.

![şekil3.27](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-27.png)

Saatin 5 saniyelik bir periyodu vardır, bu nedenle trafik ışıkları en fazla 5 saniyede bir değişir. Sonlu durum makinesi ilk açıldığında, soru işaretleriyle gösterildiği gibi durumu bilinmemektedir. Bu nedenle, bilinen bir duruma getirmek için sistem sıfırlanmalıdır. Bu zamanlama şemasında, eşzamansız olarak sıfırlanabilen iki duraklıların kullanıldığını belirten hemen S0'a sıfırlanır. S0 durumunda, ışık LA yeşil ve ışık LB kırmızıdır.

Bu örnekte trafik hemen Academic Ave'e gelir.Bu nedenle, Bravado Blvd'ye trafik gelse bile denetleyici S0 durumunda kalır ve LA'yı yeşil tutar. ve beklemeye başlar. 15 saniye sonra Academic Ave. üzerindeki trafik tamamen geçer ve TA düşer. Takip eden saat kenarında, kontrolör LA'yı sarıya çevirerek S1 durumuna geçer. 5 saniye sonra kontrolör, LA'nın kırmızıya ve LB'nin yeşile döndüğü S2 durumuna geçer. Denetleyici, Bravado Blvd'deki tüm trafik oluşana kadar S2 durumunda bekler. geçti. Daha sonra LB'yi sarıya çevirerek S3 durumuna geçer. 5 saniye sonra kontrolör S0 durumuna girer ve LB kırmızı ve LA yeşile döner. İşlem tekrarlanır.

## 3.4.2 Durum Kodlama
Önceki örnekte, durum ve çıktı kodlamaları keyfi olarak seçilmiştir. Farklı bir seçim, farklı bir devre ile sonuçlanabilirdi. Doğal bir soru, en az mantık kapısına veya en kısa yayılma gecikmesine sahip devreyi üreten kodlamanın nasıl belirleneceğidir. Ne yazık ki, durum sayısı fazla olduğunda mümkün olmayan tüm olasılıkları denemek dışında en iyi kodlamayı bulmanın basit bir yolu yoktur. Bununla birlikte, ilgili durumların veya çıktıların bitleri paylaşması için inceleme yoluyla iyi bir kodlama seçmek çoğu zaman mümkündür. Bilgisayar destekli tasarım (CAD) araçları, olası kodlamaları arama ve makul bir kodlama seçme konusunda da iyidir.

Durum kodlamasında önemli bir karar, ikili kodlama ile tek-sıcak kodlama arasındaki seçimdir. Trafik ışığı denetleyicisi örneğinde kullanıldığı gibi ikili kodlamada, her durum bir ikili sayı olarak temsil edilir. K ikili sayıları log2K bitleriyle temsil edilebildiğinden, K durumlu bir sistem yalnızca log2K bit durumlarına ihtiyaç duyar.

Tek sıcak kodlamada, her durum için ayrı bir durum biti kullanılır. Tek-sıcak olarak adlandırılır, çünkü herhangi bir zamanda yalnızca bir bit "sıcak" veya DOĞRUdır. Örneğin, üç durumlu tek-sıcak kodlanmış bir FSM, 001, 010 ve 100 durum kodlamalarına sahip olacaktır. Her bir durum biti bir flip-flop'ta depolanır, bu nedenle onehot kodlama, ikili kodlamadan daha fazla flip-flop gerektirir. Ancak, one-hot kodlama ile sonraki durum ve çıkış mantığı genellikle daha basittir, dolayısıyla daha az geçit gerekir. En iyi kodlama seçimi, belirli FSM'ye bağlıdır.

Örnek 3.6 : N'ye bölme sayacının bir çıkışı vardır ve girişi yoktur. Y çıkışı, her N'den bir saat döngüsü için YÜKSEK'tir. Başka bir deyişle, çıkış saatin frekansını N'ye böler. Bir 3'e bölme sayacı için dalga biçimi ve durum geçiş diyagramı Şekil 3.28'de gösterilmektedir. İkili ve tek sıcak durum kodlamalarını kullanarak böyle bir sayaç için devre tasarımları çizin.

![şekil3.28](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-28.png)

Çözüm: Tablo 3.6 ve 3.7, kodlamadan önceki soyut durum geçişini ve çıktı tablolarını gösterir.

![Tablo3.6](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T6.png)

![Tablo3.7](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T7.png)

Tablo 3.8, üç durum için ikili ve tek sıcak kodlamaları karşılaştırır.

![Tablo3.8](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T8.png)

İkili kodlama iki bit durum kullanır. Bu kodlama kullanılarak durum geçiş tablosu Tablo 3.9'da gösterilmiştir. Giriş olmadığını unutmayın; sonraki durum yalnızca mevcut duruma bağlıdır. Çıktı tablosu okuyucuya alıştırma olarak bırakılmıştır. Sonraki durum ve çıktı denklemleri:

![Tablo3.9](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T9.png)

S′1 = S1S0
S′0 = S1S0   (3.4)

Y = S1S0  (3,5)

Tek sıcak kodlama, üç bit durum kullanır. Bu kodlama için durum geçiş tablosu Tablo 3.10'da gösterilmiş ve çıktı tablosu yine bir alıştırma olarak okuyucuya bırakılmıştır. Sonraki durum ve çıktı denklemleri aşağıdaki gibidir:

![Tablo3.10](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T10.png)

S'2 = S1
S'1 = S0
S′0 = S2    (3.6)

Y = S0 (3.7)

Şekil 3.29, bu tasarımların her biri için şemaları göstermektedir. İkili kodlanmış tasarım donanımının, Y ve S0' için aynı geçidi paylaşacak şekilde optimize edilebileceğini unutmayın. Ayrıca, tek-sıcak kodlamanın, makineyi sıfırlama sırasında S0'a başlatmak için hem ayarlanabilir(ler) hem de sıfırlanabilir (r) flip-floplar gerektirdiğini gözlemleyin. En iyi uygulama seçimi, kapıların ve parmak arası terliklerin göreli maliyetine bağlıdır, ancak bu özel örnek için genellikle tek-sıcak tasarım tercih edilir.

![şekil3.29](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-29.png)

İlgili bir kodlama, K durumunun tam olarak biri YANLIŞ olan K bitleri ile temsil edildiği tek-soğuk kodlamadır.

## 3.4.3 Moore and Mealy Machines
Şimdiye kadar, çıktının yalnızca sistemin durumuna bağlı olduğu Moore makinelerinin örneklerini gösterdik. Bu nedenle, Moore makineleri için durum geçiş diyagramlarında çıktılar daireler içinde etiketlenir. Mealy makinelerinin Moore makinelerine çok benzediğini hatırlayın, ancak çıktılar mevcut duruma olduğu kadar girdilere de bağlı olabilir. Bu nedenle, Mealy makineleri için durum geçiş diyagramlarında, çıktılar daireler yerine yaylar üzerinde etiketlenir. Çıkışları hesaplayan kombinasyonel mantık bloğu, Şekil 3.22(b)'de gösterildiği gibi mevcut durumu ve girişleri kullanır.

![şekil3.22](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-22.png)


Örnek 3.7 MOORE VERSUS MEALY MAKİNELERİ
Alyssa P. Hacker, FSM beyinli bir evcil robot salyangoza sahiptir. Salyangoz, 1'ler ve 0'lar dizisi içeren bir kağıt şeridi boyunca soldan sağa doğru sürünür. Her saat döngüsünde, salyangoz bir sonraki bite doğru sürünür. Salyangoz, üzerinden süründüğü son iki bit soldan sağa doğru 01 olduğunda gülümser. Salyangozun ne zaman gülümsemesi gerektiğini hesaplayacak FSM'i tasarlayın. Giriş A, salyangozun antenlerinin altındaki bittir. Çıktı Y, salyangoz gülümsediğinde TRUE'dur. Moore ve Mealy durum makinesi tasarımlarını karşılaştırın. Her makine için giriş, durumlar ve çıktıyı gösteren bir zamanlama diyagramı çizin, Alyssa'nın salyangozu 0100110111 dizisi boyunca süründükçe.
Çözüm: Moore makinesi, Şekil 3.30(a)'da gösterildiği gibi üç durum gerektirir. Durum geçiş diyagramının doğru olduğuna kendinizi ikna edin. Özellikle, giriş 0 olduğunda S2'den S1'e bir yayın neden olduğunu düşünün?
Karşılaştırıldığında, Mealy makinesi yalnızca iki durum gerektirir, Şekil 3.30(b)’de gösterildiği gibi.
Her yay A/Y olarak etiketlenmiştir. A, o geçişi sağlayan girişin değeri ve Y, karşılık gelen çıktıdır.
Tablolar 3.11 ve 3.12, Moore makinesi için durum geçiş ve çıktı tablolarını gösterir. Moore makinesi en az iki bit durum gerektirir. İkili durum kodlaması kullanmayı düşünün: S0 = 00, S1 = 01 ve S2 = 10. Tablolar 3.13 ve 3.14, bu kodlamalarla durum geçiş ve çıktı tablolarını yeniden yazar.
Bu tablolardan, sonraki durum ve çıktı denklemlerini inceleme yoluyla buluruz.
Bu denklemlerin basitleştirilmesi, 11 durumunun var olmaması gerçeği kullanılarak yapılır. Dolayısıyla, var olmayan durum için karşılık gelen sonraki durum ve çıktı, umursanmazlar (tabloların içinde gösterilmez). Denklemlerimizi minimize etmek için umursanmazları kullanırız.

Denklem 3.8
 S1' = S0A
 S0' = A'

 Denklem 3.9 
 Y= S1
 
Tablo 3.15, Mealy makinesi için birleştirilmiş durum geçiş ve çıktı tablosunu gösterir. Mealy makinesi yalnızca bir bit durum gerektirir. İkili durum kodlaması kullanmayı düşünün: S0 = 0 ve S1 = 1. Tablo 3.16, bu kodlamalarla durum geçiş ve çıktı tablosunu yeniden yazar.
Bu tablolardan, sonraki durum ve çıktı denklemlerini inceleme yoluyla buluruz.
 
 Denklem 3.10
 S0' = A'
 Denklem 3.11 
 Y = S0A
Moore ve Mealy makinesi şemaları Şekil 3.31'de gösterilmiştir. Her makine için zamanlama diyagramları Şekil 3.32'de gösterilmiştir (135. sayfaya bakınız). İki makine farklı durum dizilerini takip eder. Dahası, Mealy makinesinin çıktısı, durum değişikliğini beklemek yerine girişe yanıt olarak bir döngü daha erken yükselir. Mealy çıktısı bir flip-flop aracılığıyla geciktirilirse, Moore çıktısıyla eşleşir. FSM tasarım stilinizi seçerken, çıktılarınızın ne zaman yanıt vermesini istediğinizi göz önünde bulundurun.

![şekil3.30](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-30.png)
 
![Tablo3.11](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T11.png)
![Tablo3.12](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T12.png)
![Tablo3.13](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T13.png)
![Tablo3.14](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T14.png)
![Tablo3.15](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T15.png)
![Tablo3.16](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T16.png)

## 3.4.4 Durum Makinelerini Faktörleme
Karmaşık FSM'lerin tasarımı, eğer bu makineler birden fazla etkileşimli daha basit durum makinelerine ayrılabilirse genellikle daha kolaydır, böylece bazı makinelerin çıktısı diğerlerinin girişi olur. Bu hiyerarşi ve modülerlik uygulamasına durum makinelerinin faktörleme denir.

![şekil3.31](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-31.png)
![şekil3.32](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-32.png)

Örnek 3.8 FAKTÖRLENMEMİŞ VE FAKTÖRLENMİŞ DURUM MAKİNELERİ
3.4.1 Bölümünden trafik ışığı kontrolörünü, Bravado Bulvarı ışığını yeşil tutan ve seyirciler ile bando, dağınık gruplar halinde futbol maçlarına yürüdükleri süre boyunca geçit moduna alacak şekilde değiştirin. Kontrolör iki yeni giriş alır: P ve R. P'yi en az bir döngü boyunca iddia etmek geçit moduna girer. R'yi en az bir döngü boyunca iddia etmek geçit modundan çıkar. Geçit modundayken, kontrolör, LB yeşil olduğunda normal sırasına devam eder ve sonra LB yeşil iken geçit modu sona erene kadar bu durumda kalır.
Öncelikle, Şekil 3.33(a)’da gösterildiği gibi tek bir FSM için bir durum geçiş diyagramı çizin. Sonra, Şekil 3.33(b)’de gösterildiği gibi iki etkileşimli FSM için durum geçiş diyagramlarını çizin. Mod FSM'i, parade modundayken M çıktısını iddia eder. Işıklar FSM'i, M ve trafik sensörleri TA ve TB'ye dayanarak ışıkları kontrol eder.
Çözüm: Şekil 3.34(a) tek FSM tasarımını gösterir. S0'dan S3'e durumlar normal modu işler. S4'ten S7'ye durumlar geçit modunu işler. Diyagramın iki yarısı neredeyse aynıdır, ancak geçit modundayken, FSM Bravado Bulv. üzerinde yeşil ışıkla S6'da kalır. P ve R girişleri, bu iki yarı arasındaki hareketi kontrol eder. FSM karmaşık ve tasarlaması sıkıcıdır. Şekil 3.34(b) faktörlenmiş FSM tasarımını gösterir. Mod FSM'i, ışıkların normal modda mı yoksa geçit modunda mı olduğunu izlemek için iki duruma sahiptir. Işıklar FSM'i, M TRUE olduğu sürece S2'de kalmak üzere modifiye edilmiştir.

![şekil3.33](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-33.png)
![şekil3.34](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-34.png)

##3.4.5 Bir Şematikten FSM Türetme
Bir şematikten durum geçiş diyagramını türetme işlemi, neredeyse FSM tasarımının tersi bir süreci izler. Bu işlem, örneğin, eksik belgelenmiş bir projeyi devralırken veya başkasının sistemini tersine mühendislik yaparken gerekli olabilir.

▶ Devreyi inceleyin, girişleri, çıktıları ve durum bitlerini belirtin.
▶ Sonraki durum ve çıktı denklemlerini yazın.
▶ Sonraki durum ve çıktı tablolarını oluşturun.
▶ Erişilemeyen durumları elemek için sonraki durum tablosunu indirgeyin.
▶ Her geçerli durum bit kombinasyonuna bir isim atayın.
▶ Sonraki durum ve çıktı tablolarını durum isimleriyle yeniden yazın.
▶ Durum geçiş diyagramını çizin.
▶ FSM'in ne yaptığını kelimelerle ifade edin.
Son adımda, FSM'in genel amacını ve işlevini öz olarak tanımlamaya dikkat edin—durum geçiş diyagramının her geçişini basitçe yeniden ifade etmeyin.
Örnek 3.9 BİR FSM'İN DEVRESİNDEN TÜRETME
Alyssa P. Hacker eve geldiğinde, ancak tuş takımı kilidi yeniden bağlanmış ve eski kodu artık çalışmıyor. Üzerine Şekil 3.35'teki devre şemasını gösteren bir kağıt parçası yapıştırılmış. Alyssa, devrenin bir sonlu durum makinesi olabileceğini düşünüyor ve kapıyı açmasına yardımcı olup olmadığını görmek için durum geçiş diyagramını türetmeye karar veriyor.

Çözüm: Alyssa devreyi inceleyerek başlar. Giriş A1:0 ve çıktı Kilidi Açıktır. Durum bitleri zaten Şekil 3.35'te etiketlenmiştir. Bu, çıktının yalnızca durum bitlerine bağlı olduğu için bir Moore makinesidir. Devreden, sonraki durum ve çıktı denklemlerini doğrudan yazar:
S′1 = S0A1'A0
S′0 = S1'S0'A1A0
Unlock = S1
![şekil3.35](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-35.png)
Daha sonra, denklemlerden sonraki durum ve çıktı tablolarını, Denklem 3.12 tarafından belirtildiği gibi, öncelikle tablolara 1'leri yerleştirerek ve geri kalan her yere 0 yerleştirerek yazıyor.

Alyssa, kullanılmayan durumları kaldırarak ve umursamazları kullanarak satırları birleştirerek tabloyu indirger. S1:0 = 11 durumu, Tablo 3.17'de olası bir sonraki durum olarak asla listelenmez, bu yüzden bu mevcut durumlu satırlar kaldırılır. Mevcut durum S1:0 = 10 için, sonraki durum her zaman S1:0 = 00'dir, girişlerden bağımsız olarak, bu yüzden girişler için umursamazlar eklenir. İndirgenmiş tablolar Tablo 3.19 ve 3.20'de gösterilir.
Her durum bit kombinasyonuna isimler atar: S0, S1:0 = 00 için, S1, S1:0 = 01 için ve S2, S1:0 = 10 için. Tablolar 3.21 ve 3.22 durum isimleriyle sonraki durum ve çıktı tablolarını gösterir.
![Tablo3.17](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T17.png)
![Tablo3.18](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T18.png)
![Tablo3.19](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T19.png)
![Tablo3.20](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T20.png)
![Tablo3.21](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T21.png)
![Tablo3.22](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-T22.png)

![şekil3.36](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3-36.png)

Alyssa, Tablolar 3.21 ve 3.22 kullanarak Şekil 3.36'da gösterilen durum geçiş diyagramını yazar. İnceleme yoluyla, sonlu durum makinesinin, ardından bir giriş değeri olan biri izleyen üçlü bir giriş değeri, A1:0, algıladıktan sonra kapıyı açtığını görebilir. Sonra kapı tekrar kilitlenir. Alyssa bu kodu kapı tuş takımında dener ve kapı açılır!

##3.4.6 FSM İncelemesi
Sonlu durum makineleri, yazılı bir spesifikasyondan ardışık devrelerin sistemli bir şekilde tasarlanması için güçlü bir yoldur. Bir FSM tasarlamak için aşağıdaki prosedürü kullanın:
▶ Girişleri ve çıktıları belirleyin.
▶ Bir durum geçiş diyagramı çizin.
▶ Bir Moore makinesi için:
– Bir durum geçiş tablosu yazın.
– Bir çıktı tablosu yazın.
▶ Bir Mealy makinesi için:
– Birleştirilmiş durum geçiş ve çıktı tablosu yazın.
▶ Durum kodlamalarını seçin—seçiminiz donanım tasarımını etkiler.
▶ Sonraki durum ve çıktı mantığı için Boolean denklemleri yazın.
▶ Devre şematik çizimini çizin.
Bu kitap boyunca karmaşık dijital sistemlerin tasarımında FSM'leri tekrar tekrar kullanacağız.

# 3.5 ARDışIK MANTIĞIN ZAMANLAMASI
Bir flip-flop'un, saat sinyalinin yükselen kenarında girişi

D'yi çıktıya

Q'ya kopyaladığını hatırlayın. Bu işleme, saat kenarında D'nin örneklenmesi denir. Eğer
D, saat yükseldiğinde 0 veya 1 olarak sabitse, bu davranış açıkça tanımlanmıştır.
Peki ya

D, saat yükselirken değişiyorsa ne olur?
Bu problem, bir fotoğraf makinesinin bir resim çekerken karşılaştığı
probleme benzer. Bir kurbağanın nilüfer yaprağından göle atladığı anı
fotoğraflamayı hayal edin. Eğer atlamadan önce fotoğrafı çekerseniz, nilüfer
yaprağında bir kurbağa görürsünüz. Atlamadan sonra fotoğrafı çekerseniz,
suda halkalar görürsünüz. Ama tam kurbağa atladığı anda çekerseniz, kurbağanın nilüfer yaprağından suya doğru uzandığı bulanık bir görüntü görebilirsiniz. Bir fotoğraf makinesi, nesnenin keskin bir görüntü elde edilmesi için
sabit kalmak zorunda olduğu bir diyafram süresi ile karakterize edilir. Benzer şekilde, bir ardışık elemanın, flip-flop'un iyi tanımlanmış bir çıktı üretmesi için girişin sabit kalmak zorunda olduğu saat kenarı etrafında bir diyafram süresi vardır.
Bir ardışık elemanın diyaframı, sırasıyla saat kenarından önce ve sonra bir kurulum süresi ve bir tutma süresi ile tanımlanır. Tıpkı statik disiplinin bizi yasak bölge dışındaki mantık seviyelerini kullanmaya sınırlaması gibi,
dinamik disiplin de bizi diyafram süresi dışında değişen sinyalleri kullanmaya sınırlar. Dinamik disipline avantaj sağlayarak,
zamanı, sinyal seviyelerini ayrık 1'ler ve 0'lar olarak düşündüğümüz gibi, saat döngüleri olarak adlandırılan ayrık birimler cinsinden düşünebiliriz. Bir sinyal, sınırlı bir süre boyunca hızlıca dalgalanıp osile olabilir. Dinamik disiplin altında, sadece son değeriyle ilgileniriz, saat döngüsünün sonunda, sabit bir değere yerleştikten sonra. Bu nedenle, basitçe
A[n], sinyalin 
n'inci saat döngüsünün sonundaki değeri olarak yazabiliriz, burada
n bir tam sayıdır, yerine
A(t), bazı anlarda
A'nın değeri olarak, burada
t herhangi bir gerçek sayıdır.

Saat periyodu, tüm sinyallerin yerleşmesi için yeterince uzun olmalıdır. Bu, sistemin hızı üzerinde bir sınır belirler. Gerçek sistemlerde, saat sinyali tüm flip-floplara tam olarak aynı anda ulaşmaz. Saat kayması olarak adlandırılan bu zaman varyasyonu, gerekli saat periyodunu daha da artırır.
Bazen, özellikle gerçek dünya ile arayüz oluşturulduğunda, dinamik disiplini tatmin etmek imkansızdır. Örneğin, girişi bir düğmeden gelen bir devreyi düşünün. Bir maymun, saat yükselirken düğmeye basabilir. Bu, flip-flopu 0 ve 1 arasında bir değerde yakaladığı ve iyi bir mantık değerine dönüşmesi için sınırsız bir sü

re alabilecek bir metastabilite fenomenine yol açabilir. Böyle asenkron girişlerin çözümü, çok küçük (ama sıfır olmayan) bir olasılıkla yasal olmayan bir mantık değeri üretebilen bir senkronizatör kullanmaktır.
Bu bölümün geri kalanında tüm bu fikirleri genişletiyoruz.

## 3.5.1 Dinamik Disiplin
Şimdiye kadar, ardışık devrelerin fonksiyonel spesifikasyonuna odaklandık. Bir flip-flop veya FSM gibi senkron ardışık bir devrenin, Şekil 3.37'de gösterildiği gibi, bir zamanlama spesifikasyonuna da sahip olduğunu hatırlayın. Saat yükseldiğinde, çıktı (veya çıktılar) saatten-Q'ya kontaminasyon gecikmesi, tccq, sonrasında değişmeye başlayabilir ve kesinlikle saatten-Q'ya yayılma gecikmesi, tpcq, içinde son değere yerleşmelidir. Bunlar, sırasıyla, devreden geçen en hızlı ve en yavaş gecikmeleri temsil eder. Devrenin girişini doğru bir şekilde örneklemesi için, giriş (veya girişler) en azından bir kurulum süresi, tsetup, kadar önce saat yükselme kenarından önce stabilize olmuş olmalı ve en az bir tutma süresi, thold, kadar saat yükselme kenarından sonra sabit kalmalıdır. Kurulum ve tutma sürelerinin toplamı, girişin sabit kalmak zorunda olduğu toplam süre olduğu için, devrenin diyafram süresi olarak adlandırılır.

Dinamik disiplin, bir senkron ardışık devrenin girişlerinin, saat kenarı etrafındaki kurulum ve tutma diyafram süresi boyunca sabit olması gerektiğini belirtir. Bu gerekliliği uygulayarak, flip-flopların değişmeyen sinyalleri örneklediğini garanti ederiz. Yalnızca örneklenme zamanındaki girişlerin son değerleriyle ilgilendiğimiz için, sinyalleri mantık seviyeleri kadar zamanda da ayrık olarak ele alabiliriz.
