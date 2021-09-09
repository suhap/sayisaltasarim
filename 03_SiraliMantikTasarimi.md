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

