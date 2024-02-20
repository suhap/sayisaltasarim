
#1.1 Mikroişlemci Gelişiminin Önemi

Mikroişlemcilerin keşfi, cep telefonu ve internet gibi günlük hayatımızı kökten değiştiren teknolojilerin ortaya çıkmasını sağlamıştır. Mikroişlemcilerin inanılmaz hızlı gelişimi sayesinde günümüzde kullanılan bir akıllı telefon, otuz yıl önceki bir sunucudan çok daha fazla yeteneğe sahip olabilmektedir. Bu gelişmeler, birçok alanda mevcut cihazların evrim geçirmesine ve yeni cihazların ortaya çıkmasına yol açmıştır. Gelişmiş ve yeni cihazlar, kullanıldıkları alanda köklü değişikliklere yol açmıştır. Örneğin, insansız hava araçlarının ortaya çıkması, orduların savaşma şeklini ve stratejilerini önemli ölçüde değiştirmiştir. Önemli bir ekonomik etkiye sahip olan mikroişlemci satışlarının 2030 yılında 128 milyon dolara çıkması beklenmektedir. Teknik, ekonomik ve sosyal etkilerinin yanı sıra, mikroişlemci mimarisi en karmaşık insan icatlarından biridir.

Bu derste 1'ler ve 0'lar üzerinde çalışan sayısal sistemlerin tasarımına odaklanılmaktadır. Bu sistemlerin en temel birimi olan mantık kapıları ve mantık kapıları kullanılarak oluşturulan toplayıcılar ve bellekler gibi daha karmaşık modüller incelenecektir. Bu modüllerden biri olan mikroişlemci mimarisi tek seferde anlaşılamayacak kadar karmaşıktır. Ders süresince karmaşıklığın nasıl yönetileceği üzerinde durulacaktır.

# 1.2 Karmasıklık Yönetimi
Bir mühendisi veya bilim adamını sıradan bir kişiden ayıran en önemli özelliklerden biri, karmaşıklığı  nasıl yönetileceğine dair sistematik bir yaklaşım geliştirebilmesidir. Modern sayısal sistemler, milyarlarca transistörden oluşmaktadır. Hiçbir insan, her transistördeki elektronların hareketini tanımlayan denklemler çözerek bu sistemleri anlayamaz. Bir mikroişlemcinin nasıl oluşturulacağını anlamak için karmaşıklığı yönetiminin öğrenilmesi gerekmektedir.

# 1.2.1 Soyutlama
Karmaşıklığı yönetmenin en temel tekniği soyutlamadır: önemsiz ayrıntıları gizlemek. Bir sistem birçok farklı soyutlama seviyesinde incelenebilir. Örneğin, Amerikalı politikacılar dünyayı şehirler, bölgeler, eyaletler ve ülkeler olarak soyutlar. Bir bölge birden fazla şehir ve bir eyalet birçok bölge içerebilir. Bir politikacı cumhurbaşkanlığı için yarışırken, her bir bölgenin nasıl oy kullandığından ziyade çoğunlukla devletin bir bütün olarak nasıl oy kullanacağıyla ilgilenir, bu nedenle devlet en kullanışlı soyutlama düzeyidir. Öte yandan, seçim bürosu her şehrin nüfusunu ölçer, bu nedenle daha düşük bir soyutlama düzeyinin ayrıntılarını dikkate almalıdır.

![soyutlamaTablosu](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/1.png)

Yukarıdaki şekil bir bilgisayar sistemi için soyutlama sevyelerini göstermektedir. En düşük soyutlama sevyesi elektronların hareketlerinin tanımlandığı fiziktir. Elektronların davranışı kuantum mekaniği ve Maxwell denklemleri ile tanımlanabilir. Derste üzerinde duracağımız sayısal sistemlerin yapı taşları transistör (bir zamanlar vakum tüpleri) adı verilen elektronik cihazlardır. Bu cihazlar, terminal adı verilen iyi tanımlanmış bağlantı noktalarına sahiptir ve terminalde ölçülen gerilim ve akım arasındaki ilişki kullanılarak matematiksel olarak modellenebilir. Soyutlama kavramı sayesinde, bir cihazın içindeki elektron davranışını görmezden gelinebilir, böylece sisteme cihaz sevyesinden bakabilme fırsatı yakalanabilir. Bir üst soyutlama sevyesi(analog devre soyutlaması) transistör gibi elektronik devrelerin bir araya gelerek analog devre elemanlarını(ükselteç-amplifiers-) oluşturulmasını tanımlar. Analog devre elemanları  kesintisiz akım/voltaj giriş ve çıkışına sahiptir. Sayısal devreler ise 0 ve 1 gibi ayrık voltaj seviyelerine sahiptir. Lojik tasarımda sayısal devre elemanları kullanarak toplayıcı ve hazıfa gibi daha karmaşık devreler inşa edilcektir.

Mikromimari(Microarchitecture), lojik cihazların kullanıldığı devre mimarisini tanımlamaktadır. Bu soyutlama düzeyi bir yazılımcının gözünden bilgisayar mimarisini tasarlamaktadır. Örneğin, kişisel bilgisayarda (PC) kullanılan Intel x86 mimarisi, programcıların kullandığı komutlar ve saklayıcıları (değişkenleri geçici olarak depolamak için bellek) tanımlamaktadır. Mikromimarisi ise mimari tarafından tanımlanan bu komutları çalıştırabilmek için gerekli lojik devre mimarisidir. Belirli bir mimari, farklı fiyat/performans/güç  kriterlerine sahip farklı mikromimariden biri tarafından gerçekleştirilir. Örneğin x86 mimarisi, Intel Core i7, Intel 80486 ve AMD Athlon gibi farklı mikromimarilerden biri kullanılarak gerçekleştirilebilir.

Mimarinin bir üst seviyesi olan İşletim Sistemi, sabit bir sürücüye erişim veya bellek yönetimi gibi düşük düzeyli ayrıntıları ele almaktadır. Son olarak Uygulama katmanı, kullanıcının ihtiyaç duyduğu programları işletim sistemi marifeti ile sunmaktadır. Soyutlama sayesinde annelerimiz kuantum fizik bilgisi veya bilgisayar organizasyon bilgisine ihtiyaç duymadan internette gezinebilmektedir.

Bu ders bilgisayar mimarisinin oluşturan sayısal devre soyutlama sevyesine odaklanacaktır. Bir soyutlama düzeyinde çalışırken, çalıştığınız yerin hemen üstündeki ve altındaki soyutlama düzeyleri hakkında bir şeyler bilmek iyidir. Örneğin bir bilgisayar mühendisi yazdığı programın çalışacağı mimariyi anlamadan optimize kod yazması mümkün değildir. 

# 1.2.2 Disiplin

Yüksek soyutlama sevyelerinden efektif çalışmak için tasarım seçimlerinin biliçli olarak kısıtlanmaktadır. Değiştirilebilir parçaların kullanılması, bilinen bir disiplin uygulamasıdır. Değiştirilebilir parçaların ilk örneklerinden biri çakmaklı tüfek imalatıdır. 19. yüzyılın başlarına kadar tüfekler tek tek elle yapılmaktaydı. Birçok farklı ustadan satın alınan parçalar, yetenekli bir silah ustası tarafından dikkatlice bir araya getirilmektedi. Değiştirilebilir parçaların kullanımı endüstride devrim yarattı. Tüfek parçalarının iyi tanımlanmış standartlarla sınırlandırılması sayesinde tüfekler çok daha hızlı ve daha az beceriyle monte edilebilir ve onarılabilir oldular. Bu sayede silah ustaları tek bir namlu veya dipçiğin şekil ile ilgilenmek gibi daha düşük soyutlama sevyeleri ile ilgilenmez oldular. 

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
İlkokulda, sayma ve matematiksel işlemler (mutemelen on parmağımız olduğu için) ondalık olarak yapmak öğretilmektedir. Ondalık sayı sisteminde on tane ondalık basamak vardır: 0, 1, 2, ..., 9. Ondalık basamaklar, daha uzun ondalık sayılar oluşturmak için birleştirilir. Ondalık sayının her sütunu, önceki sütunun on katı ağırlığa sahiptir. Sağdan sola, sütun ağırlıkları 1, 10, 100, 1000 vb. şeklindedir. Ondalık sayılar, taban 10 olarak adlandırılır. Birden fazla tabda çalışılırsa karışıklığı önlemek için çalışılan taban sayıdan sonra bir alt simge ile gösterilir. Aşağıdaki şekil 9742 <sub>10</sub> ondalık sayısının nasıl her bir basamağının toplamı olarak karşılık gelen sütunun ağırlığıyla çarpılarak yazıldığını göstermektedir.

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
 2 <sup>8</sup> = 256 olasılıktan birini temsil eden sekiz tane bite bayt denir. Bilgisayar belleklerinde depolanan nesnelerin boyutu, alışılmış olarak bit yerine bayt olarak ifade edilmektedir. 
 
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

İşaretsiz sayılar gibi, N-bit ikiye tümleyen sayılar da  2N olası değerden birini temsil eder. Ancak değerler pozitif ve negatif sayılar arasında bölünür. Örneğin, 4 bitlik işaretsiz bir sayı 16 değeri temsil eder: 0 ila 15. 4 bitlik bir ikiye tümleyen sayı da 16 değeri temsil eder: -8 ila 7. Genel olarak, N-bit ikiye tümleyen sayısı aralığı [− 2 <sup>N-1</sup>, 2 <sup>N-1</sup> - 1]. Pozitif sayıların sayısına göre bir fazla negatif sayı vardır, çünkü -0 yoktur. En düşük negatif sayı 10…000 <sub>2</sub> = −2 <sup>N−1</sup> bazen garip sayı olarak adlandırılır. İkiye tümleyen, bitleri ters çevirerek (01…111 <sub>2</sub>) ve 1 ekleyerek bulunur:  10…000 <sub>2</sub>. Dolayısıyla, bu negatif sayının pozitif karşılığı yoktur.

Sonuç 2 <sup>N−1</sup> − 1'den büyük veya −2 <sup>N−1</sup>'den küçükse, N-bit pozitif sayı veya negatif sayı eklemek taşmaya neden olabilir. Negatif bir sayıya pozitif bir sayı eklemek asla taşmaya neden olmaz. İşaretsiz sayıların aksine, en önemli sütun taşmayı göstermez. Bunun yerine, eklenen iki sayı aynı işaret bitine sahipse ve sonuç zıt işaret bitine sahipse taşma meydana gelir.

4 Haziran 1996'da fırlatılan 7 milyar dolarlık Ariane 5 roketi, fırlatıldıktan 40 saniye sonra rotasından saptı, dağıldı ve patladı. Arıza, roketi kontrol eden bilgisayarın 16 bitlik aralığını aşması ve çökmesi sonucu meydana geldi.

Kod, Ariane 4 roketinde kapsamlı bir şekilde test edilmişti. Ancak Ariane 5, kontrol bilgisayarı için daha büyük değerler üreten ve taşmaya yol açan daha hızlı bir motora sahipti.

Örnek 1.14 4 bit ikinin tümleyen sayılarını kullanarak 4 <sub>10</sub> + 5 <sub>10</sub> sonucu nedir. Sonuç taşar mı?
Çözüm: 4 <sub>10</sub> + 5 <sub>10</sub>= 0100 <sub>2</sub> + 0101 <sub>2</sub> = 1001 <sub>2</sub> = -7 <sub>10</sub>. Sonuç, 4 bitlik pozitif ikiye tümleyen sayıların aralığını aşarak yanlış bir negatif sonuç üretir. Hesaplama beş veya daha fazla bit kullanılarak yapılmış olsaydı, 01001 <sub>2</sub> = 9 <sub>10</sub> sonucu doğru olurdu.

İkiye tümleyen sayısı daha fazla bite genişletildiğinde, işaret biti en anlamlı bit konumlarına kopyalanmalıdır. Bu işleme işaret uzantısı denir. Örneğin, 3 ve −3 sayıları sırasıyla 0011 ve 1101'in 4 bitlik ikinin tümleyen sayıları olarak yazılır. Sırasıyla 0000011 ve 1111101'i oluşturmak için işaret bitini üç yeni üst bite kopyalayarak yedi bite işaret genişletilirler.
# Sayı sistemlerinin karşılaştırılması

En yaygın olarak kullanılan üç ikili sayı sistemi, işaretsiz, ikiye tümleyen ve işaret/büyüklüktür. Aşağıdaki tabloda, bu üç sistem N-bit sayı aralığında karşılaştırılmaktadır. İkiye tümleyen sayıları hem pozitif hem de negatif tamsayıları temsil ettikleri ve sıradan toplamanın tüm sayılar için işe yaradığı için uygundur. Çıkarma, ikinci sayının olumsuzlanması (yani ikisinin tümleyeni alınarak) ve ardından eklenmesiyle gerçekleştirilir. Aksi belirtilmedikçe, tüm işaretli ikili sayıların ikiye tümleyen gösterimini kullandığını varsayılmaktadır.

![sayisistemleri](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/13.PNG)

Aşağıdaki şekilde, her sistemdeki 4 bitlik sayıların değerlerini gösteren bir sayı doğrusu göstermektedir. İşaretsiz sayılar normal ikili düzende [0, 15] aralığını kapsar. İkinin tümleyen sayıları [-8, 7] aralığını kapsar. Negatif olmayan sayılar [0, 7], işaretsiz sayılarla aynı kodlamaları paylaşır. Negatif sayılar [-8, -1], daha büyük bir işaretsiz ikili değer 0'a daha yakın bir sayıyı temsil edecek şekilde kodlanmıştır. Tuhaf sayı 1000'in -8'i temsil ettiğine ve pozitif bir karşılığı olmadığına dikkat edin. İşaret/büyüklük sayıları [−7, 7] aralığını kapsar. En önemli bit işaret bitidir. Pozitif sayılar [1, 7] işaretsiz sayılarla aynı kodlamaları paylaşır. Negatif sayılar simetriktir ancak işaret biti ayarlanmıştır. 0, hem 0000 hem de 1000 ile temsil edilir. Bu nedenle, N-bit işaret/büyüklük sayıları, 0'ın iki temsili nedeniyle yalnızca 2 <sup>N</sup> − 1 tamsayıları temsil eder.

![sayisistemleridogru](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/14.PNG)

# 1.5. Lojik Kapılar
Artık bilgiyi temsil etmek için ikili değişkenleri nasıl kullanacağımızı bildiğimize göre, bu ikili değişkenler üzerinde işlemler gerçekleştiren sayısal sistemleri keşfediyoruz. Mantık kapıları, bir veya daha fazla ikili girişi alan ve bir ikili çıktı üreten basit sayısal devrelerdir. Mantık kapıları, girişi (veya girişleri) ve çıkışı gösteren bir sembolle çizilir. Girişler genellikle solda (veya üstte) ve çıkışlar sağda (veya altta) çizilir. Sayısal tasarımcılar tipik olarak kapı girişleri için alfabenin başlangıcına yakın harfleri ve kapı çıkışı için Y harfini kullanır. Girişler ve çıkış arasındaki ilişki bir doğruluk tablosu veya Boole denklemi ile açıklanabilir. Doğruluk tablosu soldaki girişleri ve sağdaki ilgili çıktıları listeler. Her olası girdi kombinasyonu için bir satır vardır. Bir Boole denklemi, ikili değişkenler kullanan matematiksel bir ifadedir.

## 1.5.1 NOT Kapısı
Bir NOT geçidinin aşağıdaki şekilde gösterildiği gibi bir girişi, A ve bir çıkışı vardır. NOT geçidinin çıkışı, girişinin tersidir. A YANLIŞ ise, Y DOĞRUDUR. A DOĞRU ise, Y YANLIŞ demektir. Bu ilişki, şekildeki doğruluk tablosu ve Boole denklemi ile özetlenmiştir. Boole denkleminde A üzerindeki çizgi NOT olarak telaffuz edilir, bu nedenle Y = A’  "Y eşittir NOT A" olarak okunur. NOT geçidi ayrıca bir inverter olarak da adlandırılır. Diğer metinler NOT için Y = A ′, Y = ¬A, Y =! A veya Y = ~ A dahil olmak üzere çeşitli gösterimler kullanır. Yalnızca Y = A’   'yı kullanacağız, ancak başka bir yerde başka bir gösterimle karşılaşırsanız şaşırmayın.

![NOT](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/15.png)

## 1.5.2 Buffer
Diğer tek girişli mantık geçidi buffer olarak adlandırılır ve aşağıdaki şekilde gösterilmektedir. Sadece girdiyi çıktıya kopyalar.
Mantıksal açıdan bakıldığında, bir tampon telden farklı değildir, bu yüzden işe yaramaz görünebilir. Bununla birlikte, analog bakış açısından, buffer, bir motora büyük miktarlarda akım verme yeteneği veya çıkışını birçok kapıya hızlı bir şekilde gönderme yeteneği gibi arzu edilen özelliklere sahip olabilir. Bu, bir sistemi tam olarak anlamak için neden birden çok soyutlama düzeyini dikkate almamız gerektiğinin bir örneğidir; sayısal soyutlama, bir tamponun gerçek amacını gizler.
 Üçgen sembolü bir buffer i  gösterir. Çıktı üzerindeki bir daireye balon adı verilir ve üsteki şekilde gösterildiği gibi NOT kapısı sembolünde görüldüğü gibi ters çevirmeyi gösterir.
 
![Buffer](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/16.png)

## 1.5.3 AND Kapısı
İki girişli mantık kapıları daha ilginçtir. Alttaki şekilde gösterilen AND geçidi, ancak ve ancak hem A hem de B TRUE ise, bir TRUE çıkışı, Y üretir. Aksi takdirde çıktı FALSE olur. Kural olarak, girişler sanki ikili olarak sayıyormuşsunuz gibi 00, 01, 10, 11 sırasına göre listelenir. Bir AND geçidi için Boole denklemi birkaç şekilde yazılabilir: Y = A • B, Y = AB veya Y = A ∩ B. ∩ sembolü “kesişme” olarak telaffuz edilir ve mantıkçılar tarafından tercih edilir. Y = AB'yi tercih ediyoruz, "Y eşittir A ve B" yi okuyoruz çünkü tembeliz.

![And](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/17.png)

## 1.5.4 OR Kapısı
Aşağıdaki şekilde gösterilen OR geçidi, eğer A veya B (veya her ikisi) DOĞRU ise, Y, bir DOĞRU çıktı üretir. OR geçidi için Boole denklemi Y = A + B veya Y = A ∪ B olarak yazılır. ∪ sembolü birleşim olarak telaffuz edilir ve mantıkçılar tarafından tercih edilir. Dijital tasarımcılar normalde + gösterimini kullanır, Y = A + B, "Y eşittir A veya B" olarak telaffuz edilir.

![OR](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/18.png)

## 1.5.5 Diğer İki Girişli Kapılar
Aşağıdaki şekil diğer ortak iki girişli mantık kapılarını gösterir. XOR (özel OR, "eski OR" olarak telaffuz edilir), eğer A veya B, ancak ikisi de DOĞRU ise, DOĞRUDUR. Herhangi bir kapıyı, çalışmasını tersine çevirmek için bir balon takip edebilir. NAND geçidi NOT AND gerçekleştirir. Her iki giriş TRUE olmadıkça çıkışı TRUE'dur. NOR geçidi NOT OR gerçekleştirir. Ne A ne de B DOĞRU değilse çıktısı DOĞRUDUR. Bir N-girişli XOR geçidi bazen bir eşlik geçidi olarak adlandırılır ve eğer tek sayıda giriş TRUE ise bir TRUE çıktı üretir. İki girişli geçitlerde olduğu gibi, doğruluk tablosundaki giriş kombinasyonları sayım sırasına göre listelenir.

![Digerikigiris](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/19.png)

Örnek 1.15 Aşağıdaki şekil XOR'un tersini gerçekleştiren iki girişli bir XNOR geçidi için sembolü ve Boole denklemini göstermektedir. Doğruluk tablosunu tamamlayın.

![XOR](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/20.png)


Çözüm: Aşağıdaki şekil doğruluk tablosunu göstermektedir. Her iki giriş de FALSE veya her iki giriş de TRUE ise XNOR çıkışı TRUE'dur. İki girişli XNOR geçidi bazen bir eşitlik kapısı olarak adlandırılır çünkü girişler eşit olduğunda çıkışı TRUE olur.

![Dogruluktablosu](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/21.png)

## 1.5.6 Çok Girişli Kapılar

Üç veya daha fazla girişin birçok Boole işlevi mevcuttur. En yaygın olanları AND, OR, XOR, NAND, NOR ve XNOR'dur. Bir N-giriş AND geçidi, tüm N girişleri DOĞRU olduğunda bir DOĞRU çıkış üretir. Bir N-giriş VEYA geçidi, en az bir giriş DOĞRU olduğunda bir DOĞRU çıkış üretir.

Örnek 1.16 Aşağıdaki şekilde üç girişli NOR geçidi için sembolü ve Boole denklemini gösterir. Doğruluk tablosunu tamamlayın.

![NOR3](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/22.PNG)

Çözüm: Aşağıdaki şekil doğruluk tablosunu göstermektedir. Çıkış, yalnızca girişlerden hiçbiri DOĞRU değilse TRUE olur.

![DogrulukT](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/23.png)

# 1.6 Dijital Soyutlamaya Yakından Bakış
Dijital bir sistem, ayrık değerli değişkenler kullanır. Bununla birlikte, değişkenler bir tel üzerindeki voltaj, bir dişlinin konumu veya bir silindirdeki sıvı seviyesi gibi sürekli fiziksel miktarlarla temsil edilir. Bu nedenle, tasarımcı sürekli değeri ayrık değerle ilişkilendirmek için bir yol seçmelidir.

Örneğin, bir teldeki voltajla ikili bir sinyal A'yı temsil ettiğini düşünün. 0 volt (V) A = 0 ve 5 V ise A = 1 olsun. Herhangi bir gerçek sistem bir miktar gürültüye tolerans göstermelidir, bu nedenle 4,97 V muhtemelen A = 1 olarak yorumlanmalıdır. Peki ya 4.3V, 2.8 V veya 2.500000 V nasıl yorumlanır?

## 1.6.1 Besleme Gerilim
Sistemdeki en düşük voltajın, toprak veya GND olarak da adlandırılan 0 V olduğunu varsayalım. Sistemdeki en yüksek voltaj güç kaynağından gelir ve genellikle VDD olarak adlandırılır. 1970'lerde ve 1980'lerin teknolojisinde, VDD genellikle 5 V idi. Çipler daha küçük transistörlere doğru ilerledikçe, VDD 3,3 V'a düştü, Güç tasarrufu yapmak ve transistörlerin aşırı yüklenmesini önlemek için 2,5 V, 1,8 V, 1,5 V, 1,2 V veya daha da düşmektedir.

## 1.6.2 Lojik Seviye
Sürekli bir değişkenin ikilik tabandaki bir sayıya dönüştürme işlemi, aşağıdaki şekilde gösterildiği gibi mantık seviyeleri tanımlanarak yapılır. İlk kapıya sürücü adı verilirken ikinci kapıya alıcı denir. Sürücünün çıkışı, alıcının girişine bağlanır. Sürücü, 0 ila V <sub>OL</sub> aralığında bir DÜŞÜK (0) çıkış veya V <sub>OH</sub> ila V <sub>DD</sub> aralığında bir YÜKSEK (1) çıkış üretir. Alıcı, 0 ila V <sub>IL</sub> aralığında bir giriş alırsa, girişi DÜŞÜK olarak değerlendirecektir. Alıcı, V <sub>IH</sub> ila V <sub>DD</sub> aralığında bir giriş alırsa, girişi HIGH olarak değerlendirecektir. Gürültü veya hatalı elemanlar gibi nedenlerle, alıcının girişi V <sub>IL</sub> ve V <sub>IH</sub> arasındaki yasak bölgeye düşerse, kapının davranışı tahmin edilemez. V <sub>OH</sub>, V <sub>OL</sub>, V <sub>IH</sub> ve V <sub>IL</sub>, çıkış ve giriş yüksek ve düşük mantık seviyeleri olarak adlandırılır.

![Lojiksevye](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/24.PNG)

## 1.6.3 Gürültü Aralıgı
Sürücünün çıkışı alıcının girişi bağlandığında, V <sub>OL</sub> < V <sub>IL</sub> ve V <sub>OH</sub> > V <sub>IH</sub> seçmeliyiz. Bu nedenle, sürücünün çıkışı bir miktar gürültü ile kirlenmiş olsa bile, alıcının girişi yine de doğru mantık seviyesini tespit edecektir. Gürültü aralığı, sinyalin hala geçerli bir girdi olarak yorumlanabilmesi için en kötü durum çıkışına eklenebilecek gürültü miktarıdır. Aşağıdaki şekilde görülebileceği gibi, sırasıyla düşük ve yüksek gürültü aralıkları;

![gurultuaralıgı](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/25.PNG)

 
Örnek 1.18 Aşağıdaki şekildeki tersleyici devresini düşünün. V <sub>O1</sub>, inverter I <sub>1</sub>'in çıkış voltajıdır ve V <subI2</sub>, tersleyici I <sub>2</sub>'nin giriş voltajıdır. Her iki tersleyicide aşağıdaki özelliklere sahiptir: V <sub>DD</sub> = 5V, V <sub>IL</sub> = 1.35V, V <sub>IH</sub> = 3.15V, V <sub>OL</sub> = 0.33V ve V <sub>OH</sub> = 3.84V. Tersleyici düşük ve yüksek gürültü aralıkları nedir? Devre, V <sub>O1</sub> ve V <sub>I2</sub> arasındaki 1V gürültüyü tolere edebilir mi?

![tersleyicidevresi](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/26.PNG)

Çözüm: Sürücü gürültü marjları: NM <sub>L</sub> = V <sub>IL</sub> - V <sub>OL</sub> = (1,35V - 0,33V) = 1,02V, NM <sub>H</sub> = V <sub>OH</sub> - V <sub>IH</sub> = (3,84V - 3,15V) = 0,69V. Devre, çıkış LOW (NM <sub>L</sub> = 1,02 V) olduğunda 1V gürültüyü tolere edebilir, ancak çıkış YÜKSEK (NM <sub>H</sub> = 0,69 V) olduğunda bunu tolere edemez. Örneğin, I1 sürücüsünün en kötü durumdaki YÜKSEK değerini, V <sub>O1</sub> = V <sub>OH</sub> = 3,84 V verdiğini varsayalım. Gürültü, alıcının girişine ulaşmadan önce voltajın 1 V düşmesine neden oluyorsa, V <sub>I2</sub> = (3,84V - 1V) = 2,84V. Bu kabul edilebilir giriş YÜKSEK değerinden daha düşüktür, V <sub>IH</sub> = 3,15 V, bu nedenle alıcı uygun bir YÜKSEK girişi algılamayabilir.


## 1.6.4 DC iletim karakteristigi
Sayısal soyutlamanın sınırlarını anlamak için, bir kapının analog davranışını araştırmalıyız. Bir kapının DC transfer karakteristikleri, giriş, çıkışın devam edebilmesi için yeterince yavaş değiştirildiğinde çıkış voltajını giriş voltajının bir fonksiyonu olarak tanımlar. Giriş ve çıkış voltajları arasındaki ilişkiyi tanımladıkları için transfer özellikleri olarak adlandırılırlar.

İdeal bir tersleyici, Aşağıdaki şekil (a) 'da gösterildiği gibi, V <sub>DD</sub>/2'de ani bir anahtarlama eşiğine sahip olacaktır. V (A) < V <sub>DD</sub> / 2 için, V (Y) = V <sub>DD</sub>. V (A)> V <sub>DD</sub> / 2 için, V (Y) = 0. Böyle bir durumda V <sub>IH</sub> = V <sub>IL</sub> = V <sub>DD</sub> / 2. V <sub>OH</sub> = V <sub>DD</sub> ve V <sub>OL</sub> = 0. Şekil (b) 'de gösterildiği gibi, gerçek bir tersleyici uç noktalar arasında daha kademeli olarak değişir. Giriş voltajı V (A) 0 olduğunda, çıkış voltajı V (Y) = V <sub>DD</sub>. V (A) = V <sub>DD</sub> olduğunda, V (Y) = 0. Ancak, bu uç noktalar arasındaki geçiş yumuşaktır ve tam olarak V <sub>DD</sub> / 2'de ortalanmayabilir. Bu mantık seviyelerinin nasıl tanımlanacağı sorusunu gündeme getirmektedir.

Mantık seviyelerini seçmek için makul bir yer, transfer karakteristiği dV (Y) / dV (A) eğiminin −1 olduğu yerdir. Bu iki nokta, birim kazanç noktaları olarak adlandırılır. Birim kazanç noktalarında mantık seviyelerinin seçilmesi genellikle gürültü marjlarını maksimize eder. V <sub>IL</sub> azaltılırsa, V <sub>OH</sub> yalnızca küçük bir miktar artar. Ancak V <sub>IL</sub> artırılsaydı, V <sub>OH</sub> hızla düşerdi.

![DC](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/27.png)

## 1.6.5 Static displin
Girişlerin yasak bölgeye düşmesini önlemek için dijital mantık kapıları statik disipline uyacak şekilde tasarlanmıştır. Statik disiplin, mantıksal olarak geçerli girdiler verildiğinde, her devre elemanının mantıksal olarak geçerli çıktılar üretmesini gerektirir.

Dijital tasarımcılar, statik disipline uyarak, dijital devrelerin basitliği ve sağlamlığı karşılığında rastgele analog devre elemanlarını kullanma özgürlüğünden feragat ederler. Soyutlama düzeyini analogdan dijitale yükseltirler, gereksiz ayrıntıları gizleyerek tasarım verimliliğini artırır.

V <sub>DD</sub> ve mantık seviyelerinin seçimi isteğe bağlıdır, ancak iletişim kuran tüm kapılar uyumlu mantık seviyelerine sahip olmalıdır. Bu nedenle kapılar, mantık ailesindeki tüm kapılar, ailedeki diğer kapılar ile birlikte kullanıldığında statik disipline uyacak şekilde mantık aileleri halinde gruplandırılır. Aynı mantık ailesindeki mantık kapıları, tutarlı güç kaynağı voltajları ve mantık seviyeleri kullandıklarından legolar gibi birbirine geçerler.

1970'lerden 1990'lara kadar baskın olan dört ana mantık ailesi, Transistör-Transistör Mantığı (TTL), Tamamlayıcı Metal Oksit-Yarıiletken Mantığı (CMOS, sea-moss), Düşük Voltaj TTL Mantığı (LVTTL) ve Düşük Voltaj CMOS Mantığıdır (LVCMOS). Mantık seviyeleri aşağıdaki tabloda karşılaştırılmıştır. 


![Table](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/28.png)

Örnek 1.19 Yukarıdaki mantık ailelerinden hangileri birbiriyle güvenilir bir şekilde iletişim kurabilir?

Çözüm: Aşağıdaki tablo, hangi mantık ailelerinin uyumlu mantık düzeylerine sahip olduğunu listeler. TTL veya CMOS gibi 5V mantık ailesinin 5V kadar YÜKSEK bir çıkış voltajı üretebileceğini unutmayın. Bu 5V sinyal, LVTTL veya LVCMOS gibi 3,3V mantık ailesinin girişini yönlendirirse, alıcı özel olarak "5 volt uyumlu" olacak şekilde tasarlanmadıkça alıcıya zarar verebilir.

![Tablecompatible](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/29.png)

# 1.7 CMOS Transistorler

Babbage’ın Analitik Motoru dişlilerden yapıldı ve ilk elektrikli bilgisayarlar röleler veya vakum tüpleri kullanıyordu. Modern bilgisayarlar, ucuz, küçük ve güvenilir oldukları için transistör kullanır. Transistörler, bir kontrol terminaline voltaj veya akım uygulandığında AÇILAN veya KAPATILAN elektrikle kontrol edilen anahtarlardır. İki ana transistör türü, bipolar bağlantı transistörleri ve metal oksit-yarı iletken alan etkili transistörleridir (sırasıyla "yosun fetleri" veya "M-O-S" olarak telaffuz edilen MOSFET'ler veya MOS transistörleri). 

1958'de Texas Instruments'tan Jack Kilby, iki transistör içeren ilk entegre devreyi kurdu. 1959'da Fairchild Semiconductor'dan Robert Noyce, tek bir silikon çip üzerinde birden fazla transistörü birbirine bağlama yönteminin patentini aldı. O zamanlar transistörlerin her biri yaklaşık 10 dolara mal oluyor.

Otuz yılı aşkın süredir benzeri görülmemiş üretim ilerlemeleri sayesinde, mühendisler artık 1 cm <sub>2</sub> silikon çip üzerine yaklaşık bir milyar MOSFET paketleyebiliyor ve bu transistörlerin her biri 10 mikro sentten daha ucuza mal oluyor. Kapasite ve maliyet, yaklaşık olarak her 8 yılda bir büyük ölçüde artmaya devam ediyor. MOSFET'ler artık neredeyse tüm dijital sistemlerin yapı taşlarıdır. Bu bölümde, mantık kapılarının MOSFET'lerden nasıl inşa edildiğini görmek için dijital soyutlamanın altına bakacağız.

## 1.7.1 Yarıiletkenler

MOS transistörleri, kaya ve kumdaki baskın atom olan silikondan yapılmıştır. Silikon (Si) bir grup IV atomudur, bu nedenle valans kabuğunda dört elektrona sahiptir ve dört bitişik atomla bağlar oluşturarak kristal bir kafes oluşturur. Aşağıdaki şekil a'da bu kafes çizmi kolay olsun diye 2 boyutlu olarak gösterilmiştir ancak bu kafesin bir küp şeklinde olduğunu unutmamak gerekmektedir. Şekildeki çizgiler kovalent bağları göstermektedir. Silikon kendi başına zayıf bir iletkendir çünkü tüm elektronlar kovalent bağlara bağlıdır. Bununla birlikte, katkı atomları olarak adlandırılan küçük miktarlardaki safsızlıklar dikkatlice eklendiğinde daha iyi bir iletken haline gelir. Arsenik (As) gibi bir grup V katkı maddesi eklenirse, katkı atomlarının bağlarda yer almayan fazladan bir elektronu vardır. Elektron,  aşağıdaki şekil b'de gösterildiği gibi arkada bir iyonize katkı atomu (As +) bırakarak kafes etrafında kolayca hareket edebilir. Elektron negatif bir yük taşır, bu nedenle arseniğe n-tipi katkı maddesi diyoruz. Öte yandan, bor (B) gibi bir grup III katkı maddesi eklenirse, aşağıdaki şekil c'de gösterildiği gibi katkı atomlarında bir elektron eksiktir. Bu eksik elektrona delik denir. Komşu bir silikon atomundan gelen bir elektron, eksik bağı doldurmak için hareket ederek iyonize bir katkı atomu (B−) oluşturabilir ve komşu silikon atomunda bir delik bırakabilir. Benzer bir şekilde, delik kafes etrafında hareket edebilir. Delik, negatif yük eksikliğidir, bu nedenle pozitif yüklü bir parçacık gibi davranır. Bu nedenle bor'a p-tipi katkı maddesi diyoruz. Silikonun iletkenliği, katkı maddelerinin konsantrasyonuna bağlı olarak birçok büyüklük sırasına göre değiştiğinden, silikona yarı iletken denir.

![yarıiletken](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/30.png)

## 1.7.2 Diyot

P-tipi ve n-tipi silikon arasındaki bağlantıya diyot denir. Şekilde gösterildiği gibi p-tipi bölge anot ve n-tipi bölge katot olarak adlandırılır. Anot üzerindeki voltaj, katottaki voltajın üzerine çıktığında, diyot öne doğru eğilir ve akım, diyot boyunca anottan katoda akar. Ancak anot voltajı katottaki voltajdan daha düşük olduğunda, diyot ters yönlüdür ve hiçbir akım akmaz. Diyot sembolü sezgisel olarak akımın yalnızca bir yönde aktığını gösterir.

![diyot](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/31.png)

## 1.7.3 Kondansatör

Bir kondansatör, bir yalıtkanla ayrılmış iki iletkenden oluşur. İletkenlerden birine bir V voltajı uygulandığında, iletken Q elektrik yükünü biriktirir ve diğer iletken, zıt −Q yükünü biriktirir. Kondansatörün kapasitansı C, yükün voltaja oranıdır: C = Q / V. Kapasite, iletkenlerin boyutuyla orantılıdır ve aralarındaki mesafe ile ters orantılıdır. 

Kapasitans önemlidir çünkü bir iletkeni şarj etmek veya boşaltmak zaman ve enerji gerektirir. Daha fazla kapasitans, bir devrenin daha yavaş olacağı ve çalışması için daha fazla enerji gerektireceği anlamına gelir.

## 1.7.4 nMOS ve pMOS Transistörler

Bir MOSFET'i iletken ve yalıtkan katmanlardan oluşan bir goflete benzetebiliriz. Bu gofret, çapı yaklaşık 15 ila 30 cm olan ince yassı silikon katmanlardan oluşmaktadır. Gofrete benzetilen bu yapı başlanğıçta katkısızdır. Üretim, katkı maddelerinin silikona enjekte edildiği, ince silikon dioksit ve silikon filmlerinin büyütüldüğü ve metalin biriktirildiği bir dizi adımı içerir. Her adımda silikon gofret istenildiği şekilde desenlendirilir. 
Transistörler çok küçük(1 mikron <sup>2</sup>) olduğundan ve tüm silikon levha tek seferde işlenebildiğinden milyarlarca transistör üretmek oldukça ucuz olmaktadır. Üretim adımları tamamlandıktan sonra, silikon gofret chip adı verilen dikdörtgenler halinde kesilir. Milyarlarca transistör içeren chipler bir sonraki adımda metal bacaklara sahip plastik veya seramik bir pakete yerleştirilir.

MOSFET üç katmanlı sandiçe benzetilevbilir; en alt katmanda substrate adı verilen silikon bulunmaktadır. Bu katmanın üstünde yalıtkan bir silikon dioksit (SiO <sub>2</sub>) bulunur. En üstte ise kapı adı verilen iletken bir katman bulunmaktadır. Geneksel olarak, kapı  katmanı metalden yapılmaktadır. Dolayısıyla metal-oksit yarı-iletken MOSFET adını almaktadır. Modern üretim süreçleri, kapı için polikristalin silikon kullanır çünkü yüksek sıcaklıktaki üretim aşamalarına dayanıklıdır. Silikon dioksit daha çok cam olarak bilinir ve yarı iletken endüstrisinde genellikle oksit olarak adlandırılır. Metal oksit yarı iletken sandviç, dielektrik adı verilen ince bir yalıtkan oksit tabakasının metal ve yarı iletken plakaları ayırdığı bir kapasitör oluşturur.

MOSFET'lerin iki çeşidi vardır: nMOS ve pMOS (“n-moss” ve “p-moss” olarak telaffuz edilir).  Aşağıdaki şekil bir gofretin içinden kesilerek ve yandan bakılarak yapılan her bir türün enine kesitlerini göstermektedir. NMOS olarak adlandırılan n-tipi transistörler, kaynak ve drenaj adı verilen kapının bitişiğinde n-tipi katkı maddelerinin bölgelerine sahiptir ve bir p-tipi yarı iletken substrat üzerine inşa edilmiştir. PMOS transistörleri, n-tipi bir alt tabakadaki p-tipi kaynak ve boşaltma bölgelerinden oluşan tam tersidir.

![MOSFET](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/32.png)

Bir MOSFET, geçit voltajının kaynak ile tahliye arasındaki bağlantıyı AÇAN veya KAPATAN bir elektrik alanı oluşturduğu voltaj kontrollü bir anahtar gibi davranır. Alan etkili transistör terimi bu çalışma prensibinden gelir. Bir nMOS transistörün işleyişini keşfederek başlayalım.

Bir nMOS transistörün substratı normalde sistemdeki en düşük voltaj olan GND'ye bağlıdır. İlk olarak, aşağıdkai şekil (a) 'da gösterildiği gibi, kapının da 0 V'de olduğu durumu düşünün. Kaynak veya boşaltma ve alt tabaka arasındaki diyotlar, kaynak veya boşaltma voltajı negatif olmadığından ters eğimlidir. Bu nedenle, akımın kaynak ve boşaltma arasında akması için bir yol yoktur, bu nedenle transistör KAPALI'dır. Şimdi, aşağıdkai şekil (b) 'de gösterildiği gibi kapının VDD'ye ne zaman yükseltildiğini düşünün. Bir kapasitörün üst plakasına pozitif voltaj uygulandığında, üst plakada pozitif yük ve alt plakaya negatif yük çeken bir elektrik alanı oluşturur. Voltaj yeterince büyükse, kapının alt tarafına o kadar çok negatif yük çekilir ki, bölge p-tipinden etkin bir şekilde n-tipi haline gelmek için tersine çevrilir. Bu ters çevrilmiş bölgeye kanal denir. Artık transistör, n-tipi kaynaktan n-tipi kanaldan n-tipi drenaja kadar sürekli bir yola sahiptir, böylece elektronlar kaynaktan drenaja akabilir. Transistör AÇIK. Bir transistörü açmak için gereken kapı voltajına eşik voltajı Vt denir ve tipik olarak 0,3 ila 0,7 V arasındadır.

![MOSFET2](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/33.png)

pMOS transistörleri, Şekide gösterilen sembollerindeki balondan tahmin edilebileceği gibi, tam tersi şekilde çalışır. Substrat, VDD'ye bağlanır. Kapı da VDD'de olduğunda, pMOS transistörü KAPALI'dır. Kapı GND'de olduğunda, kanal p-tipine dönüşür ve pMOS transistörü AÇIK durumdadır.

![transistör](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/34.png)

Maalesef MOSFET'ler mükemmel anahtarlar değildir. Özellikle, nMOS transistörleri 0’ları iyi geçer ancak 1’leri kötü geçer. Spesifik olarak, bir nMOS transistörünün kapısı VDD'de olduğunda, drenaj yalnızca 0 ile VDD - Vt arasında sallanacaktır. Benzer şekilde, pMOS transistörleri 1’leri iyi geçer, ancak 0’ları zayıftır. Bununla birlikte, transistörleri yalnızca iyi modlarında kullanan mantık kapıları inşa etmenin mümkün olduğunu göreceğiz.

nMOS transistörleri bir p-tipi alt tabakaya ihtiyaç duyar ve pMOS transistörleri bir n-tipi alt tabakaya ihtiyaç duyar. Aynı çip üzerinde her iki transistör çeşidini oluşturmak için, üretim süreçleri tipik olarak bir p-tipi yonga plakası ile başlar, ardından pMOS transistörlerinin gitmesi gereken kuyular olarak adlandırılan n-tipi bölgeleri implante edin. Her iki transistör çeşidini sağlayan bu işlemlere Tamamlayıcı MOS veya CMOS denir. CMOS işlemleri, bugün üretilen tüm transistörlerin büyük çoğunluğunu oluşturmak için kullanılmaktadır.

Özetle, CMOS süreçleri bize yukarıdaki şekilde gösterildiği gibi iki tür elektrikle kontrol edilen anahtar verir. Kapıdaki (g) voltaj, kaynak (s) ile drenaj (d) arasındaki akım akışını düzenler. nMOS transistörleri, kapı 0 olduğunda KAPALI ve kapı 1 olduğunda AÇIK durumdadır. pMOS transistörleri tam tersidir: Kapı 0 olduğunda AÇIK ve kapı 1 olduğunda KAPALI.

## 1.7.5 CMOS(Complementary MOS) Not Kapısı

Aşağıdaki şekil, CMOS transistörlerle oluşturulmuş bir NOT geçidinin şemasını gösterir. Üçgen GND'yi ve düz çubuk VDD'yi gösterir; bu etiketler gelecekteki şemalardan çıkarılacaktır. NMOS transistörü N1, GND ve Y çıkışı arasına bağlanır. PMOS transistörü P1, VDD ve Y çıkışı arasına bağlanır. Her iki transistör kapısı A girişi tarafından kontrol edilir. 

![NOT](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/35.png)

A = 0 ise, N1 KAPALI ve P1 AÇIK. Bu nedenle Y, VDD'ye bağlanır ancak GND'ye bağlanmaz ve mantık 1'e çekilir. P1 iyi 1'i geçer. A = 1 ise, N1 AÇIK ve P1 KAPALI ve Y mantık 0'a çekilir. N1 kararlı bir 0'a geçer. Doğruluk tablosu incelendiğinde, devrenin gerçekten bir NOT geçidi olduğunu görüyoruz.

## 1.7.6 Diğer CMOS Lojik Kapılar

Aşağıdaki şekil, iki girişli bir NAND geçidinin şemasını göstermektedir. Şematik diyagramlarda, teller her zaman üç yollu bağlantılarda birleştirilir. Dört yönlü kavşaklarda, yalnızca bir nokta gösteriliyorsa birleştirilirler. NMOS transistörleri N1 ve N2 seri olarak bağlanmıştır; Çıkışı GND'ye çekmek için her iki nMOS transistörü de AÇIK olmalıdır. PMOS transistörleri P1 ve P2 paraleldir; Çıkışı V <sub>DD</sub>'ye çekmek için yalnızca bir pMOS transistör AÇIK olmalıdır. Aşağıdaki tabloda, kapının bir NAND olarak işlev gördüğünü göstererek, aşağı çekme ve yukarı çekme ağlarının çalışmasını ve çıktının durumunu listeler. Örneğin, A = 1 ve B = 0 olduğunda, N1 AÇIK, ancak N2 KAPALI, Y'den GND'ye giden yolu bloke ediyor. P1 KAPALI, ancak P2 AÇIK, V <sub>DD</sub>'den Y'ye bir yol oluşturuyor. Bu nedenle, Y 1'e çekiliyor.

![NAND](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/36.png)

![TabloNAND](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/37.png)

Aşağıdaki şekil , NOT, NAND veya NOR gibi herhangi bir ters çevirici mantık geçidi oluşturmak için kullanılan genel formu gösterir. nMOS transistörleri, 0’ları geçirmekte iyidir, bu nedenle, çıkışı 0’a çekmek için çıkış ile GND arasına aşağıya açılan bir nMOS transistör ağı yerleştirilir. pMOS transistörleri 1’leri geçirmekte iyidir, bu nedenle çıkışı 1’e kadar çekmek için çıkış ve V <sub>DD</sub> arasına bir yukarı çekmeli pMOS transistör ağı yerleştirilir. Ağlar, seri veya paralel transistörlerden oluşabilir. Transistörler paralel olduğunda, transistörlerden biri AÇIK ise ağ AÇIK konumdadır. Transistörler seri haldeyken, ağ yalnızca her iki transistör de AÇIK ise AÇIK konumdadır. Giriş telindeki eğik çizgi, geçidin birden fazla giriş alabileceğini gösterir.

Hem yukarı çekme hem de aşağı çekme ağları aynı anda AÇIK olsaydı, V <sub>DD</sub> ve GND arasında bir kısa devre olurdu. Geçidin çıkışı yasak bölgede olabilir ve transistörler muhtemelen yanmaya yetecek kadar büyük miktarda güç tüketebilir. Öte yandan, hem yukarı çekme hem de aşağı çekme ağları aynı anda KAPALI olsaydı, çıkış ne V <sub>DD</sub>'ye ne de GND'ye bağlanırdı. Çıktının yüzdüğünü söylüyoruz. Değeri yine tanımsızdır. Yüzen çıktılar genellikle istenmeyen bir durumdur, ancak ileride bu durumun zaman zaman tasarımcının avantajına nasıl kullanılabileceklerini göreceğiz.

Düzgün çalışan bir mantık geçidinde, herhangi bir zamanda ağlardan biri AÇIK ve diğeri KAPALI olmalıdır, böylece çıkış YÜKSEK veya DÜŞÜK çekilir ancak kısa devre veya yüzer olmaz. Bunu, iletim tamamlayıcıları kuralını kullanarak garanti edebiliriz. NMOS transistörleri seri olduğunda, pMOS transistörleri paralel olmalıdır. NMOS transistörleri paralel olduğunda, pMOS transistörleri seri olmalıdır.

Örnek 1.20 CMOS transistörlerini kullanarak üç girişli bir NAND geçidi için bir şema çizin.

Çözüm: NAND geçidi, yalnızca üç girişin tümü 1 olduğunda bir 0 çıkışı üretmelidir. Bu nedenle, aşağı açılır ağda seri olarak üç nMOS transistörü olmalıdır. İletim tamamlayıcılar kuralına göre, pMOS transistörleri paralel olmalıdır. Böyle bir kapı aşağıdaki şekilde gösterilmektedir; doğru doğruluk tablosuna sahip olup olmadığını kontrol ederek işlevi doğrulayabilirsiniz.

![20NAND](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/38.png)

Örnek 1.21 CMOS transistörlerini kullanarak iki girişli bir NOR geçidi için bir şema çizin.

Çözüm: Her iki giriş 1 ise NOR geçidi 0 çıkış üretmelidir. Bu nedenle, aşağı açılır ağın paralel olarak iki nMOS transistörüne sahip olması gerekir. İletim tamamlayıcılar kuralına göre, pMOS transistörleri seri halinde olmalıdır. Böyle bir kapı aşağıdaki şekilde gösterilmektedir.

![21NOR](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/39.png)

Örnek 1.22 İki girişli bir AND geçidi için bir şema çizin.

Çözüm: Tek bir CMOS geçidi ile bir AND geçidi oluşturmak imkansızdır. Ancak, NAND ve NOT kapıları inşa etmek kolaydır. Bu nedenle, CMOS transistörleri kullanarak bir AND geçidi oluşturmanın en iyi yolu, aşağıdaki şekilde gösterildiği gibi bir NAND ve ardından bir NOT kullanmaktır.

![22AND](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/40.png)

## 1.7.7 İletim Kapıları
Zaman zaman tasarımcılar, hem 0 hem de 1 geçebilen ideal bir anahtar kullanmayı uygun buluyor. NMOS transistörlerinin 0'ı geçmekte iyi olduğunu ve pMOS transistörlerinin 1'i geçmekte iyi olduğunu hatırlayın, bu nedenle ikisinin paralel kombinasyonu her iki değeri de iyi geçirir. Aşağıdaki şekil , iletim kapısı veya geçiş kapısı adı verilen böyle bir devreyi göstermektedir. Anahtarın iki tarafı A ve B olarak adlandırılır çünkü bir anahtar çift yönlüdür ve tercih edilen giriş veya çıkış tarafına sahip değildir. Kontrol sinyalleri enable, EN ve EN’ olarak adlandırılır. EN = 0 ve EN’ = 1 olduğunda, her iki transistör de KAPALI. Dolayısıyla, iletim kapısı KAPALI veya devre dışıdır, bu nedenle A ve B bağlı değildir. EN = 1 ve EN’ = 0 olduğunda, iletim kapısı AÇIK veya etkindir ve herhangi bir mantık değeri A ile B arasında akabilir.

![iletimkapi](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/41.png)

## 1.7.8 Sözde-nMOS Mantığı
Bir N girişli CMOS NOR geçidi, paralel olarak N nMOS transistörleri ve seri olarak N pMOS transistörlerini kullanır. Seri transistörler paralel transistörlerden daha yavaştır, tıpkı serideki dirençlerin paralel dirençlerden daha fazla dirence sahip olması gibi. Dahası, pMOS transistörleri nMOS transistörlerinden daha yavaştır çünkü delikler silikon kafes etrafında elektronlar kadar hızlı hareket edemez. Bu nedenle paralel nMOS transistörleri hızlıdır ve seri pMOS transistörleri, özellikle birçoğu seri olduğunda yavaştır.

Sözde-nMOS mantığı, yavaş pMOS transistör yığınını, aşağıdaki şekilde gösterildiği gibi her zaman AÇIK olan tek bir zayıf pMOS transistör ile değiştirir. Bu pMOS transistörüne genellikle zayıf çekme denir. PMOS transistörünün fiziksel boyutları, pMOS transistörünün Y YÜKSEK çıkışını zayıf bir şekilde çekeceği şekilde seçilir - yani, nMOS transistörlerinden hiçbiri AÇIK değilse. Ancak herhangi bir nMOS transistörü AÇIK ise, zayıf yukarı çekmeyi etkisiz hale getirir ve mantık 0 üretmek için Y'yi GND'ye yeterince yaklaştırır.

![nMOS](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/42.png)

Sözde nMOS mantığının avantajı, birçok girişle hızlı NOR geçitleri oluşturmak için kullanılabilmesidir. Örneğin, aşağıdaki şekil, sözde nMOS dört girişli NOR gösterir. Sözde nMOS geçitleri, ileride tartışılan belirli bellek ve mantık dizileri için kullanışlıdır. Dezavantajı, çıkış DÜŞÜK olduğunda VDD ve GND arasında bir kısa devre olmasıdır; zayıf pMOS ve nMOS transistörlerinin her ikisi de AÇIK. Kısa devre sürekli güç çeker, bu nedenle sözde-nMOS mantığı idareli kullanılmalıdır.

![nMOS4](https://raw.githubusercontent.com/suhap/sayisaltasarim/master/resource/43.png)

Sözde nMOS kapıları adını, üretim süreçlerinin yalnızca nMOS transistörlere sahip olduğu 1970'lerden almıştır. HIGH çıkışını çekmek için zayıf bir nMOS transistörü kullanıldı çünkü pMOS transistörleri mevcut değildi.

# 8 Güç Tüketimi
Güç tüketimi, birim zamanda kullanılan enerji miktarıdır. Dijital sistemlerde güç tüketimi büyük önem taşımaktadır. Cep telefonları ve dizüstü bilgisayarlar gibi taşınabilir sistemlerin pil ömrü, güç tüketimiyle sınırlıdır. Güç, prize takılı sistemler için de önemlidir, çünkü elektrik maliyetlidir ve sistem çok fazla güç çekerse aşırı ısınır.

Dijital sistemler hem dinamik hem de statik güç çekerler. Dinamik güç, sinyaller 0 ile 1 arasında değişirken kapasitansı şarj etmek için kullanılan güçtür. Statik güç, sinyaller değişmediğinde ve sistem boştayken bile kullanılan güçtür.

Mantık kapıları ve bunları bağlayan teller kapasitansa sahiptir. Bir kapasitans C'yi voltaj V <sub>DD</sub>'ye şarj etmek için güç kaynağından çekilen enerji CV <sub>DD</sub> <sup>2</sup>'dir. Kapasitör üzerindeki voltaj f frekansında (yani saniyede f kez) anahtarlanırsa, kapasitörü f / 2 kez şarj eder ve saniyede f / 2 kez boşaltır. Boşaltma güç kaynağından enerji çekmez, bu nedenle dinamik güç tüketimi

Dinamik = 1/2 CV <sub>DD</sub> <sup>2</sup> f 

Elektrik sistemleri boştayken bile bir miktar akım çekerler. Transistörler KAPALI olduğunda, az miktarda akım sızdırırlar. Bölüm 1.7.8'de tartışılan sözde-nMOS geçidi gibi bazı devreler, V <sub>DD</sub>'den GND'ye akımın sürekli aktığı bir yola sahiptir. Toplam statik akım, Idd, aynı zamanda, kaçak akım veya Vdd ile GND arasında akan durgun besleme akımı olarak da adlandırılır. Statik güç tüketimi, bu statik akımla orantılıdır:

P <sub>static</sub> = I <sub>DD</sub> V <sub>dd</sub>

Örnek 1.23 Belirli bir cep telefonunun 6 watt-saatlik (W-hr) bir pili vardır ve 1,2 V'ta çalışır. Kullanıldığında, cep telefonunun 300 MHz'de çalıştığını ve herhangi bir zamanda çip anahtarlamasındaki ortalama kapasitans miktarının 10 nF (10 <sup>-8</sup> Farad) olduğunu varsayalım. Kullanımdayken, anteninden 3 W güç de yayınlar. Telefon kullanımda değilken, sinyal işleme kapatıldığı için dinamik güç neredeyse sıfıra düşer. Ancak telefon, kullanımda olsun veya olmasın 40 mA hareketsiz akım da çekiyor. Telefonun pil ömrünü (a) kullanılmıyorsa ve (b) sürekli kullanılıyorsa belirleyin.

Çözüm: Statik güç P <sub>statik</sub> = (0,040 A) (1,2 V) = 48 mW'dir.
(a) Telefon kullanılmıyorsa, bu tek güç tüketimidir, dolayısıyla pil ömrü (6 Whr) / (0,048 W) = 125 saattir (yaklaşık 5 gün).
(b) Telefon kullanılıyorsa, dinamik güç P <sub>dinamik</sub> = (0,5) (10 <sup>−8</sup> F) (1,2 V) <sup>2</sup> (3 × 10 <sup>8</sup> Hz) = 2,16 W.

Statik ve yayın gücü ile birlikte toplam aktif güç 2,16 W + 0,048 W + 3 W = 5,2 W, dolayısıyla pil ömrü 6 W-sa / 5,2 W = 1,15 saattir. Bu örnek, bir cep telefonunun gerçek işleyişini biraz fazla basitleştiriyor, ancak güç tüketiminin temel fikirlerini gösteriyor.





