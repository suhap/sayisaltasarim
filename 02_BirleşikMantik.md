# 2.1 Giriş
 Aşağıdaki şekilde gösterilen bir kara kutu olarak gösterilen sayısal elektronik devresi, ayrık değişkenleri işleyen bir sistem olarak düşünülebilir. 
- bir veya daha fazla ayrık değerli giriş terminali
- bir veya daha fazla ayrık değerli çıkış terminali
- girdiler ve çıktılar arasındaki ilişkiyi açıklayan işlevsel bir özellik
- girişlerin değişmesi ve yanıt veren çıkışlar arasındaki gecikmeyi açıklayan bir zamanlama özelliği.

![şekil2.1](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-1.png)

Kara kutunun içine bakılırsa devreler, düğümlerden ve elemanlardan oluştuğu görülebilir. Bir elemanın kendisi, girişler, çıkışlar ve belli özellillere sahip bir devredir. Bir düğüm, voltajı ayrık bir değişken taşıyan bir teldir. Düğümler giriş, çıkış veya dahili olarak sınıflandırılır. Girişler dış dünyadan değerler alır. Çıktılar, dış dünyaya değerler verir. Giriş veya çıkış olmayan kablolara dahili düğümler denir. Aşağıdaki şekil, üç elemanlı, E1, E2 ve E3 ve altı düğümlü bir devreyi göstermektedir. A, B ve C düğümleri girişlerdir. Y ve Z çıktılardır. n1, E1 ve E3 arasındaki dahili bir düğümdür.

![şekil2.2](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-2.png)

Dijital devreler, kombinasyonel veya sıralı olarak sınıflandırılır. Bir birleşimsel devrenin çıkışları, yalnızca girişlerin mevcut değerlerine bağlıdır; başka bir deyişle, çıktıyı hesaplamak için mevcut giriş değerlerini birleştirir. Örneğin, bir mantık kapısı, birleşimsel bir devredir. Sıralı bir devrenin çıkışları, girişlerin hem mevcut hem de önceki değerlerine bağlıdır; başka bir deyişle, giriş sırasına bağlıdır. Bir birleşimsel devre hafızasızdır, ancak sıralı bir devre hafızaya sahiptir. Bu bölüm kombinasyonel devrelere odaklanır ve sonraki bölüm sıralı devreleri inceler.

Bir birleşimsel devrenin işlevsel özelliği, çıkış değerlerini akım giriş değerleri cinsinden ifade eder. Bir birleşimsel devrenin zamanlama özelliği, girişten çıkışa kadar olan gecikmenin alt ve üst sınırlarından oluşur. Öncelikle fonksiyonel spesifikasyona odaklanacağız, ardından bu bölümün ilerleyen kısımlarında zamanlama spesifikasyonuna döneceğiz.

Aşağıdaki şekil, iki girişli ve bir çıkışlı bir birleşimsel devreyi göstermektedir. Şeklin solunda A ve B girişleri ve sağında Y çıkışı vardır. Kutunun içindeki CL sembolü, yalnızca kombinasyonel mantık kullanılarak uygulandığını gösterir. Bu örnekte, F işlevi OR olarak belirtilmiştir: Y = F (A, B) = A + B. Diğer bir deyişle, Y çıkışının, A ve B olmak üzere iki girişin, yani Y = A VEYA B'nin bir fonksiyonu olduğunu söylüyoruz.

![şekil2.3](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-3.png)

Aşağıdaki şekil, yukarıdaki şekilde gösterilen kombinasyonel mantık devresi için iki olası uygulamayı göstermektedir. Kitap boyunca tekrar tekrar göreceğimiz gibi, genellikle tek bir işlev için birçok uygulama vardır. Elinizdeki yapı taşları ve tasarım kısıtlamalarınız için hangisinin kullanılacağını siz seçersiniz. Bu kısıtlamalar genellikle alanı, hızı, gücü ve tasarım süresini içerir.

![şekil2.4](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-4.png)

Aşağıdaki şekil, çoklu çıkışlara sahip bir birleşimsel devreyi göstermektedir. Bu belirli kombinasyonel devreye tam toplayıcı adı verilir ve onu Bölüm 5.2.1'de yeniden inceleyeceğiz. İki denklem, girişler, A, B ve Cin cinsinden çıkışların, S ve Cout'un işlevini belirtir.

![şekil2.5](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-5.png)

Çizimleri basitleştirmek için, genellikle bir çizgi ve yanında bir sayı olan tek bir çizgi, birden çok sinyalden oluşan bir yolu belirtmek için kullanırız. Sayı, veriyolunda kaç sinyal olduğunu belirtir. Örneğin, Aşağıdaki şekil, üç giriş ve iki çıkış içeren bir birleşimsel mantık bloğunu temsil eder. 

![şekil2.6a](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-6a.png)

Bit sayısı önemsizse veya bağlamdan anlaşılırsa, eğik çizgi sayı olmadan gösterilebilir. Aşağıdaki şekil, bir bloktan ikinci bloğa girişler olarak hizmet eden keyfi sayıda çıktıya sahip iki kombinasyonel mantık bloğunu gösterir.

![şekil2.6b](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-6b.png)

Kombinasyon bileşiminin kuralları, bize daha küçük birleşimsel devre elemanlarından nasıl büyük bir birleşimsel devre oluşturabileceğimizi söylemektedir. 

Bir devre, birbirine bağlı devre elemanlarından oluşuyorsa birleşimseldir, öyle ki
- Her devre elemanının kendisi birleşimlidir.
- Devrenin her düğümü ya devreye bir giriş olarak atanır ya da bir devre elemanının tam olarak bir çıkış terminaline bağlanır.
- Devre, döngüsel yollar içermez: devre boyunca her yol, her devre düğümünü en fazla bir kez ziyaret eder.

Örnek 2.1 Aşağıdaki şekilde devrelerden hangisi, kombinasyonel kompozisyon kurallarına göre kombinasyonel devrelerdir?

![şekil2.7](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-7.png)

Çözüm: Devre (a) kombinasyoneldir. İki kombinasyonel devre elemanından (inverterler I1 ve I2) yapılmıştır. Üç düğümü vardır: n1, n2 ve n3. n1, devreye ve I1'e bir giriştir; n2, I1'in çıkışı ve I2'nin girişi olan dahili bir düğümdür; n3, devrenin ve I2'nin çıkışıdır. (b) kombinasyonel değildir, çünkü döngüsel bir yol vardır: XOR'un çıktısı, girdilerinden birine geri beslenir. Dolayısıyla, n4'te başlayan döngüsel bir yol XOR'dan n5'e geçer ve n4'e geri döner. (c) kombinasyoneldir. (d) kombinasyonel değildir, çünkü düğüm n6, hem I3 hem de I4'ün çıkış terminallerine bağlanır. (e) birleşimseldir, daha büyük bir birleşimsel devre oluşturmak için bağlanan iki birleşimsel devreyi gösterir. (f) iki element arasında döngüsel bir yola sahip olduğu için birleşimsel kompozisyon kurallarına uymaz. Elemanların işlevlerine bağlı olarak, bir birleşimsel devre olabilir veya olmayabilir.

Mikroişlemciler gibi büyük devreler çok karmaşık olabilir, bu nedenle karmaşıklığı yönetmek için Bölüm 1'deki ilkeleri kullanıyoruz. Bir devreyi iyi tanımlanmış bir arayüze ve işleve sahip bir kara kutu olarak görmek, bir soyutlama ve modülerlik uygulamasıdır. Devreyi daha küçük devre elemanlarından oluşturmak bir hiyerarşi uygulamasıdır. Kombinasyonel kompozisyon kuralları, bir disiplin uygulamasıdır.

Bir birleşimsel devrenin işlevsel özelliği genellikle bir doğruluk tablosu veya bir Boole denklemi olarak ifade edilir. Sonraki bölümlerde, herhangi bir doğruluk tablosundan bir Boole denkleminin nasıl çıkarılacağını ve denklemleri basitleştirmek için Boole cebri ve Karnaugh haritalarının nasıl kullanılacağını açıklayacağız. Mantık kapılarını kullanarak bu denklemlerin nasıl uygulanacağını ve bu devrelerin hızının nasıl analiz edileceğini gösteriyoruz.

NOT: Kombinasyonel kompozisyon kuralları yeterlidir ancak kesinlikle gerekli değildir. Bu kurallara uymayan bazı devreler, çıkışlar yalnızca girişlerin mevcut değerlerine bağlı olduğu sürece hala kombinasyoneldir. Bununla birlikte, garip devrelerin kombinasyonel olup olmadığını belirlemek daha zordur, bu nedenle genellikle kombinasyonel devreler inşa etmenin bir yolu olarak kendimizi kombinasyonel kompozisyonla sınırlayacağız.

# 2.2 Boolean Denklemleri

Boole denklemleri, DOĞRU veya YANLIŞ olan değişkenlerle ilgilenir, bu nedenle dijital mantığı tanımlamak için mükemmeldir. Bu bölüm, Boole denklemlerinde yaygın olarak kullanılan bazı terminolojiyi tanımlar, ardından doğruluk tablosu verilen herhangi bir mantık işlevi için bir Boole denkleminin nasıl yazılacağını gösterir.

## 2.2.1 Terminoloji

A değişkeninin tamamlayıcısı, ters A'dır. Değişken veya onun tamamlayıcısı, "literal" olarak adlandırılır. Örneğin, A, A’, B ve B’ literal değerlerdir. A'ya değişkenin gerçek biçimi ve A’ 'ya tamamlayıcı biçim diyoruz; "Gerçek biçim", A'nın DOĞRU olduğu anlamına gelmez, yalnızca A'nın üzerinde bir çizgi olmadığı anlamına gelir.

Bir veya daha fazla literal değerin AND işlemine tabi tutulmasına product veya implicant denir. A’B, AB’C’ ve B, üç değişkenli bir fonksiyonun tüm sonuçlarıdır. Bir minterm, işlevin tüm girdilerini içeren bir product işlemidir. A’B’C’, A, B ve C üç değişkeninin bir fonksiyonu için bir mintermdir, ancak AB’, C'yi içermediği için değildir. Benzer şekilde, bir veya daha fazla değişmezin VEYA'sına sum denir. Bir maxterm, fonksiyonun tüm girdilerini içeren bir sum işlemidir. A + B’ + C, A, B ve C olmak üzere üç değişkenli bir fonksiyon için bir maxterm leridir.

Boole denklemlerini yorumlarken işlem sırası önemlidir. Y=A+BC, Y=(A OR B) VE C veya Y = A OR (B AND C) bu iki ifadeden hangisinin yerine geçer? Boole denklemlerinde, NOT en yüksek önceliğe sahiptir, ardından AND ve ardından OR gelir. Tıpkı sıradan denklemlerde olduğu gibi, çarpımlar toplamlardan önce gerçekleştirilir. Bu nedenle denklem Y = A OR (B AND C) olarak okunur. Denklem 2.1, işlemlerin sırasına ilişkin başka bir örnek verir.

A’B + BCD’ = ((A’)B) + ((BC)D’))

## 2.2.2 Sum-of-Products Form

N girdiden oluşan doğruluk tablosu, girişlerin her olası değeri için bir tane olmak üzere 2<sup>N</sup> satır içerir. Bir doğruluk tablosundaki her satır, o satır için DOĞRU olan bir minterm ile ilişkilendirilir. Aşağıdaki şekil, A ve B olmak üzere iki girişin doğruluk tablosunu göstermektedir. Her satır, ilgili mintermini gösterir. Örneğin, ilk satır için minterm A’B’ 'dir çünkü A = 0, B = 0 olduğunda A’B’ DOĞRUDUR. Mintermler 0 ile başlayarak numaralandırılır; üst sıra minterm 0, m0'a, sonraki satır minterm 1'e, m1'e vb. karşılık gelir.

![şekil2.8](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-8.png)

Çıktı Y'nin DOĞRU olduğu mintermlerin her birini toplayarak herhangi bir doğruluk tablosu için bir Boole denklemi yazabiliriz. Örneğin, üstteki Şekide, mavi daire içinde gösterilen Y çıktısının TRUE olduğu yalnızca bir satır (veya minterm) vardır. Böylece, Y = A’B. Alltaki Şekil, çıktının TRUE olduğu birden fazla satıra sahip bir doğruluk tablosunu göstermektedir. Daire içindeki mintermlerin her birinin toplamını almak Y = A’B + AB verir:

![şekil2.9](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-9.png)

Bu, çarpımların toplamı (OR) olduğu için (minterm oluşturan AND'ler) bir fonksiyonun toplam çarpımlar kanonik biçimi(sum-of-products canonical form) olarak adlandırılır. Aynı işlevi yazmanın Y = B’A + BA gibi birçok yolu olmasına rağmen, mintermleri doğruluk tablosunda göründükleri sırayla sıralayacağız, böylece aynı doğruluk tablosu için her zaman aynı Boole ifadesini yazacağız. 

Çarpımların toplamı kanonik formu, Σ toplama sembolü kullanılarak sigma gösterimi ile de yazılabilir. Bu gösterimle, Yukarıdaki Şekildeki işlev şu şekilde yazılacaktır:
F(A,B) = Σ(m1, m3)
F(A,B) = Σ(1, 3)

Örnek 2.2 Ben Bitdiddle piknik yapıyor. Yağmur yağarsa ya da karıncalar olursa bundan zevk almaz. Sadece Ben piknikten hoşlanırsa TRUE çıkışı verecek bir devre tasarlayın.

Çözüm: Önce girişleri ve çıkışları tanımlayın. Girişler, karıncalar ve yağmur parametreleri; A ve R'dir. Karıncalar olduğunda A DOĞRU ve karıncalar olmadığında YANLIŞ'dır. Aynı şekilde yağmur yağdığında R DOĞRU ve güneş Ben'in üzerine gülümsediğinde YANLIŞ'dır. Çıktı, E, Ben’in piknik keyfi. Ben piknikten hoşlanıyorsa E DOĞRU, acı çekerse YANLIŞ. Aşağıdaki şekil, Ben’in piknik deneyimi için doğruluk tablosunu göstermektedir.

![şekil2.10](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-10.png)

Toplam çarpım formunu kullanarak denklemi şu şekilde yazıyoruz: E = A’ R’ veya E = Σ(0). Denklemi, Aşağıdaki şekilde gösterilen iki invertör ve iki girişli bir AND geçidi kullanarak oluşturabiliriz. Bu doğruluk tablosunu NOR işlevi olarak tanıyabilirsiniz. E = A NOR R = (A + R)'

![şekil2.11a](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-11a.png)

Aşağıdaki şekil NOR gerçekleştirimi göstermektedir.

![şekil2.11b](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-11b.png)

Ürünlerin toplamı formu, herhangi bir sayıda değişken içeren herhangi bir doğruluk tablosu için bir Boole denklemi sağlar. Aşağıdaki şekil rastgele üç girişli bir doğruluk tablosunu göstermektedir. Mantık fonksiyonunun toplam-çarpım biçimi denklemlerdeki gibidir.Ne yazık ki, çarpımların toplamı formu mutlaka en basit denklemi oluşturmaz. Bölüm 2.3'te aynı işlevi daha az terim kullanarak nasıl yazacağımızı gösteriyoruz.

![şekil2.12](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-12.png)

## Product-of-Sum Form

Boole işlevlerini ifade etmenin alternatif bir yolu, toplamların çarpımı kanonik biçimidir. Bir doğruluk tablosunun her satırı, o satır için YANLIŞ olan bir maksimum terime karşılık gelir. Örneğin, iki girişli bir doğruluk tablosunun ilk satırı için maxterm (A + B) 'dir çünkü (A + B), A = 0, B = 0 olduğunda YANLIŞ olur. Herhangi bir devre için bir Boole denklemini, çıktının FALSE olduğu makstermlerin her birinin AND'si olarak doğrudan doğruluk tablosundan yazabiliriz. Toplamların çarpımı kanonik biçimi, ürün sembolü Π kullanılarak pi gösterimi ile de yazılabilir.

Örnek 2.3 Aşağıdaki Şekilde doğruluk tablosu için toplamların çarpımı formunda bir denklem yazın.

![şekil2.13](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-13.png)

Çözüm: Doğruluk tablosunda çıktının YANLIŞ olduğu iki satır vardır. Dolayısıyla fonksiyon, toplamların çarpımı formunda Y = (A + B)(A’ + B) as veya pi gösterimi kullanılarak Y = Π(M0, M2) veya Y = Π(0, 2) şeklinde yazılabilir. İlk maxterm (A + B), herhangi bir AND 0 değeri 0 olduğu için A = 0, B = 0 için Y = 0 olduğunu garanti eder. Benzer şekilde, ikinci maksterm, (A’ + B), A = 1, B = 0 için Y = 0 olmasını garanti eder.

Benzer şekilde, Şekildeki Ben’in pikniği için bir Boole denklemi, 0’ların üç satırını daire içine alarak, toplamların çarpımı biçiminde yazılabilir. E = (A’ + R) (A + R’) (A’ + R’) veya E = Π (1, 2, 3). Bu, çarpımların toplamı denkleminden daha çirkin, E = A’ R’, ancak iki denklem mantıksal olarak eşdeğerdir. Çarpımların toplamı, bir doğruluk tablosunun yalnızca birkaç satırında çıktı TRUE olduğunda daha kısa bir denklem üretir; toplamların çarpımı, bir doğruluk tablosunun yalnızca birkaç satırında çıktı FALSE olduğunda daha basittir.

# 2.3. BOOLEAN CEBRİ
Önceki bölümde, bir doğruluk tablosu verilen bir Boole ifadesinin nasıl yazılacağını öğrendik. Ancak, bu ifade mutlaka en basit mantık kapıları kümesine götürmez. Matematiksel denklemleri basitleştirmek için cebiri kullandığınız gibi, Boolean denklemlerini basitleştirmek için Boole cebirini kullanabilirsiniz. Boole cebirinin kuralları, sıradan cebir kurallarına çok benzer, ancak bazı durumlarda daha basittir, çünkü değişkenlerin yalnızca iki olası değeri vardır: 0 veya 1. 

Boole cebri, doğru olduğunu varsaydığımız bir dizi aksiyoma dayanır. Aksiyomlar, bir tanımın kanıtlanamaması anlamında kanıtlanamaz. Bu aksiyomlardan, Boole cebirinin tüm teoremlerini kanıtlıyoruz.Bu teoremlerin pratik önemi büyüktür, çünkü bize daha küçük ve daha az maliyetli devreler üretmek için mantığı nasıl basitleştireceğimizi öğretirler.

Boole cebirinin aksiyomları ve teoremleri dualite ilkesine uyar. 0 ve 1 sembolleri ve • (VE) ve + (VEYA) operatörleri değiştirilirse, ifade yine de doğru olacaktır. Bir ifadenin ikilisini belirtmek için asal sembolü (′) kullanıyoruz.

## 2.3.1 Aksiyomlar
Aşağıdaki tablo, Boole cebirinin aksiyomlarını belirtir. Bu beş aksiyom ve ikilileri Boole değişkenlerini ve NOT, AND ve OR'nin anlamlarını tanımlar. Aksiyom A1, bir Boolean değişkeni B'nin 1 değilse 0 olduğunu belirtir. Aksiyomun değili A1′, değişkenin 0 değilse 1 olduğunu belirtir. A1 ve A1 ′ birlikte, bize 0 ve 1’lerin Boole veya ikili alanında çalıştığımızı söyler. Aksiyomlar A2 ve A2' - NOT işlemini tanımlar. A3 ila A5 aksiyomları AND'yi tanımlar; onların değilleri, A3′ ila A5′ OR'yi tanımlar.

![şekil2.T1](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T1.png)

## Bir Degiskene ait Teoremler
Aşağıdaki tablodaki T1 ila T5 teoremleri, bir değişken içeren denklemlerin nasıl basitleştirileceğini açıklamaktadır. 

![şekil2.T2](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T2.png)

Özdeşlik teoremi T1, herhangi bir Boole değişkeni için B, B VE 1 = B olduğunu belirtir. Aynı zamanda değil durumu, B OR 0 = B olduğunu belirtir. Donanımda, aşağıdaki şekilde gösterildiği gibi, T1, iki girişli bir AND geçidinin bir girişi her zaman 1 ise, AND geçidini kaldırıp onu değişken girişe (B) bağlı bir kabloyla değiştirebileceğimiz anlamına gelir. Benzer şekilde, T1 ′, iki girişli bir OR geçidinin bir girişi her zaman 0 ise, OR geçidini B'ye bağlı bir tel ile değiştirebileceğimiz anlamına gelir. Genel olarak, kapılar para, güç ve gecikmeye mal olur, bu nedenle bir kapıyı kabloyla değiştirmek faydalıdır.

![şekil2.14](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-14.png)

Boş eleman teoremi, T2, B AND 0'ın her zaman 0'a eşit olduğunu söyler. Bu nedenle, 0, diğer herhangi bir girdinin etkisini geçersiz kıldığından, AND işlemi için boş öğe olarak adlandırılır. Dual, B OR 1'in her zaman 1'e eşit olduğunu belirtir. Bu nedenle, 1, OR işlemi için boş öğedir.  Donanımda, Şekil alt ortada gösterildiği gibi, bir AND geçidinin bir girişi 0 ise, AND geçidini LOW (0'a) bağlı bir tel ile değiştirebiliriz. Benzer şekilde, bir OR geçidinin bir girişi 1 ise, OR geçidini HIGH (1'e) bağlı bir tel ile değiştirebiliriz. 

Idempotency, T3, bir değişkenin VE kendisinin sadece kendisine eşit olduğunu söyler. Benzer şekilde, bir değişken VEYA'nın kendisi kendisine eşittir. Teorem adını Latin köklerinden alır: idem (aynı) ve güçlü (güç). İşlemler, onlara koyduğunuz şeyin aynısını döndürür. Şekil alt sağ idempotency'nin bir kapının bir kabloyla değiştirilmesine yine izin verdiğini göstermektedir.

İnvolüsyon, T4, bir değişkeni iki kez tamamlamanın orijinal değişkenle sonuçlandığını söylemenin süslü bir yoludur. Dijital elektronikte iki yanlış bir doğru yapar. Seri haldeki iki invertör mantıksal olarak birbirini iptal eder ve Şekil sağ üstte gösterildiği gibi mantıksal olarak bir kabloya eşdeğerdir. T4'ün ikilisi kendisidir.


Tamamlayıcı teoremi, T5 (şekil sağ orta/alt), bir değişkenin VE onun tamamlayıcısının 0 olduğunu belirtir (çünkü bunlardan birinin 0 olması gerekir). Ve dualite ile, bir değişken VEYA onun tamamlayıcısı 1'dir (çünkü bunlardan birinin 1 olması gerekir).
