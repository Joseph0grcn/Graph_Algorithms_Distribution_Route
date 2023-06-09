
<h1>Graph_Algorithms_Distribution_Route</h1>
seçilen kordinatlarda ana lojistik merkez seçiminin yapılması ve harita üzerinde bu noktaların gösterilmesinden oluşan bir projedir

<h2>neden böyle bir yol tercih ettik</h2>
<p> 
Yakın zamanda meydana gelen deprem felaketinden sonra karşılaştığımız lojistik sorunları inceledik.
olabildiğince fazla yardım edilmeye çalışılsada deprem nedeniyle yolların kapanması şehir dışından yardımların şehir içine girmesine engel olmuştur.
bizde bunlara nasıl bir çözüm bulabilceğimizi düşündük.
seçtiğimiz lokasyonlar park, bahçe, stadyum, ve açıklık alanlardan oluşmaktadır.
bu yerleri seçme amacımız kargo helikopterlerinin direkt olarak iniş yapabilcekleri yada yapabilmeleri için az bir uğraş ile inilebilecek alanlara dönüştürülebilecek yerler olabilmesinden dolayıdır.
seçilen alanlardan bizim önerdiğimiz alan şehir dışından gelen yardımların ana lojistik depolama alanı yapıldıktan sonra yardımların kargo helikopterleriyle buraya düzenli bir şekilde istiflenmesi yapılacaktır. 
diğer alanlarında insanların geçici olarak kalabilceği ve ihtiyaca göre ana lojistik merkezden ihtiyaçların taşınıp dağıtılabilceği yerlere dönüştürülecektir.
kısaca özetlemek gerekirse 
kargo helikopteri şehir dışından gelen yardımları ana lojistik merkeze taşıyacak ve şehir içindeki daha küçük taşımaları lokasyonlar arası daha minimal araçlarla daha seri bir şekilde taşınacaktır.
<p>
<h1>Bu uygulama nedir</h1>
Bu uygulamada, bir dağıtım rotası planlaması için tasarlanmış, c#, HTML, CSS ve JavaScript dilleri kullanılarak oluşturulmuştur.

Uygulamada Leaflet isimli bir JavaScript kütüphanesi kullanılarak bir harita görüntülenmektedir. Harita, OpenStreetMap verileri kullanılarak oluşturulur. 
Haritanın zoom ve pan özellikleri sayesinde, kullanıcılar haritayı istedikleri şekilde görüntüleyebilirler.
Dağıtım yapılacak olan yerlerin koordinatları ve ihtiyaç duyulan malzemelerin listesi locations adlı bir JavaScript değişkeni içerisinde saklanmaktadır.
stock adlı bir başka JavaScript değişkeni de, depoda bulunan malzemelerin listesini tutar.

Ayrıca, getAddress adlı bir fonksiyon kullanarak, bir koordinatın adresini alır.
Bu fonksiyon, OpenStreetMap API'sini kullanarak bir GET isteği gönderir ve isteğin cevabında yer alan verileri alarak, koordinatın adresini döndürür.
Buradan dönen lokasyonlar dijksra's algoritmasında main metotunun içinde bulunan 'kordinatlar' çok boyutlu dizisine girilir. 


 haversineDistance adlı bir fonksiyon kullanarak, iki koordinat arasındaki haversine mesafesini hesaplar.
 Bu fonksiyon, birinci koordinatın enlem ve boylam değerleri ile ikinci koordinatın enlem ve boylam değerleri arasındaki mesafeyi hesaplayarak, mesafeyi kilometre cinsinden döndürür.

Dijkstra adlı bir fonksiyon kullanarak, Dijkstra algoritmasını kullanarak bir ağırlıklı graf üzerinde en kısa yolu bulur.
Bu fonksiyon, bir graf matrisi ve bir başlangıç düğümü alır. Graf matrisindeki her eleman, iki düğüm arasındaki mesafeyi gösterir.
Fonksiyon, graf matrisindeki en kısa yolu bulmak için Dijkstra algoritmasını kullanır ve en kısa yolu ve düğümleri tutan bir dizi döndürür.

 distributeStock adlı bir fonksiyon kullanarak, depodaki malzemeleri yerlere dağıtmak için en kısa yolu kullanır.
 Bu fonksiyon, depodaki malzemelerin listesini, dağıtım yapılacak olan yerlerin listesini ve en kısa yolu alır.
 Fonksiyon, malzemelerin belirtilen öncelik sırasına göre dağıtımını yaparak, dağıtım planını bir dizi şeklinde döndürür.

Polyline adlı bir nesne oluşturarak en kısa rotayı çizer. Ayrıca, rota uzunluğu ve tahmini süre bilgilerini hesaplar ve sayfada gösterir.
Sayfa, farklı fonksiyonlar aracılığıyla malzeme dağıtımını simüle ederek, bir depodan, farklı lokasyonlara malzeme taşıma senaryolarını test edebilir.
Sayfa, kullanıcıların malzeme dağıtımına ilişkin verileri girerek, en kısa rotayı ve bu rotada malzemelerin hangi lokasyona hangi sırayla dağıtılacağına ilişkin bir plan oluşturmalarına olanak tanır.

Bu Senaryoda, JavaScript dilinde yazılmış olan bazı algoritmaları ve kütüphaneleri kullanarak bir uygulama geliştirmek için bir örnek sunar.
Ayrıca, bu algoritmaların ve kütüphanelerin nasıl kullanılacağını göstererek, bu tarz uygulamaların nasıl tasarlanabileceği konusunda bir fikir verir.

<h2>kullanımı</h2>
Dagitim_Rotasi.html internet uzantısı üzerinden lokasyonlar görülebilir. buradan alınan lokasyonlar
Program.cs dosyasındaki lokasyonlar kısmına girilip çalıştırıldığında uzaklıklar ve ağırlıklarla birlikte hesaplanıp Consol üzerinden olası bütün uzaklıklar gösterilip consolun son kısmında 
yeşil yazıyla birlikte tavsiye edilen ana lojistik merkez ve bu lojistik merkez seçildiğinde diğer lokasyonlara ulaşmak için gerekli toplam mesafe gösterilecektir.

