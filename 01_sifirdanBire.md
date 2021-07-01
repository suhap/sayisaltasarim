
# 1.1 Mikroişlemci Gelişiminin Önemi
Son 30 yılda büyük gelişim gösteren mikroişlemci teknolojisi sayesinde günümüzde kulllanılan bir dizüstü bilgisayarları, geçmişteki oda büyüklüğündeki sunuculardan daha yetenekli hale geldiler. Mikroişlemcilerdeki bu inanılmaz ilerlemeler sayesinde cep telefonlarını ve interneti hayatımızdaki yerini aldı. Ayrıca tıp alanında mevcut cihazlar evrim geçirirken yeni ve bir çok cihaz bu alanda hizmet vermeye başlamıştır. Mikro işlemcilerin gelişimi savunma sanayinde yeni silah sistemlerinin ortaya çıkmasını ve mevcut sistemlerin daha efektif kullanılmasını sağlayarak orduların savaşma şeklini değiştirmiştir. Mikroişlemci satışlarının önemli bir bölümünü oluşturduğu, dünya çapındaki yarı iletken satışları 1985'te 21 milyar ABD dolarından 2011'de 300 milyar dolara yükselmiştir. Mikroişlemcilerin yalnızca teknik, ekonomik ve sosyal olarak önemli olmadığına, aynı zamanda doğası gereği büyüleyici bir insan icadı olduğuna inanıyoruz. Bu kitabı okumayı bitirdiğinizde, kendi mikroişlemcinizi nasıl tasarlayıp oluşturacağınızı öğreneceksiniz. Yol boyunca öğrendiğiniz beceriler, sizi diğer birçok dijital sistemi tasarlamaya hazırlayacaktır.
Bu derse başlamadan önce elektrik bilginizin, programlama deneyiminizin ve bilgisayar konusunda temel bilginizin olması gerekmektedir. Bu ders boyunca 1'ler ve 0'lar üzerinde çalışan dijital sistemlerin tasarımına odaklanmaktadır. Bu sistemlerin tasarımı için 1'leri ve 0'ları girdi olarak kabul eden ve çıktı olarak 1'ler ve 0'ları üreten dijital mantık kapıları incelenecektir. Ardından mantık kapıları kullanılarak toplayıcılar ve bellekler gibi daha karmaşık modüllerinin nasıl oluşturulacağını inceleyeceğiz. Ardından, mikroişlemcinin ana dili olan Assembly ile nasıl program yazacağımızı incelecektir. Son olarak, Assembly dili ile yazılmış programları çalıştıran bir mikroişlemcinin kapılar kullanılarak nasıl inşa edileceği incelenecektir.
Dijital sistemlerin büyük bir avantajı, yapı taşlarının oldukça basit olmasıdır: sadece 1'ler ve 0'lar. Matematik veya fizik bilgisi gerektirmezler. Bunun yerine, tasarımcının görevi bu basit blokları birleştirerek karmaşık sistemlerde inşaa etmektir. Bir mikroişlemci, tek seferde anlaşılmayacak kadar karmaşık olan, oluşturduğunuz ilk sistem olacaktır. Bu kitap boyunca dokunan ana temalardan biri karmaşıklığın nasıl yönetileceğidir.

# 1.2 Karmasıklık Yönetimi
Bir mühendisi veya bilim adamını sıradan bir kişiden ayıran en önemli özelliklerden biri, karmaşıklığı  nasıl yönetileceğine dair sistematik bir yaklaşım geliştirebilmesidir. Modern dijital sistemler, milyonlarca veya milyarlarca transistörden yapılmıştır. Hiçbir insan, her transistördeki elektronların hareketini tanımlayan denklemler yazarak ve tüm denklemleri aynı anda çözerek bu sistemleri anlayamaz. Bir mikroişlemcinin nasıl oluşturulacağını anlamak için karmaşıklığı yönetiminin öğrenilmesi gerekmektedir.

# 1.2.1 Soyutlama
Karmaşıklığı yönetmenin en temel tekniği soyutlamadır: önemsiz ayrıntıları gizlemek. Bir sistem birçok farklı soyutlama seviyesinde incelenebilir. Örneğin, Amerikalı politikacılar dünyayı şehirler, bölgeler, eyaletler ve ülkeler olarak soyutlar. Bir bölge birden fazla şehir ve bir eyalet birçok bölge içerebilir. Bir politikacı cumhurbaşkanlığı için yarışırken, her bir bölgenin nasıl oy kullandığından ziyade çoğunlukla devletin bir bütün olarak nasıl oy kullanacağıyla ilgilenir, bu nedenle devlet en kullanışlı soyutlama düzeyidir. Öte yandan, seçim bürosu her şehrin nüfusunu ölçer, bu nedenle daha düşük bir soyutlama düzeyinin ayrıntılarını dikkate almalıdır.

![soyutlamaTablosu](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/1.png)

Yukarıdaki şekil bir bilgisayar sistemi için soyutlama sevyelerini göstermektedir. En düşük soyutlama sevyesi elektronların hareketlerinin tanımlandığı fiziktir. Elektronların davranışı kuantum mekaniği ve Maxwell denklemleri ile tanımlanabilir. Derste üzerinde duracağımız sayısal sistemlerin yapı taşları transistör (bir zamanlar vakum tüpleri) adı verilen elektronik cihazlardır. Bu cihazlar, terminal adı verilen iyi tanımlanmış bağlantı noktalarına sahiptir ve terminalde ölçülen gerilim ve akım arasındaki ilişki kullanılarak matematiksel olarak modellenebilir. Soyutlama kavramı sayesinde, bir cihazın içindeki elektron davranışını görmezden gelinebilir, böylece sisteme cihaz sevyesinden bakabilme fırsatı yakalanabilir. Bir üst soyutlama sevyesi(analog devre soyutlaması) transistör gibi elektronik devrelerin bir araya gelerek analog devre elemanlarını(ükselteç-amplifiers-) oluşturulmasını tanımlar. Analog devre elemanları  kesintisiz akım/voltaj giriş ve çıkışına sahiptir. Sayısal devreler ise 0 ve 1 gibi ayrık voltaj seviyelerine sahiptir. Lojik tasarımda sayısal devre elemanları kullanarak toplayıcı ve hazıfa gibi daha karmaşık devreler inşa edilcektir.

Mikromimari(Microarchitecture), lojik cihazların kullanıldığı devre mimarisini tanımlamaktadır. Bu soyutlama düzeyi bir yazılımcının gözünden bilgisayar mimarisini tasarlamaktadır. Örneğin, kişisel bilgisayarda (PC) kullanılan Intel x86 mimarisi, programcıların kullandığı komutlar ve saklayıcıları (değişkenleri geçici olarak depolamak için bellek) tanımlamaktadır. Mikromimarisi ise mimari tarafından tanımlanan bu komutları çalıştırabilmek için gerekli lojik devre mimarisidir. Belirli bir mimari, farklı fiyat/performans/güç  kriterlerine sahip farklı mikromimariden biri tarafından gerçekleştirilir. Örneğin x86 mimarisi, Intel Core i7, Intel 80486 ve AMD Athlon gibi farklı mikromimarilerden biri kullanılarak gerçekleştirilebilir.














