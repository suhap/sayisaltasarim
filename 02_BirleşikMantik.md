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

Boş eleman teoremi, T2, B AND 0'ın her zaman 0'a eşit olduğunu söyler. Bu nedenle, 0, diğer herhangi bir girdinin etkisini geçersiz kıldığından, AND işlemi için boş öğe olarak adlandırılır. Dual, B OR 1'in her zaman 1'e eşit olduğunu belirtir. Bu nedenle, 1, OR işlemi için boş öğedir.  Donanımda, aşağıdaki şekil gösterildiği gibi, bir AND geçidinin bir girişi 0 ise, AND geçidini LOW (0'a) bağlı bir tel ile değiştirebiliriz. Benzer şekilde, bir OR geçidinin bir girişi 1 ise, OR geçidini HIGH (1'e) bağlı bir tel ile değiştirebiliriz. 

![şekil2.15](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-15.png)

Idempotency, T3, bir değişkenin VE kendisinin sadece kendisine eşit olduğunu söyler. Benzer şekilde, bir değişken VEYA'nın kendisi kendisine eşittir. Teorem adını Latin köklerinden alır: idem (aynı) ve güçlü (güç). İşlemler, onlara koyduğunuz şeyin aynısını döndürür. Aşağıdaki şekil idempotency'nin bir kapının bir kabloyla değiştirilmesine yine izin verdiğini göstermektedir.

![şekil2.16](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-16.png)

İnvolüsyon, T4, bir değişkeni iki kez tamamlamanın orijinal değişkenle sonuçlandığını söylemenin süslü bir yoludur. Dijital elektronikte iki yanlış bir doğru yapar. Seri haldeki iki invertör mantıksal olarak birbirini iptal eder ve aşağıdaki şekilde gösterildiği gibi mantıksal olarak bir kabloya eşdeğerdir. T4'ün ikilisi kendisidir.

![şekil2.17](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-17.png)

Tamamlayıcı teoremi, T5 (aşağıdaki şekil), bir değişkenin VE onun tamamlayıcısının 0 olduğunu belirtir (çünkü bunlardan birinin 0 olması gerekir). Ve dualite ile, bir değişken VEYA onun tamamlayıcısı 1'dir (çünkü bunlardan birinin 1 olması gerekir).

![şekil2.18](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-18.png)

## Birden çok Degiskene ait Teoremler
Aşağıdaki tabloda T6 ila T12 teoremleri, birden fazla Boole değişkenini içeren denklemlerin nasıl basitleştirileceğini açıklar.

![şekil2.T3](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T3.png)

Değişim ve birleşimlilik, T6 ve T7, geleneksel cebirde olduğu gibi çalışır. Komütatiflik ile, bir VE veya VEYA işlevi için girişlerin sırası, çıktının değerini etkilemez. İlişkilendirme ile, belirli girdi grupları, çıktının değerini etkilemez.

Dağılım teoremi, T8, geleneksel cebirdeki ile aynıdır, ancak ikili, T8 ′ değildir. T8'e göre, AND, OR üzerinden dağıtır ve T8 ′ ile OR, AND üzerinden dağıtır. Geleneksel cebirde, çarpma toplamaya dağıtılır ancak toplama, çarpma üzerinden dağıtılmaz, böylece (B + C) × (B + D) ≠ B + (C × D).

Örtme, birleştirme ve fikir birliği teoremleri, T9 ila T11, gereksiz değişkenleri ortadan kaldırmamıza izin verir. Biraz düşünerek, kendinizi bu teoremlerin doğru olduğuna ikna edebilmelisiniz.

De Morgan'ın Teoremi, T12, dijital tasarımda özellikle güçlü bir araçtır. Teorem, tüm terimlerin çarpımının tamamlamasının, her terimin tamamlayıcısının toplamına eşit olduğunu açıklar. Benzer şekilde, tüm terimlerin toplamının tamamlayıcısı, her terimin tamamlayıcısının ürününe eşittir.

De Morgan'ın teoremine göre, bir NAND geçidi, ters girdilere sahip bir OR geçidine eşdeğerdir. Benzer şekilde, bir NOR geçidi, ters girdilere sahip bir AND geçidine eşdeğerdir. Aşağıdaki şekil, NAND ve NOR kapıları için bu De Morgan eşdeğer kapılarını göstermektedir. Her bir işlev için gösterilen iki sembole ikili denir. Mantıksal olarak eşdeğerdirler ve birbirlerinin yerine kullanılabilirler.

![şekil2.19](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-19.png)

Ters çevirme çemberi bir balon olarak adlandırılır. Sezgisel olarak, bir baloncuğun kapıdan "itilmesinin" diğer taraftan çıkmasına ve kapının gövdesini AND'den OR'a veya tersi yönde çevirmesine neden olduğunu hayal edebilirsiniz. Örneğin, yukaridaki şekil'deki NAND geçidi, çıkışta bir balon bulunan bir AND gövdesinden oluşur. Kabarcığı sola itmek, girişlerde kabarcıklar bulunan bir OR gövdesi ile sonuçlanır.Kabarcık itmenin temel kuralları şunlardır:
- Baloncukları geriye (çıkıştan) veya ileriye (girişlerden) itmek, geçidin gövdesini AND'den OR'a veya tersi yönde değiştirir.
- Çıkıştan girişlere bir balonun itilmesi, tüm geçit girişlerine baloncuklar yerleştirir.
- Tüm kapı girişlerindeki baloncukları çıkışa doğru ileri itmek, çıkışta bir balon oluşturur.

Örnek 2.4: Allataki şekil, bir Boole fonksiyonu Y ve onun tamamlayıcısı Y’ için doğruluk tablosunu gösterir: De Morgan Teoremini kullanarak, Y'nin product-of-sums kanonik biçimini Y’ 'nin sum-of-products biçiminden türetin:

![şekil2.20](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-20.png)

Çözüm: Aşağıdaki şekil , Y’ 'nin içerdiği mintermleri (daire içine alınmış) göstermektedir: Y’ 'nin  sum-of-products kanonik biçimin;
Y’ = A’B’ + A’B

![şekil2.21](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-21.png)

Her iki tarafın tümleyicisini alarak ve De Morgan Teoremini iki kez uygulayarak şunu elde ederiz:
Y’’ = Y = (A’ B’ + A’B)’ = (A’B’)’(A’B)’ = (A + B)(A + B’)

## 2.3.5 Denklem indirgeme
Boole cebirinin teoremleri Boole denklemlerini basitleştirmemize yardımcı olur. Örneğin, Aşağıdkai şekilde doğruluk tablosundaki sum-of-products ifadesini düşünün: Y = A’B’ + AB’: Teorem T10'a göre, denklem Y = B’ 'ye sadeleştirilir: Bu, doğruluk tablosuna bakıldığında açıkça görülmüş olabilir. Genel olarak, daha karmaşık denklemleri basitleştirmek için birden çok adım gerekli olabilir.

![şekil2.9](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-9.png)

sum-of-products denklemlerini basitleştirmenin temel ilkesi, PA + PA’ = P ilişkisini kullanarak terimleri birleştirmektir, burada P herhangi bir dolaylı olabilir. Bir denklem ne kadar basitleştirilebilir? Mümkün olan en az etkiyi kullanırsa en aza indirilecek sum-of-products biçiminde bir denklem tanımlarız. Aynı sayıda etkiye sahip birkaç denklem varsa, en az olan en az değişmez değere sahip olandır.

Bir implicant, daha az değişmez değerle yeni bir implikant oluşturmak için denklemdeki diğer herhangi bir implicant ile birleştirilemezse, birincil implikant olarak adlandırılır. Minimal bir denklemdeki sonuçların tümü birincil çıkarımlar(implikant) olmalıdır. Aksi takdirde, değişmez değerlerin sayısını azaltmak için birleştirilebilirler. 

Örnek 2.6 A’B’C’ + AB’C’ + AB’C ifadesini sadeleştiriniz.

Çözüm: Orijinal denklemle başlıyoruz ve aşağıdaki tabloda gösterildiği gibi Boole teoremlerini adım adım uyguluyoruz. Bu noktada denklemi tamamen basitleştirdik mi? Hadi daha yakından bakalım. 

![şekil2.T4](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T4.png)

Orijinal denklemden, A’B’C’ ve AB’C’ mintermleri yalnızca A değişkeninde farklılık gösterir. Böylece mintermleri birleştirerek B’C’ 'yi oluşturduk. Ancak, orijinal denkleme bakarsak, son iki minterm AB’C’ ve AB’C 'nin de tek bir değişmez değerle (C ve C’) farklılık gösterdiğini not ederiz. Böylece, aynı yöntemi kullanarak, bu iki mintermi birleştirerek minterm AB’ 'yi oluşturabilirdik. Etkilenen B’C’ ve AB’ 'nin minterm AB’C’ 'yi paylaştığını gösteririz.

Öyleyse, minterm çiftlerinden yalnızca birini sadeleştirmek zorunda mıyız yoksa ikisini de basitleştirebilir miyiz? İdempotens teoremini kullanarak, terimleri istediğimiz kadar çoğaltabiliriz: B = B + B + B + B .... Bu prensibi kullanarak, aşağıdaki tabloda gösterildiği gibi denklemi iki asal çarpımı olan B C + AB'ye tamamen sadeleştiriyoruz.

![şekil2.T5](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T5.png)

Biraz mantığa aykırı olsa da, bir etkiyi genişletmek (örneğin, AB'yi ABC + ABC'ye dönüştürmek) bazen denklemleri en aza indirmede yararlıdır. Bunu yaparak, başka bir minterm ile birleştirilmek (paylaşılmak) için genişletilmiş mintermlerden birini tekrarlayabilirsiniz.

Bir Boole denklemini Boole cebri teoremleriyle tamamen basitleştirmenin biraz deneme yanılma gerektirebileceğini fark etmiş olabilirsiniz. Bölüm 2.7, süreci kolaylaştıran Karnaugh haritaları adı verilen yöntemsel bir tekniği açıklar.

Mantıksal olarak eşdeğer kalmaya devam ederse neden bir Boole denklemini basitleştirmeye çalışalım? Basitleştirme işlevi fiziksel olarak uygulamak için kullanılan kapıların sayısını azaltır, böylece daha küçük, daha ucuz ve muhtemelen daha hızlı hale getirir. Bir sonraki bölümde mantık geçitleriyle Boole denklemlerinin nasıl uygulanacağı açıklanmaktadır.

# 2.4 Lojik ifadelerden Lojik Kapılara (sematik)
Şematik, elemanları ve bunları birbirine bağlayan telleri gösteren bir dijital devrenin diyagramıdır.  Örneğin, aşağıdaki şekilde, favori mantık denklemin (Y = A'B'C' + AB'C' + AB'C) olası bir donanım uygulamasını göstermektedir.

![şekil2.23](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-23.png)

Şemaları tutarlı bir şekilde çizerek, bunların okunmasını ve hata ayıklamasını kolaylaştırıyoruz. Genel olarak aşağıdaki kurallara uyacağız:
- Girişler, şematiğin sol (veya üst) tarafındadır.
- Çıkışlar, bir şemanın sağ (veya alt) tarafındadır.
- Mümkün olduğunda kapılar soldan sağa akmalıdır.
- Düz kablolar, çok köşeli kablolardan daha iyidir (karmaşık teller, devrenin ne yaptığını düşünmek yerine teli takip etmek gibi zihinsel çabayı gerektirir).
- Kablolar her zaman bir T bağlantısında bağlanır. 
- Tellerin kesiştiği nokta, teller arasındaki bir bağlantıyı gösterir. 
- Noktasız kesişen kablolar bağlantı yapmaz.  
Son üç kısıt aşağıdaki şekilde görülmektedir. 

![şekil2.24](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-24.png)

Çarpımların toplamı formundaki herhangi bir Boole denklemi, 2.23 şekile benzer bir sistematik yolla şematik olarak çizilebilir. İlk olarak, girdiler için sütunlar çizin. Gerekirse tamamlayıcı girişler sağlamak için inverterleri bitişik sütunlara yerleştirin. Mintermlerin her biri için sıra sıra AND kapıları çizin. Ardından, her çıktı için, o çıktıyla ilgili mintermlere bağlı bir OR geçidi çizin. Bu stile programlanabilir mantık dizisi (PLA) adı verilir çünkü invertörler, AND geçitleri ve OR kapıları sistematik bir şekilde dizilmiştir. 

Aşağıdaki şekil, geçen son derste Boole cebri kullanarak bulduğumuz basitleştirilmiş denklemin bir uygulamasını göstermektedir. Basitleştirilmiş devrenin bir 2.23 şekilden önemli ölçüde daha az donanıma sahip olduğuna dikkat edin. Daha az girişli kapılar kullandığı için daha hızlı da olabilir.

![şekil2.25](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-25.png)

Kapıların ters çevrilmesinden yararlanarak kapı sayısını daha da azaltabiliriz (tek bir invertörle de olsa). B’ C’  'nin ters girdilere sahip bir AND olduğunu gözlemleyin. aşağıdaki şekil, C'deki inverteri ortadan kaldırmak için bu optimizasyonu kullanan bir şematik gösterir. De Morgan teoremine göre, ters girdilerle AND'nin bir NOR geçidine eşdeğer olduğunu hatırlayın. Uygulama teknolojisine bağlı olarak, en az sayıda geçidi kullanmak veya diğerlerine göre tercihe göre belirli kapı tiplerini kullanmak daha ucuz olabilir. Örneğin, CMOS uygulamalarında AND'ler ve OR'ler yerine NAND'ler ve NOR'lar tercih edilir.

![şekil2.26](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-26.png)

Birçok devrenin, her biri girişlerin ayrı bir Boole işlevini hesaplayan birden fazla çıkışı vardır. Her çıktı için ayrı bir doğruluk tablosu yazabiliriz, ancak tüm çıktıları tek bir doğruluk tablosuna yazmak ve tüm çıktılarla bir şematik çizim yapmak genellikle uygundur.

Örnek 2.7: Dekan, bölüm başkanı, öğretim görevlisi ve yurt müdürü bazen konferans salonunu kullanmaktadır. Ne yazık ki, ara sıra aynı anda kullanmak istemektedirler. Bu durum Dekan'ın huysuz mütevellilerle bağış toplama toplantısı yurdun BTB partisiyle aynı anda gerçekleşmesi gibi felaketlere yol açıyorlar. Bu durumu çözmek için Alyssa P. Hacker, bir oda rezervasyon sistemi tasarlaması için çağrıldı.

Sistemin dört girişi, A3, ..., A0 ve dört çıkışı, Y3, ..., Y0 vardır. Bu sinyaller A3:0 ve Y3:0  olarak da yazılabilir. Her kullanıcı, ertesi gün için  konferans salonunu talep ettiğinde bildirir. Sistem,  konferans salonunu en yüksek öncelikli kullanıcıya vererek en fazla bir çıktı ileri sürer. Sistemin bedelini ödeyen dekan en yüksek önceliği talep eder. Bölüm başkanı, öğretim görevlisi ve yurt müdürü  azalan önceliğe sahiptir. 

Sistem için bir doğruluk tablosu ve Boole denklemleri yazın. Bu işlevi yerine getiren bir devre çizin.

Çözüm: Bu işleve dört girişli öncelik devresi denir. Sembolü ve doğruluk tablosu gösterilmektedir.

![şekil2.27](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-27.png)

Her çıktıyı çarpımların toplamı biçiminde yazabilir ve denklemleri Boole cebri kullanarak azaltabiliriz. Bununla birlikte, basitleştirilmiş denklemler, fonksiyonel açıklamadan (ve doğruluk tablosundan) incelenerek kolayca çıkarılabilir. 

A3 bir ise Y3 DOĞRUDUR, yani Y3 = Α3.
A2 bir ise ve A3 sıfır ise Y2 DOĞRU'dur, bu nedenle Y2 = A’3 A2
A1 bir ise ve yüksek öncelikli girişlerden hiçbiri bir değilse Y1 DOĞRUDUR: Y1 = A’3A’2A1 
A0 ve başka hiçbir giriş bir olmadığında Y0 DOĞRUDUR iddia edildi: Y0 = A’3A’2A’1A0

Şematik, şekil 2.28 de gösterilmiştir. Deneyimli bir tasarımcı, genellikle inceleme yoluyla bir mantık devresi uygulayabilir. Açık bir özellik verildiğinde, kelimeleri denklemlere ve denklemleri kapılara çevirin.

![şekil2.28](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-28.png)

Öncelikli devrede A3 bir ise, çıkışların diğer girişlerin ne olduğunu umursamadığına dikkat edin. Çıktının önemsemediği girdileri tanımlamak için X sembolünü kullanıyoruz. Şekil 2.29, dört-girişli öncelikli devre doğruluk tablosunun önemsemeden çok daha küçük hale geldiğini göstermektedir. Bu doğruluk tablosundan, X’lerin girişlerini göz ardı ederek Boole denklemlerini çarpımların toplamı formunda kolayca okuyabiliriz. 

![şekil2.29](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-29.png)


# ÇOK SEViYELi BiRLESiK MANTIK
Çarpımların toplamı formundaki mantık, iki seviyeli mantık olarak adlandırılır, çünkü bir VEYA kapıları seviyesine bağlı bir AND kapıları seviyesine bağlı değişmez değerlerden oluşur. Tasarımcılar genellikle ikiden fazla mantık kapısı seviyesi olan devreler inşa ederler. Bu çok seviyeli kombinasyonel devreler, iki seviyeli muadillerinden daha az donanım kullanabilir. Kabarcık itme, çok seviyeli devrelerin analizinde ve tasarlanmasında özellikle yararlıdır.

## 2.5.1 Donanım Azaltma
Bazı mantık işlevleri, iki seviyeli mantık kullanılarak oluşturulduklarında çok büyük miktarda donanım gerektirir. Dikkate değer bir örnek, çoklu değişkenlerin XOR fonksiyonudur. Örneğin, şimdiye kadar incelediğimiz iki seviyeli teknikleri kullanarak üç girişli bir XOR oluşturmayı düşünün.

Tek sayıda giriş TRUE olduğunda bir N-girişli XOR'un bir TRUE çıktı oluşturduğunu hatırlayın. Şekil 2.20, TRUE çıktılar üreten satırlar daire içine alınmış üç girişli bir XOR için doğruluk tablosunu göstermektedir. Doğruluk tablosundan, Y = A'B'C+A'B'C'+AB'C'+ABC deklemini çarpımların toplamı biçiminde bir Boole denklemi okuyoruz. Ne yazık ki, bu denklemi daha az etkiye indirgemenin bir yolu yoktur.

![şekil2.30](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-30.png)

Öte yandan, A ⊕ B ⊕ C = (A ⊕ B) ⊕ C (şüpheniz varsa bunu mükemmel tümevarım ile kendinize kanıtlayın). Bu nedenle, üç girişli XOR, Şekil 2.31'de gösterildiği gibi, iki girişli XOR'un bir kademesinden oluşturulabilir.

![şekil2.31](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-31.png)

Benzer şekilde, sekiz girişli bir XOR, iki seviyeli toplam ürün uygulaması için 128 sekiz girişli AND geçidi ve bir 128 girişli OR geçidi gerektirir. Çok daha iyi bir seçenek, Şekil 2.32'de gösterildiği gibi, iki girişli XOR geçitlerinden oluşan bir ağaç kullanmaktır.

![şekil2.32](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-32.png)

Belirli bir mantık işlevinin en iyi çok düzeyli uygulamasını seçmek basit bir süreç değildir. Dahası, "en iyi" birçok anlama sahiptir: en az kapı, en hızlı, en kısa tasarım süresi, en az maliyet, en az güç tüketimi. Bölüm 5'te, bir teknolojideki "en iyi" devrenin diğerinde mutlaka en iyi olmadığını göreceksiniz. Örneğin, AND'leri ve OR'leri kullanıyoruz, ancak CMOS'ta NAND'ler ve NOR'lar daha verimlidir. Biraz deneyimle, çoğu devre için inceleme yaparak iyi bir çok düzeyli tasarım oluşturabileceğinizi göreceksiniz. Bu kitabın geri kalanında devre örneklerini incelerken bu deneyimin bir kısmını geliştireceksiniz. Öğrenirken, çeşitli tasarım seçeneklerini keşfedin ve değiş tokuşları düşünün. Bilgisayar destekli tasarım (CAD) araçları, olası çok düzeyli tasarımların geniş bir alanında arama yapmak ve mevcut yapı taşları göz önüne alındığında kısıtlamalarınıza en uygun olanı aramak için de mevcuttur.

## 2.5.2 Tersleyici itme
Bölüm 1.7.6'dan CMOS devrelerinin AND'ler ve OR'ler yerine NAND'ları ve NOR'ları tercih ettiğini hatırlayabilirsiniz. Ancak denklemi NAND'lar ve NOR'lar ile çok düzeyli bir devreden inceleyerek okumak oldukça zor olabilir. Şekil 2.33, işlevi incelemeyle hemen netleşmeyen çok düzeyli bir devreyi göstermektedir. Kabarcık itme, bu devreleri yeniden çizmenin yararlı bir yoludur, böylece kabarcıklar birbirini götürür ve işlev daha kolay belirlenebilir. 

![şekil2.33](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-33.png)

Bölüm 2.3.3'teki ilkelere dayalı olarak, balon itme kuralları aşağıdaki gibidir:
- Devrenin çıkışından başlayın ve girişlere doğru ilerleyin.
- Son çıktıdaki kabarcıkları girişlere doğru geri itin, böylelikle (Y’) çıktısının tümleyicisi yerine çıktı cinsinden bir denklem (örneğin, Y) okuyabilirsiniz.
- Geriye doğru hareket ederek, her bir kapıyı kabarcıklar birbirini götürecek formda çizin. Mevcut geçitte bir giriş balonu varsa, önceki kapıyı bir çıkış balonuyla çizin. Mevcut geçitte bir giriş balonu yoksa, önceki kapıyı bir çıkış balonu olmadan çizin.

Şekil 2.34, Şekil 2.33 balon itme kurallarına göre nasıl yeniden çizileceğini gösterir.  Y çıkışından başlayarak, NAND geçidinin çıkışta ortadan kaldırmak istediğimiz bir balonu vardır. Çıkış balonunu, Şekil 2.34(a) gösterildiği gibi, ters girdilerle bir OR oluşturmak için geri itiyoruz. Sola doğru çalışırken, en sağdaki kapı, orta NAND geçidinin çıkış baloncuğunu iptal eden bir giriş balonuna sahiptir, bu nedenle Şekil 2.34(b) gösterildiği gibi hiçbir değişiklik gerekmez. Orta kapının giriş balonu yoktur, bu nedenle Şekil 2.34(c) gösterildiği gibi en soldaki kapıyı çıkış balonu olmayacak şekilde dönüştürürüz. Şimdi, girişler haricinde devredeki tüm kabarcıklar birbirini götürür, böylece fonksiyon, gerçek veya tamamlayıcı girişlerin AND'leri ve OR'leri açısından incelenerek okunabilir:
Y = A’B’C + D’

![şekil2.34](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-34.png)

Bu son noktanın vurgulanması için, Şekil 2.35, Şekil 2.34 mantıksal olarak eşdeğer bir devreyi göstermektedir. Dahili düğümlerin işlevleri mavi ile etiketlenmiştir. Serideki kabarcıklar birbirini götürdüğü için, Şekil 2.35 mantıksal olarak eşdeğer devreyi üretmek için orta kapının çıkışındaki ve en sağdaki kapının bir girişindeki kabarcıkları yok sayabiliriz.

![şekil2.35](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-35.png)

Örnek: Çoğu tasarımcı AND ve OR kapıları açısından düşünür, ancak NAND ve NOR kapılarını destekleyen CMOS mantığında Şekil 2.36 devreyi uygulamak istediğinizi varsayalım. Devreyi NAND'lara, NOR'lara ve invertörlere dönüştürmek için kabarcık itme özelliğini kullanın.

![şekil2.36](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-36.png)

Çözüm: Kaba kuvvet çözümü, Şekil 2.37 gösterildiği gibi, her AND geçidini bir NAND ve bir invertörle ve her OR geçidini bir NOR ve bir invertörle değiştirmektir. Bu sekiz kapı gerektirir. Kabarcığın önceki ters çevirme geçidi ile nasıl iptal edilebileceğini vurgulamak için, eviricinin arkadan değil öndeki balonla çizildiğine dikkat edin.

![şekil2.37](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-37.png)

Daha iyi bir çözüm için, Şekil 2.38(a) gösterildiği gibi, kabarcıkların işlevi değiştirmeden bir geçidin çıkışına ve sonraki geçidin girişine eklenebileceğini gözlemleyin. Nihai AND, Şekil 2.38(b) gösterildiği gibi bir NAND ve bir invertöre dönüştürülür. Bu çözüm yalnızca beş kapı gerektirir.

![şekil2.38](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-38.png)

## 2.6.1 illegal X Degeri
X sembolü, devre düğümünün bilinmeyen veya geçersiz bir değere sahip olduğunu gösterir. Bu genellikle aynı anda hem 0 hem de 1'e sürülüyorsa olur. Şekil 2.39, Y düğümünün hem YÜKSEK hem de DÜŞÜK sürüldüğü bir durumu gösterir. Çekişme adı verilen bu durum bir hata olarak değerlendirilir ve kaçınılması gerekir. Çekişmeli bir düğümdeki gerçek voltaj, YÜKSEK ve DÜŞÜK süren kapıların göreceli güçlerine bağlı olarak 0 ile VDD arasında bir yerde olabilir. Çoğu zaman, ama her zaman değil, yasak bölgededir. Çatışma ayrıca savaş kapıları arasında büyük miktarda güç akmasına neden olarak devrenin ısınmasına ve muhtemelen hasar görmesine neden olabilir.

![şekil2.39](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-39.png)

X değerleri ayrıca bazen devre simülatörleri tarafından başlatılmamış bir değeri belirtmek için kullanılır. Örneğin, bir girdinin değerini belirtmeyi unutursanız, simülatör sizi soruna karşı uyarmak için bunun bir X olduğunu varsayabilir.

Bölüm 2.4'te belirtildiği gibi, dijital tasarımcılar, doğruluk tablolarında "umursamıyorum" değerlerini belirtmek için X sembolünü de kullanırlar. İki anlamı karıştırmamaya dikkat edin. X bir doğruluk tablosunda göründüğünde, doğruluk tablosundaki değişkenin değerinin önemsiz olduğunu gösterir (0 veya 1 olabilir). X bir devrede göründüğünde, devre düğümünün bilinmeyen veya geçersiz bir değeri olduğu anlamına gelir.

## Kayan Z Degeri
Z sembolü, bir düğümün YÜKSEK veya DÜŞÜK sürülmediğini gösterir. Düğümün yüzen, yüksek empedans veya yüksek Z olduğu söyleniyor. Tipik bir yanılgı, kayan veya yönlendirilmemiş bir düğümün mantık 0 ile aynı olmasıdır. Gerçekte, sistem geçmişine bağlı olarak, yüzen bir düğüm 0 olabilir, 1 olabilir veya arada bir voltajda olabilir. Başka bir devre elemanı, düğümün değeri devre çalışmasıyla ilgili olduğunda düğümü geçerli bir mantık düzeyine sürdüğü sürece, bir yüzer düğüm, devrede bir hata olduğu anlamına gelmez.

Kayan bir düğüm oluşturmanın yaygın bir yolu, bir devre girişine bir voltaj bağlamayı unutmak veya bağlantısız bir girişin 0 değerine sahip bir girişle aynı olduğunu varsaymaktır. Bu hata, kayan giriş rastgele 0'dan 1'e değiştiğinden devrenin düzensiz davranmasına neden olabilir. Nitekim vücuttan statik elektrikle değişimi tetiklemek için devreye dokunmak yeterli olabilir. Sadece öğrencinin parmağını çipin üzerine basılı tuttuğu sürece doğru çalışan devreler gördük.

Şekil 2.40 gösterilen üç durumlu tampon, üç olası çıkış durumuna sahiptir: YÜKSEK (1), DÜŞÜK (0) ve kayan (Z). Üç durumlu tamponun bir A girişi, Y çıkışı ve E'yi etkinleştirmesi vardır. Etkinleştirme TRUE olduğunda, üç durumlu tampon, giriş değerini çıkışa aktararak basit bir tampon görevi görür. Etkinleştirme YANLIŞ olduğunda, çıkışın yüzmesine izin verilir (Z). 

![şekil2.40](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-40.png)

Şekilde 2.40 üç durumlu tampon aktif bir yüksek yetkiye sahiptir. Yani, etkinleştirme YÜKSEK (1) olduğunda, arabellek etkinleştirilir. Şekil 2.41, aktif düşük etkinleştirmeli bir üç durumlu tamponu göstermektedir. Etkinleştirme DÜŞÜK (0) olduğunda, arabellek etkinleştirilir. Giriş teline bir balon koyarak sinyalin düşük aktif olduğunu gösteriyoruz. Genellikle, adı E’ üzerine bir çubuk çizerek veya Eb veya Ebar adından sonra "b" veya "bar" harflerini ekleyerek aktif bir düşük girişi belirtiriz.

![şekil2.41](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-41.png)

Üç durumlu tamponlar genellikle birden fazla çipi bağlayan veri yollarında kullanılır. Örneğin, bir mikroişlemci, bir video denetleyici ve bir Ethernet denetleyicisi, bir kişisel bilgisayardaki bellek sistemiyle iletişim kurmaya ihtiyaç duyabilir. Her yonga, Şekil 2.42 gösterildiği gibi, üç durumlu tamponları kullanarak paylaşılan bir bellek veri yoluna bağlanabilir. Veriyoluna bir değer sürmek için bir seferde yalnızca bir çipin etkinleştirme sinyalini ileri sürmesine izin verilir. Diğer yongalar, bellekle konuşan yonga ile çekişmeye neden olmaması için kayan çıktılar üretmelidir. Herhangi bir çip, herhangi bir zamanda paylaşılan veriyolundaki bilgileri okuyabilir. Bu tür üç durumlu otobüsler bir zamanlar yaygındı. Bununla birlikte, modern bilgisayarlarda, çiplerin paylaşılan bir veri yolu yerine doğrudan birbirine bağlandığı noktadan noktaya bağlantılarla daha yüksek hızlar mümkündür.

![şekil2.42](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-42.png)

# 2.7 Harita Yöntemi ile Sadelestirme(Karnaugh Map Minimization)
Boole cebirini kullanarak Boole denklemlerinin birkaç minimizasyonu üzerinde çalıştıktan sonra, dikkatli olmazsanız, bazen basitleştirilmiş bir denklem yerine tamamen farklı bir denklemle karşılaşacağınızı fark edeceksiniz. Karnaugh haritaları (K-haritaları), Boole denklemlerini basitleştirmek için grafiksel bir yöntemdir. 1953 yılında Bell Labs'ta bir telekomünikasyon mühendisi olan Maurice Karnaugh tarafından icat edildi. K-haritaları, dört değişkene kadar olan problemlerde iyi çalışır. Daha da önemlisi, Boole denklemlerini manipüle etme konusunda fikir verirler.

Mantık küçültmenin terimleri birleştirmeyi içerdiğini hatırlayın. Dolaylı bir P içeren iki terim ve bazı değişken A'nın gerçek ve tamamlayıcı formları, A'yı ortadan kaldırmak için birleştirilir: PA + PA’ = P Karnaugh haritaları, bu birleştirilebilir terimleri bir ızgarada yan yana koyarak görmeyi kolaylaştırır.

Şekil 2.43, üç girişli bir fonksiyon için doğruluk tablosunu ve K-haritasını gösterir. K haritasının üst satırı, A ve B girişleri için dört olası değeri verir. Sol sütun, C girişi için iki olası değeri verir. K-haritasındaki her kare, doğruluk tablosundaki bir satıra karşılık gelir ve o satır için Y çıktısının değerini içerir. Örneğin, sol üst kare, doğruluk tablosundaki ilk satıra karşılık gelir ve ABC = 000 olduğunda çıktı değeri Y = 1 olduğunu belirtir. Tıpkı doğruluk tablosundaki her satır gibi, bir K-haritasındaki her kare tek bir mintermi temsil eder . Açıklama amacıyla, Şekil 2.43(c), K-haritasındaki her kareye karşılık gelen mintermi göstermektedir.

![şekil2.43](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-43.png)

Her kare veya minterm, tek bir değişkendeki değişiklikle bitişik kareden farklıdır. Bu, bitişik karelerin, biri dışında, bir karede gerçek biçimde ve diğerinde tamamlayıcı biçimde görünen tüm değişmez değerleri paylaştığı anlamına gelir. Örneğin, A’B’C’ ve A’B’C mintermlerini temsil eden kareler bitişiktir ve yalnızca C değişkeninde farklılık gösterir. Üst sıradaki A ve B kombinasyonlarının tuhaf bir sırada olduğunu fark etmiş olabilirsiniz: 00, 01, 11, 10. Bu düzene Gri kod denir. Sıradan ikili düzenden (00, 01, 10, 11) farklıdır, çünkü bitişik girişler yalnızca tek bir değişkende farklılık gösterir. Örneğin, 01: 11 yalnızca A'yı 0'dan 1'e değiştirirken, 01: 10, A'yı 1'den 0'a ve B'yi 0'dan 1'e değiştirir. Dolayısıyla, kombinasyonları ikili sırayla yazmak, bitişik kareler için istediğimiz özelliği üretmezdi. sadece bir değişkende farklılık gösterir.

K-haritası da "etrafını sarar". En sağdaki kareler, en soldaki karelere etkin bir şekilde bitişiktir, çünkü bunlar yalnızca bir değişken olan A'da farklılık gösterirler. Diğer bir deyişle, haritayı alıp bir silindire yuvarlayabilir, sonra da karelerin uçlarını birleştirebilirsiniz. bir simit (yani bir halka) oluşturmak için silindir ve yine de bitişik karelerin yalnızca bir değişkende farklılık göstereceğini garanti eder.

# 2.7.1 Döngüsel Düşünme

Şekil 2.43, K-haritasında, sol sütundaki 1’lerle gösterildiği gibi, denklemde yalnızca iki minterm vardır, A’B’C’ ve A’B’C. Mintermleri K-haritasından okumak, çarpımların toplamı formundaki denklemleri doğrudan doğruluk tablosundan okumaya tam olarak eşdeğerdir.

Daha önce olduğu gibi, çarpımların toplamı formundaki denklemleri en aza indirmek için Boole cebirini kullanabiliriz.

Y = A’B’C’ + A’B’C = A’B’(C’ + C) = A’B’

K haritaları, Şekil 2.44 gösterildiği gibi, 1'leri bitişik karelerde daire içine alarak bu basitleştirmeyi grafiksel olarak yapmamıza yardımcı olur. Her daire için karşılık gelen implikantı yazıyoruz. Bölüm 2.2'den bir dolaylı ifadenin bir veya daha fazla değişmezin ürünü olduğunu unutmayın. Hem gerçek hem de tamamlayıcı formları daire içinde olan değişkenler, imanın dışında bırakılır. Bu durumda, C değişkeni hem gerçek formuna (1) hem de çemberde tamamlayıcı formuna (0) sahiptir, bu nedenle onu implicant'a dahil etmiyoruz. Başka bir deyişle, C'den bağımsız olarak A = B = 0 olduğunda Y DOĞRUDUR. Dolayısıyla, sonuç A’B’  'dir. K-haritası Boole cebri kullanarak ulaştığımız aynı cevabı verir.

![şekil2.44](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-44.png)

## 2.7.2 K-Maps ile Mantık Minimizasyonu
K haritaları, mantığı en aza indirmek için kolay bir görsel yol sağlar. Mümkün olan en az sayıda daire kullanarak haritadaki 1’lerin tüm dikdörtgen bloklarını daire içine almanız yeterlidir. Her daire mümkün olduğu kadar geniş olmalıdır. Daha sonra daire içine alınmış sonuçları okuyun.

Daha resmi olarak, bir Boole denkleminin en aza indirildiğini hatırlayın. en az sayıda asal çarpımın toplamı olarak yazılır. K-haritasındaki her daire bir içeriği temsil eder. Olası en büyük çemberler birincil çıkarımlardır.

Örneğin, Şekil 2.44 K-haritasında, A’B’C’ ve A’B’C, implikantlardır, ancak asal çıkarımlar değildir. Sadece A’B’, bu K-haritasında en önemli etkendir. K-haritasından küçültülmüş denklem bulma kuralları aşağıdaki gibidir:

- 1’leri kaplamak için gereken en az daireyi kullanın.
- Her dairedeki tüm kareler 1’leri içermelidir.
- Her daire, her yönde 2 (yani 1, 2 veya 4) karenin üssü olan dikdörtgen bir bloğu kapsamalıdır.
- Her daire mümkün olduğu kadar büyük olmalıdır.
- K-haritasının kenarlarını bir daire sarabilir.
- K-haritasındaki bir 1, daha az dairenin kullanılmasına izin veriyorsa, birden çok kez daire içine alınabilir

Örnek 2.9 Şekil 2.45 K-haritasıyla Y = F (A, B, C) fonksiyonumuz olduğunu varsayalım. K-haritasını kullanarak denklemi en aza indirin.

![şekil2.45](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-45.png)

Çözüm: Şekil 2.46 gösterildiği gibi, mümkün olduğunca az daire kullanarak K-haritasındaki 1'leri daire içine alın. K-haritasındaki her daire bir asal anlamı temsil eder ve her dairenin boyutu ikinin bir kuvvetidir (2 × 1 ve 2 × 2). Çemberde sadece doğru olarak veya sadece tamamlayıcı biçimde görünen değişkenleri yazarak, her çember için birincil anlamı oluştururuz.

Örneğin, 2×1 çemberde, B'nin gerçek ve tamamlayıcı biçimleri çembere dahil edilmiştir, bu nedenle B'yi asal implicant'a dahil etmiyoruz. Bununla birlikte, yalnızca A (A) 'nın gerçek formu ve C (C’) nin tamamlayıcı formu bu çemberdedir, bu nedenle bu değişkenleri asal dolaylı AC’ 'ye dahil ederiz. Benzer şekilde, 2×2 çemberi B = 0 olan tüm kareleri kapsar, yani asıl önemli olan B’  'dir.

![şekil2.46](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-46.png)

Sağ üstteki karenin (minterm) iki kez nasıl kaplandığına dikkat edin ve birincil dolaylı daireleri olabildiğince geniş yapın. Boole cebri tekniklerinde gördüğümüz gibi, bu, implikantın boyutunu küçültmek için bir mintermi paylaşmaya eşdeğerdir. Ayrıca, dört kareyi kaplayan dairenin K-haritasının kenarlarını nasıl çevrelediğine dikkat edin.

Örnek 2.10 Yedi bölümlü bir ekran kod çözücü, 4 bitlik bir veri girişi D3:0 alır ve 0'dan 9'a kadar bir rakam görüntülemek için ışık yayan diyotları kontrol etmek için yedi çıkış üretir. Yedi çıkışa genellikle a'dan g'ye kadar olan bölümler veya Sa-Sg denir , Şekil 2.47 tanımlandığı gibi. Rakamlar Şekil 2.48 gösterilmektedir. Çıktılar için bir doğruluk tablosu yazın ve Sa ve Sb çıktıları için Boole denklemlerini bulmak için K-haritalarını kullanın. Geçersiz giriş değerlerinin (10-15) boş bir okuma ürettiğini varsayın.

![şekil2.47](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-47.png)

![şekil2.48](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-48.png)

Çözüm: Doğruluk tablosu Tablo 2.6 verilmiştir. Örneğin, 0000 girişi Sg hariç tüm segmentleri açmalıdır.

![sekil2.6T](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T6.png)

Yedi çıktının her biri, dört değişkenli bağımsız bir işlevdir. Sa ve Sb çıktıları için K-haritaları Şekil 2.49 gösterilmektedir. Bitişik karelerin yalnızca tek bir değişkende farklılık gösterebileceğini unutmayın, bu nedenle satırları ve sütunları Gray kodu sırasına göre etiketleriz: 00, 01, 11, 10. Çıktı değerlerini karelere girerken bu sıralamayı da hatırlamaya dikkat edin.

![şekil2.49](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-49.png)

Sonra, asal sonuçları daire içine alın. Tüm 1'leri kapsayacak en az sayıda daire kullanın. Bir daire kenarların (dikey ve yatay) etrafını sarabilir ve 1 birden fazla daire içine alınabilir. Şekil 2.50, asal çarpımları ve basitleştirilmiş Boole denklemlerini gösterir.

![şekil2.50](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-50.png)

Asal ifadelerin minimal kümesinin benzersiz olmadığına dikkat edin. Örneğin, Sa K-haritasındaki 0000 girişi, D'<sub>2</sub>D'<sub>1</sub>D'<sub>0</sub> mintermini üretmek için 1000 girişiyle birlikte daire içine alındı. Daire, bunun yerine 0010 girişini içerebilir ve Şekil 2.51'de kesikli çizgilerle gösterildiği gibi bir D3D2D0 minterm üretebilirdi.

![şekil2.51](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-51.png)

Şekil 2.52 (bkz. sayfa 82), sol üst köşedeki 1'i kapatmak için asal olmayan bir dolaylının seçildiği yaygın bir hatayı göstermektedir. Bu minterm,  D'<sub>3</sub>D'<sub>2</sub>D'<sub>1</sub>D'<sub>0</sub> , minimal olmayan bir çarpımlar toplamı denklemi verir. Minterm, önceki iki şekilde yapıldığı gibi, daha büyük bir daire oluşturmak için bitişik olanlardan herhangi biriyle birleştirilebilirdi.

![şekil2.52](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-52.png)

## 2.7.3 Önemsenmeyen Durumlar
Doğruluk tablosu girdileri için "umursamıyorum" girişlerinin, bazı değişkenler çıktıyı etkilemediğinde tablodaki satır sayısını azaltmak için Bölüm 2.4'te tanıtıldığını hatırlayın. X simgesiyle gösterilirler, bu da girişin 0 veya 1 olabileceği anlamına gelir.

Önemsemeyin, çıktı değerinin önemsiz olduğu veya karşılık gelen girdi kombinasyonunun asla gerçekleşemeyeceği doğruluk tablosu çıktılarında da görünür. Bu tür çıktılar, tasarımcının takdirine bağlı olarak 0'lar veya 1'ler olarak ele alınabilir.

Bir K-haritasında, X'ler daha fazla mantık küçültmeye izin verir. 1’leri daha az veya daha büyük dairelerle kapatmaya yardımcı olurlarsa daire içine alınabilir, ancak yardımcı olmadıklarında daire içine alınmaları gerekmez.


Örnek 2.11   10 ila 15 arasındaki geçersiz girdi değerleri için çıktı değerleri umurumuzda değilse Örnek 2.10'u tekrarlayın.

Çözüm: K-haritası, Şekilde 2.53 umursamadığını temsil ettiği şekilde gösterilmiştir. Önemsizler 0 veya 1 olabileceğinden, 1’leri daha az veya daha büyük dairelerle kaplamamıza izin verip vermediğini umursamıyoruz. Daire içine alınmış umursamazlar 1'ler olarak kabul edilirken, daire içine alınmış olmayanlar 0'lar olarak kabul edilir. Sa segmenti için dört köşenin etrafına 2 × 2 kare sarmanın nasıl daire içine alındığını gözlemleyin. Önemsizlerin kullanılması mantığı büyük ölçüde basitleştirir.

![şekil2.53](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-53.png)

## 2.7.4 Büyük Resim
Boole cebri ve Karnaugh haritaları, mantık sadeleştirmenin iki yöntemidir. Nihayetinde amaç, belirli bir mantık işlevini uygulamak için düşük maliyetli bir yöntem bulmaktır.

Modern mühendislik uygulamalarında, mantık sentezleyicileri olarak adlandırılan bilgisayar programları, Bölüm 4'te göreceğimiz gibi, mantık işlevinin bir tanımından basitleştirilmiş devreler üretir. Büyük problemler için, mantık sentezleyicileri insanlardan çok daha etkilidir. Küçük sorunlar için, biraz deneyime sahip bir insan teftişle iyi bir çözüm bulabilir. Yazarların hiçbiri gerçek hayatta pratik bir problemi çözmek için bir Karnaugh haritasını kullanmadı. Ancak Karnaugh haritalarının altında yatan ilkelerden elde edilen içgörü değerlidir. Ve Karnaugh haritaları genellikle iş görüşmelerinde görünür!

# Birlesik Lojik Blokları
Birleşik mantık, daha karmaşık sistemler oluşturmak için genellikle daha büyük yapı blokları halinde gruplandırılır. Bu, yapı bloğunun işlevini vurgulamak için gereksiz kapı seviyesi ayrıntılarını gizleyen soyutlama ilkesinin bir uygulamasıdır. Bu tür üç yapı bloğunu zaten inceledik: tam toplayıcılar (Bölüm 2.1'den), öncelik devreleri (Bölüm 2.4'ten) ve yedi bölümlü ekran kod çözücüler (Bölüm 2.7'den). Bu bölüm daha yaygın olarak kullanılan iki yapı taşını tanıtır: çoklayıcılar ve kod çözücüler. Bölüm 5, diğer kombinasyonel yapı bloklarını kapsar.

## 2.8.1 Çoklayıcılar
Çoklayıcılar en yaygın kullanılan birleşik mantık devrelerindendir. Seçim sinyalinin değerine bağlı olarak birkaç olası giriş arasından bir çıkış seçerler. Bir çoklayıcıya bazen kısaca mux denir.

2:1 Çoklayıcı
Şekil 2.54, iki veri girişi D0 ve D1, bir seçim girişi S ve bir çıkış Y olan 2:1 çoklayıcı için şematik ve doğruluk tablosunu göstermektedir. Çoklayıcı, seçime göre iki veri girişi arasında seçim yapar: S = 0 ise, Y = D0 ve S = 1 ise Y = D1  S, çoklayıcının ne yaptığını kontrol ettiği için kontrol sinyali olarak da adlandırılır.

![şekil2.54](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-54.png)

Şekilde 2.55 gösterildiği gibi 2:1 çoklayıcı, çarpımların toplamı mantığından oluşturulabilir. Çoklayıcı için Boole denklemi bir Karnaugh haritası ile türetilebilir veya inceleme ile okunabilir (S=0 VE D0=1 ise Y=1'dir VEYA S=1 VE D1=1 Y=1 dir).

![şekil2.55](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-55.png)

Alternatif olarak, çoklayıcılar, Şekilde 2.56 gösterildiği gibi üç durumlu tamponlardan oluşturulabilir. Üç durumlu etkinleştirmeler, her zaman tam olarak bir üç durumlu tampon aktif olacak şekilde düzenlenmiştir. S = 0 olduğunda, üç durumlu T0 etkinleştirilir ve D0'ın Y'ye akmasına izin verilir. S = 1 olduğunda, üç durumlu T1 etkinleştirilir ve D1'in Y'ye akmasına izin verilir.

![şekil2.56](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-56.png)

Daha Geniş Çoklayıcılar
Şekil 2.57 gösterildiği gibi 4: 1 çoklayıcıda dört veri girişi ve bir çıkış vardır. Dört veri girişi arasından seçim yapmak için iki seçim sinyali gereklidir. 4: 1 çoklayıcı, Şekil 2.58 gösterildiği gibi, çarpımların toplamı mantığı, üç durumlu veya birden çok 2: 1 çoklayıcı kullanılarak oluşturulabilir.

![şekil2.57](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-57.png)

Üçdurumluları mümkün kılan çarpım terimleri, AND geçitleri ve invertörler kullanılarak oluşturulabilir. Ayrıca Bölüm 2.8.2'de tanıtacağımız bir kod çözücü kullanılarak da oluşturulabilirler. 

![şekil2.58](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-58.png)

8: 1 ve 16: 1 çoklayıcılar gibi daha geniş çoklayıcılar, Şekil 2.58 gösterilen yöntemler genişletilerek oluşturulabilir. Genel olarak, bir N: 1 çoklayıcı, log<sub>2</sub>N seçme hatlarına ihtiyaç duyar. Yine, en iyi uygulama seçimi, hedef teknolojiye bağlıdır.

Çoklayıcı Mantığı

Çoklayıcılar, mantık işlevlerini gerçekleştirmek için bakma tabloları olarak kullanılabilir. Şekil 2.59, iki girişli bir AND geçidi uygulamak için kullanılan 4: 1 çoklayıcıyı göstermektedir. Girişler, A ve B, seçme hatları olarak hizmet eder. Çoklayıcı veri girişleri, doğruluk tablosunun karşılık gelen satırına göre 0 veya 1'e bağlanır. Genel olarak, 2<sup>N</sup> girişli bir çoklayıcı, uygun veri girişlerine 0'lar ve 1'ler uygulayarak herhangi bir N girişli mantık işlevini gerçekleştirmek üzere programlanabilir. Aslında, veri girişlerini değiştirerek, çoklayıcı farklı bir işlevi gerçekleştirmek için yeniden programlanabilir.

![şekil2.59](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-59.png)

Biraz akıllıca, herhangi bir N girişli mantık işlevini gerçekleştirmek için yalnızca 2<sup>N–1</sup> girişli bir çoklayıcı kullanarak çoklayıcı boyutunu ikiye bölebiliriz. Strateji, çoklayıcı veri girişlerine 0 ve 1’lerin yanı sıra değişmez değerlerden birini sağlamaktır.

Bu prensibi göstermek için, Şekil 2.60 iki girişli VE ve 2: 1 çoklayıcı ile uygulanan XOR fonksiyonları. Sıradan bir doğruluk tablosu ile başlıyoruz ve sonra en sağdaki girdi değişkenini ortadan kaldırmak için çıktıyı bu değişken cinsinden ifade ederek satır çiftlerini birleştiriyoruz. Örneğin, VE durumunda, A = 0, Y = 0, B'den bağımsız olarak, A = 1 olduğunda, Y = 0, B = 0 ve Y = 1, B = 1 ise, Y = B. Çoklayıcıyı yeni, daha küçük doğruluk tablosuna göre bir arama tablosu olarak kullanın.

![şekil2.60](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-60.png)

Örnek 2.12 MULTIPLEKSER İLE MANTIK

Alyssa P. Hacker'ın kıdemli projesini bitirmek için Y = AB’+ B’C’ + A’BC işlevini uygulaması gerekiyor, ancak laboratuvar kitine baktığında kalan tek parçası 8: 1 çoklayıcı. İşlevi nasıl uyguluyor?

Çözüm: Şekil 2.61, Alyssa'nın tek bir 8: 1 çoklayıcı kullanan uygulamasını göstermektedir. Çoklayıcı, doğruluk tablosundaki her satırın bir çoklayıcı girişine karşılık geldiği bir arama tablosu görevi görür.

![şekil2.61](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-61.png)

Örnek 2.13 Alyssa, son sunumdan önce devresini bir kez daha açar ve 8: 1 çoklayıcıyı havaya uçurur. (Bütün gece uyumadıktan sonra yanlışlıkla 5 V yerine 20 V ile çalıştırdı.) Arkadaşlarına yedek parça için yalvarıyor ve ona 4: 1 çoklayıcı ve invertör veriyorlar. Devresini sadece bu parçalarla kurabilir mi?

Çözüm: Alyssa, çıktının C'ye bağlı olmasına izin vererek doğruluk tablosunu dört satıra indirgiyor (Çıktının A veya B'ye bağlı olmasına izin vermek için doğruluk tablosunun sütunlarını yeniden düzenlemeyi de seçebilirdi) Şekil 2.62 yeni tasarımı göstermektedir.

![şekil2.62](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-62.png)

## Decoder
Bir kod çözücünün N girişi ve 2<sup>N</sup> çıkışı vardır. Giriş kombinasyonuna bağlı olarak çıktılarından tam olarak birini belirtir. Şekil 2.63, 2: 4 kod çözücüyü göstermektedir. A<sub>1:0</sub> = 00 olduğunda, Y0 1'dir. A1:0 = 01 olduğunda, Y1 1'dir. Ve bu böyle devam eder. Çıkışlara tekli olarak adlandırılır çünkü belirli bir zamanda tam olarak biri "sıcak" (YÜKSEK) olur.

![şekil2.63](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-63.png)

Örnek 2.14  AND, OR ve NOT kapıları ile 2: 4 kod çözücü uygulayın.

Çözüm: Şekil 2.64, dört AND geçidi kullanan 2: 4 kod çözücünün uygulamasını göstermektedir. Her kapı, her girdinin gerçek veya tamamlayıcı şekline bağlıdır. Genel olarak, bir N: 2<sup>N</sup> kod çözücü, doğru veya tamamlayıcı girişlerin çeşitli kombinasyonlarını kabul eden 2<sup>N</sup> N-girişli AND geçitlerinden oluşturulabilir. Bir kod çözücüdeki her çıktı, tek bir mintermi temsil eder. Örneğin, Y0 minterm A1’A0’  ı temsil eder: Bu gerçek, diğer dijital yapı blokları ile kod çözücüler kullanırken kullanışlı olacaktır.

![şekil2.64](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-64.png)

# Zamanlama
Önceki bölümlerde, öncelikle devrenin çalışıp çalışmadığı ile ilgilenmiştik - ideal olarak, en az sayıda geçidi kullanarak. Bununla birlikte, herhangi bir tecrübeli devre tasarımcısının da onaylayacağı gibi, devre tasarımındaki en zorlu konulardan biri zamanlamadır: bir devrenin hızlı çalışmasını sağlamak.

Bir çıkışın, bir giriş değişikliğine yanıt olarak değişmesi zaman alır. Şekil 2.66, bir tampon için bir giriş değişikliği ile sonraki çıkış değişikliği arasındaki gecikmeyi göstermektedir. Şekle zamanlama diyagramı denir; bir giriş değiştiğinde tampon devresinin geçici yanıtını gösterir. DÜŞÜK'ten YÜKSEK'e geçiş yükselen kenar olarak adlandırılır. Benzer şekilde, HIGH'dan LOW'a geçiş (şekilde gösterilmemiştir) düşen kenar olarak adlandırılır. Mavi ok, Y'nin yükselen kenarının A'nın yükselen kenarından kaynaklandığını gösterir.Giriş sinyalinin% 50 noktası olan A'dan çıkış sinyalinin% 50 noktası Y'ye kadar olan gecikmeyi ölçüyoruz.% 50 noktası sinyalin geçiş sırasında LOW ve HIGH değerleri arasında yarı yolda (% 50) olduğu noktadır.

![şekil2.66](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-66.png)

## 2.9.1 Yayılma ve Kirlenme Gecikmesi
Kombinasyonel mantık, yayılma gecikmesi ve kirlenme gecikmesi ile karakterize edilir. Yayılma gecikmesi tpd, bir girişin değişmesinden çıkış veya çıkışların nihai değerlerine ulaşmasına kadar geçen maksimum süredir. Kirlenme gecikmesi tcd, bir girişin değiştiği andan herhangi bir çıkışın değerini değiştirmeye başladığı ana kadar geçen minimum süredir.

Şekil 2.67, sırasıyla mavi ve gri olarak bir tamponun yayılma gecikmesini ve kirlenme gecikmesini göstermektedir. Şekil, A'nın başlangıçta YÜKSEK veya DÜŞÜK olduğunu ve belirli bir zamanda diğer duruma değiştiğini gösterir; biz sadece değiştiği gerçeğiyle ilgileniyoruz, sahip olduğu değere değil. Yanıt olarak, Y bir süre sonra değişir. Yaylar, Y'nin, A geçişlerinden sonra tcd'yi değiştirmeye başlayabileceğini ve Y'nin kesinlikle tpd içinde yeni değerine yerleştiğini gösterir.

![şekil2.67](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-67.png)

Devrelerdeki gecikmenin altında yatan nedenler, bir devrede kapasitansı şarj etmek için gereken süre ve ışık hızını içerir. tpd ve tcd birçok nedenden dolayı farklı olabilir.
- farklı yükselme ve düşme gecikmeleri
- bazıları diğerlerinden daha hızlı olan birden fazla giriş ve çıkış
- sıcakken yavaşlayan ve soğukken hızlanan devreler

tpd ve tcd'yi hesaplamak, bu kitabın kapsamının ötesinde soyutlamanın daha düşük seviyelerine inmeyi gerektirir. Bununla birlikte, üreticiler normalde her kapı için bu gecikmeleri belirten veri sayfaları sağlar.

Halihazırda listelenen faktörlerin yanı sıra, yayılma ve kirlenme gecikmeleri de bir sinyalin girişten çıkışa geçtiği yol tarafından belirlenir. Şekil 2.68, dört girişli bir mantık devresini göstermektedir. Mavi ile gösterilen kritik yol, A veya B girişinden Y çıkışına giden yoldur. Bu, en uzun ve bu nedenle en yavaş yoldur, çünkü giriş üç kapıdan çıkışa doğru ilerler. Bu yol kritiktir çünkü devrenin çalıştığı hızı sınırlar. Gri ile gösterilen devre boyunca kısa yol, D girişinden Y çıkışına kadardır. Bu, devre boyunca en kısa ve dolayısıyla en hızlı yoldur, çünkü giriş, çıkışa yalnızca tek bir kapıdan geçer.

![şekil2.68](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-68.png)

Bir birleşimsel devrenin yayılma gecikmesi, kritik yoldaki her bir elemandan geçen yayılma gecikmelerinin toplamıdır. Kirlenme gecikmesi, kısa yoldaki her bir elemanın kirlenme gecikmelerinin toplamıdır. Bu gecikmeler Şekil 2.69 gösterilmiş ve aşağıdaki denklemlerle açıklanmıştır:

![şekil2.69](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-69.png)

t<sub>pd</sub> = 2t<sub>pd_AND</sub> + t<sub>pd_OR</sub>
t<sub>cd</sub> = t<sub>cd_AND</sub>

Örnek 2.15 Ben Bitdiddle'ın, Şekil 2.70 gösterilen devrenin yayılma gecikmesini ve kirlenme gecikmesini bulması gerekir. Veri kitabına göre, her kapının yayılma gecikmesi 100 pikosaniye (ps) ve kirlenme gecikmesi 60 ps'dir.

![şekil2.70](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-70.png)

Çözüm: Ben, kritik yolu ve devre boyunca en kısa yolu bularak başlar. Şekil 2.71 mavi ile vurgulanan kritik yol, A veya B girişinden üç kapıdan Y çıkışına doğrudur. Dolayısıyla, tpd, tek bir geçidin yayılma gecikmesinin üç katı veya 300 ps'dir. 

Şekil 2.72 gri olarak gösterilen en kısa yol, C, D veya E girişinden iki kapıdan Y çıkışına kadardır. En kısa yolda yalnızca iki kapı vardır, bu nedenle tcd 120 ps'dir.

Örnek 2.16 Bölüm 2.8.1'deki Şekil 2.58 gösterilen üç dört girişli çoklayıcı tasarımının en kötü durum zamanlamasını karşılaştırın. Tablo 2.7 , bileşenler için yayılma gecikmelerini listeler. Her tasarım için kritik yol nedir? Zamanlama analizinize göre, neden bir tasarımı diğerine tercih edebilirsiniz?

![şekil2.58](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-58.png)

![şekil2.T7](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2-T7.png)

Çözüm: Üç tasarım seçeneğinin her biri için kritik yollardan biri Şekil 2.73 ve 2.74 mavi ile vurgulanmıştır. tpd_sy, S girişinden Y çıkışına yayılma gecikmesini belirtir; tpd_dy, D girişinden Y çıkışına yayılma gecikmesini belirtir; tpd, ikisinin en kötüsüdür: max (tpd_sy, tpd_dy).

Şekil 2.73 hem iki seviyeli mantık hem de üç durumlu uygulamalar için kritik yol, kontrol sinyallerinden S birinden Y çıkışına kadardır: tpd = tpd_sy. Bu devreler kontrol açısından kritiktir, çünkü kritik yol kontrol sinyallerinden çıkışa kadardır. Kontrol sinyallerindeki herhangi bir ek gecikme, doğrudan en kötü durum gecikmesine eklenecektir. Şekil 2.73(b) D'den Y'ye gecikme, 125 ps'lik S'den Y'ye gecikme ile karşılaştırıldığında sadece 50 ps'dir.

Şekil 2.74, 2: 1 çoklayıcıların iki aşamasını kullanan 4: 1 çoklayıcının hiyerarşik uygulamasını göstermektedir. Kritik yol, herhangi bir D girişinden çıktıya kadardır. Bu devre veri açısından kritiktir çünkü kritik yol veri girişinden çıkışa kadardır:  tpd = tpd_dy.

Veri girişleri kontrol girişlerinden çok önce gelirse, en kısa kontrolden çıkışa gecikmeli tasarımı tercih ederiz (şekil 2.74). Benzer şekilde, kontrol girişleri veri girişlerinden çok önce gelirse, veriden çıkışa en kısa gecikmeli tasarımı tercih ederiz (Şekil 2.73(b)).

En iyi seçim, yalnızca devredeki kritik yola ve giriş varış sürelerine değil, aynı zamanda parçaların gücüne, maliyetine ve kullanılabilirliğine de bağlıdır.

## Glitches (Tek girisin çoklu çıkısı tetiklemesi)
Şimdiye kadar, tek bir giriş geçişinin tek bir çıktı geçişine neden olduğu durumu tartıştık. Ancak, tek bir giriş geçişinin birden çok çıkış geçişine neden olması mümkündür. Bunlara aksaklıklar veya tehlikeler denir. Aksaklıklar genellikle sorun yaratmasa da, bunların var olduğunu anlamak ve zamanlama diyagramlarına bakarken onları tanımak önemlidir. Şekil 2.75 arızalı bir devreyi ve devrenin Karnaugh haritasını göstermektedir.

Boole denklemi doğru şekilde küçültülmüştür, ancak A = 0, C = 1 ve B 1'den 0'a geçiş yaptığında ne olduğuna bakalım. Şekil 2.76 bu senaryoyu göstermektedir. Kısa yol (gri olarak gösterilmiştir) iki kapıdan, AND ve OR kapılarından geçer. Kritik yol (mavi ile gösterilmiştir) bir terrsleyici ve iki kapıdan, AND ve OR kapılarından geçer.

B 1'den 0'a geçerken, n2 (kısa yolda), n1'in (kritik yolda) yükselmesinden önce düşer. n1 yükselene kadar, OR geçidinin iki girişi 0'dır ve Y çıkışı 0'a düşer. n1 sonunda yükseldiğinde, Y 1'e döner. Şekil 2.76 zamanlama diyagramında gösterildiği gibi, Y 1'de başlar ve 1'de biter ancak anlık olarak 0'a geçer.

Çıktıya bağlı kalmadan önce yayılma gecikmesinin geçmesini beklediğimiz sürece, hatalar bir sorun değildir, çünkü çıktı sonunda doğru cevaba yerleşir.

İstersek, uygulamaya başka bir kapı ekleyerek bu aksaklıktan kaçınabiliriz. Bu, K-haritası açısından anlaşılması en kolay yoldur. Şekil 2.77, B üzerindeki ABC = 001'den ABC = 011'e bir giriş geçişinin bir asal dolaylı çemberden diğerine nasıl hareket ettiğini gösterir. K-haritasındaki iki temel etkenin sınırını aşan geçiş, olası bir aksaklığı gösterir.

Şekil 2.76 önceki'daki zamanlama diyagramından da gördüğümüz gibi, birincil implikantlardan birini uygulayan devre, diğer birincil implikantın devresi açılmadan önce kapanırsa, bir aksaklık vardır. Bunu düzeltmek için, Şekil 2.78 gösterildiği gibi, bu birincil dolaylı sınırı kapsayan başka bir daire ekliyoruz. Bunu, eklenen terim olan AC'nin fikir birliği veya gereksiz terim olduğu konsensüs teoremi olarak tanıyabilirsiniz.

Şekil 2.79, aksaklığa dayanıklı devreyi göstermektedir. Eklenen AND kapısı mavi ile vurgulanır. Şimdi, A = 0 ve C = 1 olduğunda B üzerindeki bir geçiş, çıkışta bir hataya neden olmaz, çünkü mavi AND geçidi, geçiş boyunca 1 çıktısı verir.

Genel olarak, tek bir değişkendeki bir değişiklik bir K-haritasındaki iki asal çarpım arasındaki sınırı geçtiğinde bir aksaklık meydana gelebilir. Bu sınırları kapatmak için K-haritasına fazlalık çıkarımlar ekleyerek aksaklığı ortadan kaldırabiliriz. Bu, elbette ekstra donanım maliyetiyle gelir.

Bununla birlikte, çoklu girişlerdeki eşzamanlı geçişler de hatalara neden olabilir. Bu aksaklıklar, donanım eklenerek düzeltilemez. İlginç sistemlerin büyük çoğunluğunun çoklu girişler üzerinde eşzamanlı (veya neredeyse eşzamanlı) geçişlere sahip olması nedeniyle, hatalar çoğu devrede hayatın bir gerçeğidir. Bir tür aksaklığı nasıl ortadan kaldıracağımızı göstermiş olsak da, aksaklıkları tartışmanın amacı onları ortadan kaldırmak değil, var olduklarının farkında olmaktır. Bu, özellikle bir simülatör veya osiloskop üzerindeki zamanlama diyagramlarına bakarken önemlidir.



