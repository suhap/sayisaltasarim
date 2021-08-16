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



