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

Burada kaldım

Çizimleri basitleştirmek için, genellikle bir çizgi ve yanında bir sayı olan tek bir çizgi, birden çok sinyalden oluşan bir yolu belirtmek için kullanırız. Numara, veriyolunda kaç sinyal olduğunu belirtir. Örneğin, Şekil sağ(a), üç giriş ve iki çıkış içeren bir birleşimsel mantık bloğunu temsil eder. Bit sayısı önemsizse veya bağlamdan anlaşılırsa, eğik çizgi sayı olmadan gösterilebilir. Şekil sağ(b), bir bloktan ikinci bloğa girişler olarak hizmet eden keyfi sayıda çıktıya sahip iki kombinasyonel mantık bloğunu gösterir.

