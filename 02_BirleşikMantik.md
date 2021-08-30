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

Bir veya daha fazla değişmezin AND'sine ürün veya implikant denir. A’B, AB’C’ ve B, üç değişkenli bir fonksiyonun tüm sonuçlarıdır. Bir minterm, işlevin tüm girdilerini içeren bir üründür. A’B’C’, A, B ve C üç değişkeninin bir fonksiyonu için bir mintermdir, ancak AB’, C'yi içermediği için değildir. Benzer şekilde, bir veya daha fazla değişmezin VEYA'sına toplam denir. Bir maxterm, fonksiyonun tüm girdilerini içeren bir toplamdır. A + B’ + C, A, B ve C olmak üzere üç değişkenli bir fonksiyon için bir maxtermdir.

Boole denklemlerini yorumlarken işlem sırası önemlidir. Y = A + BC, Y = (A OR B) VE C veya Y = A OR (B AND C) anlamına mı geliyor? Boole denklemlerinde, NOT en yüksek önceliğe sahiptir, ardından AND ve ardından OR gelir. Tıpkı sıradan denklemlerde olduğu gibi, ürünler toplamlardan önce gerçekleştirilir. Bu nedenle denklem Y = A OR (B AND C) olarak okunur.

Denklem 2.1, işlemlerin sırasına ilişkin başka bir örnek verir.

A’B + BCD’ = ((A’)B) + ((BC)D’))



## KaTeX

You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/):

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> You can find more information about **LaTeX** mathematical expressions [here](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).



