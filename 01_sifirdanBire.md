
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

Mimarinin bir üst seviyesi olan İşletim Sistemi, sabit bir sürücüye erişim veya bellek yönetimi gibi düşük düzeyli ayrıntıları ele almaktadır. Son olarak Uygulama katmanı, kullanıcının ihtiyaç duyduğu programları işletim sistemi marifeti ile sunmaktadır. Soyutlama sayesinde annelerimiz kuantum fizik bilgisi veya bilgisayar organizasyon bilgisine ihtiyaç duymadan internette gezinebilmektedir.

Bu ders bilgisayar mimarisinin oluşturan sayısal devre soyutlama sevyesine odaklanacaktır. Bir soyutlama düzeyinde çalışırken, çalıştığınız yerin hemen üstündeki ve altındaki soyutlama düzeyleri hakkında bir şeyler bilmek iyidir. Örneğin bir bilgisayar mühendisi yazdığı programın çalışacağı mimariyi anlamadan optimize kod yazması mümkün değildir. 

# 1.2.2 Disiplin

Yüksek soyutlama sevyelerinden efektif çalışmak için tasarım seçimlerinin biliçli olarak kısıtlamaktır. Değiştirilebilir parçaların kullanılması, bilinen bir disiplin uygulamasıdır. Değiştirilebilir parçaların ilk örneklerinden biri çakmaklı tüfek imalatıdır. 19. yüzyılın başlarına kadar tüfekler tek tek elle yapılmaktaydı. Birçok farklı ustadan satın alınan parçalar, yetenekli bir silah ustası tarafından dikkatlice bir araya getirilmektedi. Değiştirilebilir parçaların kullanımı endüstride devrim yarattı. Tüfek parçalarının iyi tanımlanmış standartlarla sınırlandırılması sayesinde tüfekler çok daha hızlı ve daha az beceriyle monte edilebilir ve onarılabilir oldular. Bu sayede silah ustaları tek bir namlu veya dipçiğin şekil ile ilgilenmek gibi daha düşük soyutlama sevyeleri ile ilgilenmez oldular. 

# 1.2.3 Karmasıklıgın için Üc Y

Soyutlama ve disipline ek olarak, tasarımcılar karmaşıklığı yönetmek için üç "-y(hierarchy, modularity, regularity)"yi kullanır: hiyerarşi, modülerlik ve düzenlilik. Bu ilkeler hem yazılım hem de donanım sistemleri için geçerlidir.

- Hiyerarşi, bir sistemi parçalara bölmeyi ve ardından bu parçalarn her birini kolay anlaşılır hale gelene kadar alt parçalara ayırmayı içerir.
- Modülarite, modüllerin iyi tanımlanmış fonksiyonlara ve arayüzlere sahip olduğunu ve böylece beklenmedik bir etki olmadan kolayca birbirine iletişim kurmalarını garanti eder.
- Düzenlilik, modüller arasında tekdüzelik arar. Ortak modüller birçok kez yeniden kullanılır, bu da tasarlanması gereken farklı modüllerin sayısını azaltır.

![cakmakliTufek](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/2.png)

Üç "-y" kavramını göstermek için tüfek imalatı örneğine dönülecektir. 19. yüzyılın başlarında yaygın olarak kullanılan en karmaşık nesnelerden biri olan çakmaklı tüfek, hiyerarşi ilkesi kullanılarak şekilde gösterilen tetik, dipçik ve namlu şeklinde üç parçaya ayrılabilir. 

Namlu, içinden merminin ateşlendiği uzun metal borudur. Kilit, ateşleme mekanizmasıdır. Dipçik ise parçaları bir arada tutan ve kullanıcıya güvenli bir tutuş sağlayan ahşap gövdedir. Kilit mekanizması, tetik, horoz, çakmaktaşı, çakmak taşını tutan parça, çakmak taşının vurduğu ve bir miktar barut bulunduran çelik zemin; tava. Bu bileşenlerin her biri daha ayrıntılı olarak hiyerarşik olarak açıklanabilir.

Modülerlik kavramında her bileşen iyi tanımlanmış bir işleve ve arayüze sahip olması gerekmektedir. Dipçiğin görevi kilit mekanizmasını ve namluyu birleştirmektir. Dipçiğin diğer parçalarla ilişkisi arayüzü montaj pimlerinden ve konumlanmasından oluşmaktadır. Dolayısıyla, modüler bir tüfek tasarımında, dipçik ve namlu doğru uzunlukta olduğu ve uygun montaj mekanizmasına sahip olduğu sürece, birçok farklı üreticinin tüfek parçaları bir arada kullanılarak tüfek montajı yapılabilir. Modülerlik, paçaların birbilerinin işlevlerini engellemelerini önlemeyi garanti etmektedir: dipçiğin tasarımı namlunun mermiye dönüş verme işlevini etkilememesi gerekmektedir. 

Düzenlilik, değiştirilebilir parçaların iyi bir fikir olduğunu öğretir. Hasarlanan herhangi bir parça diğeri ile kolayca değiştirilebilmelidir. Bu sayede parçalar el yapımı olmak yerine montaj hattında üretilebilir olmaktadır. 

# 1.3 Sayısal Soyutlama
Çoğu fiziksel değişken süreklidir. Örneğin, bir tel üzerindeki voltaj, bir salınımın frekansı veya bir kütlenin konumu sürekli niceliklerdir. Öte yandan dijital sistemlerde bilgi, ayrık değerli değişkenlerle, yani sonlu sayıda farklı değere sahip değişkenlerle temsil edilir.

![Babbage Analitik Motor](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/3.png)

İlk sayısal sistem olan Charles Babbage'ın Analitik Motoru on ayrık değere sahip olabilen değişkenleri  kullanmaktaydı. Babbage, 1834'ten 1871'e kadar bu mekanik bilgisayarı tasarlamak ve inşa etmek için çalıştı. Analitik Motor, bir arabadaki mekanik kilometre sayacına çok benzer şekilde, on konumlu (0 ila 9) vites kutusuna bezer şekilde çalışmaktadır. Yukarıdaki şekilde, her satırda bir rakamın işlendiği Analitik Motorun bir prototipini göstermektedir. Babbage 25 sıra dişli seçti, bu nedenle makine 25 basamaklı hassasiyete sahiptir.

Babbage'ın makinesinden farklı olarak, çoğu elektronik bilgisayar, yüksek voltajın '1' ve düşük voltajın '0'ı gösterdiği ikili (iki değerli) bir gösterim kullanır, çünkü iki değerli alan voltajı on deger alan voltajdan ayır etmek daha kolaydır.

N farklı duruma sahip ayrık değerli bir değişkendeki bilgi(D) miktarı, şu şekilde ölçülür:

D= log<sub>2</sub> N bits

İkili değişken, log<sub>2</sub> 2 = 1 bit bilgi taşır. Aslında, bit kelimesi ikili rakamın kısaltmasıdır. Babbage’ın dişlilerinden her biri log<sub>2</sub> 10 = 3.322 bit bilgi taşıyordu çünkü bu 2<sup>3.322</sup> = 10 benzersiz konumdan birinde olabilirdi. Sürekli bir sinyal teorik olarak sonsuz miktarda bilgi içerir çünkü sonsuz sayıda değer alabilir. Uygulamada gürültü ve ölçüm hatası, çoğu sürekli sinyal için bilgiyi yalnızca 10 ila 16 bit ile sınırlar. Ölçümün hızlı bir şekilde yapılması gerekiyorsa, bilgi içeriği daha düşüktür (örneğin, 8 bit).

Bu derste, ikili değişkenleri kullanan sayısal devrelere odaklanmaktadır: 1'ler ve 0'lar. George Boole, artık Boole mantığı olarak bilinen ikili değişkenler üzerinde çalışan bir mantık sistemi geliştirdi. Boole değişkenlerinin her biri DOĞRU veya YANLIŞ olabilir. Elektronik bilgisayarlar genellikle '1'i temsil etmek için pozitif voltaj ve' 0'ı temsil etmek için sıfır volt kullanır. Bu kitapta '1', DOĞRU ve YÜKSEK terimlerini eşanlamlı olarak kullanılırken; benzer şekilde, '0', YANLIŞ ve DÜŞÜK'ü birbirinin yerine kullanılacaktır.

Sayısal soyutlamanın güzelliği, sayısal tasarımcıların Boole değişkenlerinin fiziksel olarak belirli voltajlarla, dönen dişlilerle ve hatta hidrolik sıvı seviyeleriyle temsil edilip edilmediğini görmezden gelerek 1’lere ve 0’lara odaklanabilmesidir. Bir bilgisayar programcısı, bilgisayar donanımının özel ayrıntılarını bilmesine gerek kalmadan çalışabilir. Öte yandan, donanımın ayrıntılarını anlamak, programcının yazılımı o belirli bilgisayar için daha iyi optimize etmesini sağlar.

Tek bir bit fazla bilgi taşımaz. Bir sonraki bölümde, bit gruplarının sayıları temsil etmek için nasıl kullanılabileceğini incelenecektir. Daha sonraki bölümlerde, harfleri ve programları temsil etmek için bit grupları da kullanılacaktır.

# 1.4 Sayı Sistemleri
Alışkın olunana ondalık sayı sistemlerinin aksine; 1’lerden ve 0’lardan oluşan sayısal sistemlerde, ikili veya onaltılı sayılar genellikle daha uygundur. 

# 1.4.1 Ondalık Sayı Sistemleri
İlkokulda, sayma ve matematiksel işlemlerin ondalık olarak yapmak öğretilmektedir. Muhtemelen on parmağınız olduğu gibi, on ondalık basamak vardır: 0, 1, 2, ..., 9. Ondalık basamaklar, daha uzun ondalık sayılar oluşturmak için birleştirilir. Ondalık sayının her sütunu, önceki sütunun on katı ağırlığa sahiptir. Sağdan sola, sütun ağırlıkları 1, 10, 100, 1000 vb. Şeklindedir. Ondalık sayılar, taban 10 olarak adlandırılır. Birden fazla tabda çalışılırsa karışıklığı önlemek için çalışılan taban sayıdan sonra bir alt simge ile gösterilir. Aşağıdaki şekil 9742 <sub>10</sub> ondalık sayısının nasıl her bir basamağının toplamı olarak karşılık gelen sütunun ağırlığıyla çarpılarak yazıldığını göstermektedir.

![OndalıkGosterim](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/4.png)

N basamaklı bir ondalık sayı, 10 <sup>N</sup> olasılıktan birini temsil eder: 0, 1, 2, 3, ..., 10 <sup>N</sup> - 1. Buna sayı aralığı denir. Örneğin, üç basamaklı bir ondalık sayı, 0 ila 999 aralığındaki 1000 olasılıktan birini temsil eder.

# 1.4.2 İkilik Sayı Sistemleri

Bitler, 0 veya 1 gibi iki değerden birini temsil eder ve ikili sayılar oluşturmak üzere birleştirilir. İkili sayının her sütunu, önceki sütunun iki katı ağırlığa sahiptir, bu nedenle ikili sayılar taban 2'dir. İkili olarak, sütun ağırlıkları (yine sağdan sola) 1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048, 4096, 8192, 16384, 32768 vb.

N-bit ikili sayı 2 <sup>N</sup> olasılıktan birini temsil eder: 0, 1, 2, 3, …, 2 <sup>N</sup> − 1. Aşağıdaki Tablo, 1, 2, 3 ve 4-bit ikili sayıları ve ondalık eşdeğerlerini göstermektedir.

![ikiliktaban](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/5.png)

ÖRNEK 1.1 İkilik tabandaki 10110 <sub>2</sub> sayısını onluk tabana ceviriniz.

![cevrim](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/6.png)

ÖRNEK 1.2 Onluk tabandaki 84 <sub>10</sub> sayısını ikilik tabana ceviriniz.

Soldan başlayarak, sayıya eşit veya küçük 2'nin en büyük kuvvetiyle başlanır (bu durumda, 64). 84 ≥ 64, yani 64'ün sütununda 1 var ve 84 − 64 = 20 kalır. 20 < 32, yani 32'ler sütununda 0 var. 20 ≥ 16, yani 16'nın sütununda 1 var ve geriye 20 − 16 = 4 kalır. 4 < 8, yani 8'ler sütununda 0 var. 4 ≥ 4, yani 4'ün sütununda 1 var ve 4− 4 = 0 kalır. Bu nedenle 2'ler ve 1'ler sütununda 0'lar olmalıdır. Bunların hepsini bir araya getirirsek, 84 <sub>10</sub> = 1010100 <sub>2</sub>.

Sağdan çalışarak sayıyı art arda 2'ye bölün. Geri kalan her sütuna gider. 84/2 = 42, yani 0, 1'in sütununa girer. 42/2 = 21, yani 0, 2'nin sütununa girer. 21/2 = 10, kalan 1 ise 4'ün sütununda. 10/2 = 5, yani 0, 8'ler sütununa girer. 5/2 = 2, kalan 1 16'lar sütununda olur. 2/2 = 1, yani 0, 32'ler sütununa girer. Son olarak, 64'ün sütununda 1'in kalan kısmı ile 1/2 = 0. Sonuç: 84 <sub>10</sub> = 1010100 <sub>2</sub>.

# 1.4.3 Onaltılık Sayı Sistemleri
Uzun ikili sayılarla çalışmak hata yapma olasılığını artırmaktadır. Dolayısıyla ikilik tabandaki sayıları dört bitlik gruplara ayrabiliriz. Dört bitlik bir grup 2 <sub>4</sub> = 16 olasılıktan birini temsil eder. İkilik tabandaki sayıların 4 bitlik gösterimine onaltılık olarak adlandırılan 16 taban denilmektedir ve bu tabanda çalışmak daha kolaydır.  Onaltılık sayılar, aşağıdali tabloda gösterildiği gibi, A'dan F'ye harflerle birlikte 0'dan 9'a kadar olan rakamları kullanır. 16 tabanındaki sütunlar 1, 16, 16 <sup>2</sup> (veya 256), 16 <sup>3</sup> (veya 4096) vb. ağırlıklara sahiptir.

![OnaltilikSistem](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/7.PNG)

Örnek 1.3 2ED <sub>16</sub>'yı ikiliye ve ondalık sayıya dönüştürün.

Çözüm: Onaltılık ve ikili arasında dönüşüm kolaydır çünkü her bir onaltılık basamak doğrudan dört ikili basamağa karşılık gelir.

2 <sub>16</sub> = 0010 <sub>2</sub>, E <sub>16</sub> = 1110 <sub>2</sub> ve D <sub>16</sub> = 1101 <sub>2</sub>, yani 2ED <sub>16</sub> = 001011101101 <sub>2</sub>.

Onluk sayıya dönüştürme, aşağıdaki şekilde gösterilen aritmetiği gerektirmektedir.

![Onlukcevrim](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/8.PNG)

Örnek 1.4 1111010 <sub>2</sub> ikili sayısını onaltılık sayıya dönüştürün.
Çözüm: Yine, dönüştürme kolaydır. Sağdan okumaya başlayın. En az anlamlı dört bit 1010 <sub>2</sub> = A <sub>16</sub>'dır. Sonraki bitler 111 <sub>2</sub> = 7 <sub>16</sub>'dır.

Dolayısıyla 1111010 <sub>2</sub> = 7A <sub>16</sub>

Örnek 1.5 333 <sub>10</sub> sayısını onaltılık ve ikili sayıya dönüştürün.

Çözüm: Ondalıktan ikiliye dönüştürme gibi, ondalıktan onaltılığa dönüştürme de soldan veya sağdan yapılabilir.

Soldan başlayarak, sayıya eşit veya ondan küçük 16'nın en büyük gücüyle başlayın (bu durumda, 256).

256, 333'e bir tane var, yani 256'nın sütununda 1 vardır ve geriye 333 − 256 = 77 kalır. 16, 77'ye tane var, yani 16'lar sütununda 4 olur ve geriye 77 − 16 × 4 = 13 kalır 13 <sub>10</sub> = D <sub>16</sub>, yani 1'in sütununda bir D var. 333 <sub>10</sub> = 14D <sub>16</sub>. Örnek 1.3'te olduğu gibi onaltılıdan ikiliye dönüştürmek kolaydır. 14D <sub>16</sub> = 101001101 <sub>2</sub>. 

Sağdan çalışarak, sayıyı art arda 16'ya bölün. Kalan her sütuna gider. 333/16 = 20, kalan 13 <sub>10</sub> = D <sub>16</sub> 1 sütununa giriyor. 20/16 = 1, kalan 4 ise 16'lar sütununa giriyor. 1/16 = 0, geriye kalan 1 256'lar sütununa giriyor. Sonuç yine 14D <sub>16</sub>.

# 1.4.4 Byte, Nibble
 2 <sup>8</sup> = 256 olasılıktan birini temsil eden sekiz tane bite bayt denir. eder. Bilgisayar belleklerinde depolanan nesnelerin boyutu, alışılmış olarak bit yerine bayt olarak ifade edilmektedir. 
 
Dört bitlik veya yarım baytlık bir gruba nibble denir. 2 <sup>4</sup> = 16 olasılıktan birini temsil eder. Onaltılık tabanda bir basamak yarım bayt depolar ve iki basamak ise bir bayt depolar. Sevimli olmasına rağmen Nibble kavramı artık yaygın olarak kullanılan bir birim değildir.

Mikroişlemciler, verileri kelime adı verilen parçalar halinde işler. Bir kelimenin boyutu, mikroişlemcinin mimarisine bağlıdır. 2012 yılında, çoğu bilgisayardaki 64 bit işlemciler 64 bit kelimeler üzerinde çalıştımaktaydılar. O zamanlar, 32 bit sözcükleri işleyen eski bilgisayarlar da yaygın olarak mevcuttu. Daha basit mikroişlemciler, özellikle ekmek kızartma makinesi gibi cihazlarda kullanılanlar, 8 veya 16 bit sözcükler kullanırlar. 

Bir bit grubu içinde, 1 sütunundaki bit en az anlamlı bit (lsb) olarak adlandırılır ve diğer uçtaki bit, 6 bitlik bir ikili sayı için Şekil (a)'da gösterildiği gibi en anlamlı bit (msb) olarak adlandırılır. Benzer şekilde, bir sözcük içinde, baytlar, sekiz basamaklı onaltılık sayıda dört bayt için Şekil (b)'de gösterildiği gibi, en anlamlı bayt (MSB) aracılığıyla en az anlamlı bayt (LSB) olarak tanımlanır.

![MSBLSB](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/9.PNG)

Pratik bir tesadüf eseri, 2 <sup>10</sup> = 1024 ≈ 10 <sup>3</sup>. Dolayısıyla, kilo (Yunanca bin) terimi 2 <sup>10</sup>'u gösterir. Örneğin, 2 <sup>10</sup> bayt bir kilobayttır (1 KB). Benzer şekilde, mega (milyon) 2 <sup>20</sup> ≈ 10 <sup>6</sup> ve giga (milyar) 2 <sup>30</sup> ≈ 10 <sup>9</sup>'u gösterir. 2 <sup>10</sup> ≈ 1 bin, 2 <sup>20</sup> ≈ 1 milyon, 2 <sup>30</sup> ≈ 1 milyar olduğu bilindiğinde, 2 <sup>9</sup>'a kadar olan kuvvetlerini hatırlamak yeterli olacaktır. 

Örnek 1.6 Hesap makinesi kullanmadan 2 <sup>24</sup>'ün yaklaşık değerini bulun.

Çözüm: Üssü on'un katı ve kalanına bölün. 2 <sup>24</sup> = 2 <sup>20</sup> × 2 <sup>4</sup>.

2 <sup>20</sup> ≈ 1 milyon. 2 <sup>4</sup> = 16. Yani 2 <sup>24</sup> ≈ 16 milyon. Teknik olarak 2 <sup>24</sup> = 16.777.216, ancak 16 milyon pazarlama amaçları için yeterince yakındır.

1024 bayta kilobayt (KB) denir. 1024 bit, kilobit (Kb veya Kbit) olarak adlandırılır. Benzer şekilde MB, Mb, GB ve Gb, milyonlarca ve milyarlarca bayt ve bit için kullanılır. Bellek kapasitesi genellikle bayt cinsinden ölçülür. İletişim hızı genellikle bit / sn cinsinden ölçülür. Örneğin, bir çevirmeli modemin maksimum hızı genellikle 56 kbit / saniyedir.

# 1.4.5 İkilik Tabanda Toplama İşlemi

Aşağıdaki şekilde gösterilen ikilik tabanda toplama işlemi onluk tabandaki toplama işlemine çok benzemektedir. 

![toplama](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/10.png)

Ondalık toplamada olduğu gibi, iki sayının toplamı tek bir basamağa sığan sayıdan büyükse, sonraki sütuna 1 taşınmaktadır. Yukarıdaki şekil onluk toplama ile ikilik toplamayı karşılaştırmaktadır. Yukarıdaki şekilde en sağdaki sütununda, 9'dan büyük olduğu için 7 + 9 = 16 sayısı tek haneye sığmamaktadır. Bu durumda 16 sayısının birler basamağı olan 6 ilgili basamağa konulurken bir onluk sonraki basamağa taşınmaktadır. Benzer şekilde, ikili sistemde, iki sayının toplamı 1'den büyükse, taşan kısım bir sonraki basamağa taşınır. Örneğin, yukarıdaki şekilde (b) en sağdaki sütununda, 1 + 1 = 2 <sub>10</sub> = 10 <sub>2</sub> toplamı tek bir ikili haneye sığamaz. Bu durumda ilgili basamağa (0) kaydedip bir ikilik sonraki sütuna taşınır. İkinci sütunda toplam 1 + 1 + 1 = 3 <sub>10</sub> = 11 <sub>2</sub>'dir. Yine ilgili basamağa (1) kaydedip  bir ikilik bir sonraki sütuna taşınır. Komşu sütuna taşınan bit, taşıma biti olarak adlandırılır. 

Örnek 1.7 0111 <sub>2</sub> + 0101 <sub>2</sub>

![toplamaikili](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/11.png)

Dijital sistemler genellikle sabit sayıda basamak üzerinde çalışır. Sonuç, mevcut rakamlara sığmayacak kadar büyükse, toplamanın taştığı söylenir. Örneğin 4 bitlik bir sayı [0, 15] aralığına sahiptir. Sonuç 15'i aşarsa 4 bitlik ikili ekleme taşar. Beşinci bit atılır ve kalan dört bitte yanlış sonuç üretilir. Taşma, en önemli basamakta gerçekleşip gerçekleşmediği kontrol edilerek tespit edilebilir.

Örnek 1.8 1101 <sub>2</sub> + 0101 <sub>2</sub> hesaplayın. Taşma oluyor mu?

Çözüm: Aşağıdaki şekilde, toplamın 10010 <sub>2</sub> olduğunu göstermektedir. Bu sonuç, 4 bitlik ikili sayı aralığını aşmaktadır. Dört bit olarak saklanması gerekiyorsa, en önemli bit atılır ve 0010 <sub>2</sub>'nin yanlış sonucu bırakılır. Hesaplama, beş veya daha fazla bit içeren sayılar kullanılarak yapılmış olsaydı, sonuç 10010 <sub>2</sub> doğru olurdu.

![tasma](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/12.png)

# 1.4.6 İşaretli İkilik Sayılar
Şimdiye kadar, yalnızca pozitif büyüklükleri temsil eden işaretsiz ikili sayılar anlatıldı. Ancak genellikle hem pozitif hem de negatif sayılar kullanılmak istenirse? İşaretli ikili sayıları temsil etmek için çeşitli şemalar mevcuttur; en yaygın olarak kullanılanlar, işaret/büyüklük ve  ikiye tamlamadır.

# işaret/büyüklük sistemi

İşaret / büyüklük sayıları sezgisel olarak çekicidir çünkü negatif sayılar yazma geleneğimizi bir eksi işaretiyle ve ardından büyüklükle eşleştirir. Bir N-bit işaret / büyüklük sayısı, işaret olarak en önemli biti ve büyüklük olarak (mutlak değer) kalan N-1 biti kullanır. 0 işaret biti pozitif ve 1 işaret biti negatiftir.

Örnek 1.9  5 ve -5'i 4 bitlik işaret/büyüklük sayıları olarak yazın

Çözüm: Her iki sayının da büyüklüğü 5 <sub>10</sub> = 101 <sub>2</sub>'dir.

Dolayısıyla, 5 <sub>10</sub> = 0101 <sub>10</sub> ve
            -5 <sub>10</sub> = 1101 <sub>2</sub>

Ne yazık ki, sıradan ikili toplama, işaret/büyüklük sayıları için çalışmaz. Örneğin, −5 <sub>10</sub> + 5 <sub>10</sub>'da sıradan toplamanın kullanılması, 1101 <sub>2</sub> + 0101 <sub>2</sub> = 10010 <sub>2</sub>'yi verir ki bu saçmalıktır.

N-bitlik bir işaret/büyüklük numarası [−2 <sup>N−1</sup> + 1, 2 <sup>N−1</sup> − 1] aralığını kapsar. İşaret/büyüklük sayıları hem +0 hem de −0 mevcut olduğundan biraz tuhaftır. İkisi de sıfırı gösteriyor. Tahmin edebileceğiniz gibi, aynı sayı için iki farklı gösterimin olması zahmetli olabilir.

# İkiye tümleyen Sayılar

İkinin tümleyen sayıları, en anlamlı bit konumunun 2<sup>N−1</sup> yerine -2<sup>N−1</sup> ağırlığına sahip olması dışında, işaretsiz ikili sayılarla aynıdır. İşaret/büyüklük sayılarının eksikliklerinin üstesinden gelirler: sıfırın tek bir temsili vardır ve sıradan toplama işleri yapılabilmektedir.

İkinin tümleyen gösteriminde sıfır, tüm sıfırlar olarak yazılır: 00…000 <sub>2</sub>. En pozitif sayı, en anlamlı konumda 0 bulunmaktadır: 01…111 <sub>2</sub> = 2 <sup>N−1</sup> − 1. En negatif sayı, en anlamlı konumda 1 bulunmaktadır: 10…000<sub>2</sub> = -2<sup>N−1</sup> . Ve -1 hepsi birler olarak yazılır: 11…111 <sub>2</sub>.

En anlamlı konumda pozitif sayıların 0'a ve bu konumda negatif sayıların 1'e sahip olduğuna dikkat edin, bu nedenle en anlamlı bit işaret biti olarak görülebilir. Bununla birlikte, kalan bitler, işaret/büyüklük sayılarından ziyade ikiye tümleyen sayılar için farklı yorumlanmaktadır.
 
İkiye tümleyen sayılarının işareti, ikiye tümleyen alma adı verilen bir işlemde tersine çevrilebilmektedir. İşlem, sayıdaki tüm bitlerin ters çevrilmesini ve ardından en az anlamlı bit konumuna 1 eklenmesini içerir. Bu, negatif bir sayının temsilini bulmak veya negatif bir sayının büyüklüğünü belirlemek için kullanışlıdır.

Örnek 1.10 −2 <sub>10</sub>'un 4 bitlik ikiye tümleyen sayı olarak gösterimini bulun.

Çözüm: + 2 <sub>10</sub> = 0010 <sub>2</sub> ile başlayın. −2 <sub>10</sub>'u elde etmek için bitleri ters çevirin ve 1 ekleyin. 0010<sub>2</sub>'yi ters çevirmek 1101 <sub>2</sub> üretir. 1101 <sub>2</sub> + 1 = 1110 <sub>2</sub>. Yani −2 <sub>10</sub>, 1110 <sub>2</sub>'dir.

Örnek 1.11 1001 <sub>2</sub> ikiye tümleyen sayısının onluk değerini bulun.

Çözüm: 1001 <sub>2</sub>'nin başında 1 vardır, bu nedenle negatif olmalıdır. Büyüklüğünü bulmak için bitleri ters çevirin ve 1 ekleyin. 1001 <sub>2</sub> = 0110 <sub>2</sub>'yi ters çevirin. 0110 <sub>2</sub> + 1 = 0111 <sub>2</sub> = 7 <sub>10</sub>.

Dolayısıyla, 1001 <sub>2</sub> = -7 <sub>10</sub>.

İkinin tümleyen sayıları, toplama işleminin hem pozitif hem de negatif sayılar için düzgün çalışması gibi zorlayıcı bir avantaja sahiptir. N-bit sayıları eklerken, N'inci bitin (yani, N + 1'inci sonuç bitinin) yürütülmesinin atıldığını hatırlayın.

Örnek 1.12 İkinin tümleyen sayılarını kullanarak (a) −2 <sub>10</sub> + 1 <sub>10</sub> ve (b) −7 <sub>10</sub> + 7 <sub>10</sub>'u hesaplayın.

Çözüm: (a) −2 <sub>10</sub> + 1 <sub>10</sub> = 1110 <sub>2</sub> + 0001 <sub>2</sub> = 1111 <sub>2</sub> = −1 <sub>10</sub>. (b) −7 <sub>10</sub>+ 7 <sub>10</sub>= 1001 <sub>2</sub> + 0111 <sub>2</sub> = 10000 <sub>2</sub>. Beşinci bit atılır ve doğru 4 bitlik sonuç 0000 <sub>2</sub> bırakılır.

Çıkarma, ikinci sayının ikisinin tümleyeni alınarak, ardından eklenerek gerçekleştirilir.

Örnek 1.13 (a) 5 <sub>10</sub> − 3 <sub>10</sub> ve (b) 3 <sub>10</sub> − 5 <sub>10</sub>'u 4-bit ikinin tümleyen sayılarını kullanarak hesaplayın.

Çözüm: (a) 3 <sub>10</sub> = 0011 <sub>2</sub>. −3 <sub>10</sub> = 1101 <sub>2</sub> olduğu için; 5 <sub>10</sub> + (−3 <sub>10</sub>) = 0101 <sub>2</sub> + 1101 <sub>2</sub> = 0010 <sub>2</sub> = 2 <sub>10</sub> sonuç dört bitte saklanır.
(b) -5 <sub>10</sub> = 1011 ise; 3 <sub>10</sub> + (−5 <sub>10</sub>) = 0011 <sub>2</sub> + 1011 <sub>2</sub> = 1110 <sub>2</sub> = −2 <sub>10</sub> olmaktadır. 

0 sayısının ikiye tümleyen gösterimi için, tüm bitleri ters çevirilir (11…111 <sub>2</sub> ) 1 ekleyerek bulunur. İşaret/büyüklük sisteminden farklı olarak, ikisinin -0 yoktur. Sıfır, işaret biti 0 olduğu için pozitif olarak kabul edilir.



