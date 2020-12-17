# Birleşik Mantık Tasarımı
## Birleşik Mantık Tasarımı (Combinational Logic Design)

## Sunu 2
Sayısal elektronik devre şekildeki gibi bir sistem olarak düşünülebilir. Bu sistem, 
 1. Ayrık değişken girişleri, 
 2. Ayrık değişken çıkışları, 
 3. Giriş ve çıkışlarının birbirleri ile olan ilişkileri 
 4. Girişlerinin değişmesine bağlı olarak çıkışların değişmesindeki gecikmeyi tanımlayan bir zamanlama 
 özellikleri ile tanımlanabilir. ![2_1](https://raw.githubusercontent.com/suhap/sayisaltasarim/main/resource/2_1.PNG)

Yukarıda tanımlanan sisteme yakından incelendiğinde devreler ve teller oluştuğu görülebilir. 

## Sunu 3
Küçük devreler bir araya gelerek büyük devreler oluşturabilir. Şekilde E1, E2 ve E3 devreleri birleşerek daha büyük bir devreyi oluşturmaktadır.  Şekil incelendiğinde 3 alt devreden ve 6 telden oluştuğu görülmektedir. A, B, C telleri girişleri, Y, Z telleri çıkışları ve n1 teli ise E1 ve E3 arasındaki bağlantıyı göstermektedir. 

Sayısal devreler, birleşik veya sıralı olarak sınıflandırılır. Birleşik devrelerin çıkışları, yalnızca girişlerin mevcut değerlerine bağlıdır. Bir lojik kapı, birleşik bir devredir. Sıralı bir devrenin çıkışları ise girişlerin hem mevcut hem de önceki değerlerine bağlıdır. Dolayısıyla birleşik devrelerde hafıza elemanları mevcut değilken sıralı bir devre hafıza elemanlarına sahiptir. 
Birleşik devrelerde, çıkış akım değerleri giriş akım değerleri cinsinden ifade edilmektedir. Bir birleşik devrenin zamanlama değeri, girişten çıkışa kadar olan gecikmenin alt ve üst sınırlarından oluşur. 

## Sunu 4
Şekil sol, iki girişli ve bir çıkışlı bir birleşik devreyi göstermektedir. Şeklin solunda A ve B girişleri ve sağında Y çıkışı vardır. Kutu içindeki CL sembolü, devrenin birleşik devre olduğunu ifade etmektedir. Örnekte, OR fonksiyonu F olarak ifade edilmektedir: Y = F (A, B) = A + B

Şekil sağ, Şekil soldaki birleşik mantık devresi için iki olası uygulamayı göstermektedir. Kitap boyunca tekrar tekrar göreceğimiz gibi, genellikle tek bir foksiyon için birçok uygulama vardır. Elinizdeki yapı taşları ve tasarım kısıtlamalarınız için hangi çözümün kulanılacağı seçilebilir. Bu kısıtlamalar genellikle alanı, hızı, gücü ve tasarım süresini içerir.

## Sunu 5
Şekil sol, birden fazla çıkışa sahip bir birleşik devreyi göstermektedir. Bu tam toplayıcı devresi A, B ve Cin girişleri cinsinden, S ve Cout'un çıkışlarını tanımlar.

Çizimleri sadeleştirmek için, aynı tip birden fazla girişi, girişleri kesen eğik bir çizgi ve giriş sayısı ile ifade edebiliriz. Örneğin, şekil sağ, üç giriş ve iki çıkış içeren bir birleşik devreyi temsil etmektedir. Bit sayısı önemsizse veya bağlamdan anlaşılırsa, eğik çizgi sayı olmadan gösterilebilir. Şekil sağ(b), iki devreyi birbirine bağlayan bir teli göstemektedir. 

## Sunu 6
Birleşik lojik devreler aşağıdaki özelliklere sahiptirler;
 1. Birleşik devreyi oluşturan her devre elemanı birleşiktir.
 2. Devredeki herbir tel ya devrenin girişidir veya bir devrenin çıkışıdır. 
 3. Birleşik devreler döngüsel yollar içermez: devre boyunca her yol, her devre elemanını en fazla bir kez ziyaret eder.

Örnek 2.1 Birleşik Devreler
Şekildeki devrelerden hangisi, yukarudaki kurallarına göre birleşik devrelerdir?

Çözüm: 
(a) Birleşiktir. İki birleşik devre elemanından (inverterler I1 ve I2) oluşmaktadır. Üç tele sahiptir n1, n2 ve n3. n1, devre ve I1 girişidir. n2, I1'in çıkışı ve I2'nin girişi olan dahili bir teldir; n3, devrenin ve I2'nin çıkışıdır.
(b) Birleşik değildir, çünkü döngüsel bir yol içermektedir: XOR'un çıktısı, girdilerinden birine geri beslenir. Dolayısıyla, n4'te başlayan döngüsel bir yol XOR'dan n5'e geçer ve n4'e geri döner.
(c) Birleşiktir.
(d) Birleşik değildir, çünkü düğüm n6, hem I3 hem de I4'ün çıkışına bağlanır.
(e) Birleşiktir, daha büyük bir birleşik devre oluşturmak için bağlanan iki birleşik devreyi gösterir.
(f) İki eleman arasında döngüsel bir yola sahip olduğu için birleşik devre kurallarına uymaz. Elemanların foksiyonlarına bağlı olarak, bir birleşikdevre olabilir veya olmayabilir.

Mikroişlemciler gibi büyük devreler çok karmaşık olabilir, bu nedenle karmaşıklığı yönetmek için Bölüm 1'deki ilkeleri kullanıyoruz. Bir devreyi iyi tanımlanmış bir arayüze ve foksiyona sahip bir kara kutu olarak görmek, soyutlama ve modülerlik uygulamasıdır. Devreyi daha küçük devre elemanlarından oluşturmak  hiyerarşi uygulamasıdır. Birleşik devre kuralların, disiplin uygulamasıdır.

Bir birleşikk devrenin foksiyonu genellikle bir doğruluk tablosu veya bir Boole denklemi olarak ifade edilir. Sonraki bölümlerde, herhangi bir doğruluk tablosundan bir Boole denkleminin nasıl çıkarılacağını ve denklemleri basitleştirmek için Boole cebri ve Karnaugh haritalarının nasıl kullanılacağını açıklayacağız. Lojik kapılarını kullanarak bu denklemlerin nasıl uygulanacağını ve bu devrelerin hızının nasıl analiz edileceğini gösteriyoruz.

NOT: birleşik devre kuralları yeterlidir ancak kesinlikle gerekli değildir. Bu kurallara uymayan bazı devreler, çıkışlar yalnızca girişlerin mevcut değerlerine bağlı olduğu sürece hala birleşiktir. Bununla birlikte, garip devrelerin birleişk olup olmadığını belirlemek daha zordur, bu nedenle genellikle birleişk devreler inşa etmenin bir yolu olarak kendimizi birleşik kuralları ile sınırlayacağız.
