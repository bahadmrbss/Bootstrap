# BOOTSTRAP

## KURULUMU

Bootstrap i html sayfamıza kurmak için, bootstrap in sayfasına gelip sayfada belirtilen kurulum kodunu kopyalayıp kendi sayfamıza dahil etmemiz yeterli olacaktır. Daha fazla bilgi için [tıklayınız](https://getbootstrap.com/docs/5.3/getting-started/introduction/).

## 12'lik Izgara(Grid) Sistemini Anlamak

Bootstrap, sayfa düzeni (layout) oluşturmak için, CSS flexbox ile oluşturulmuş ızgara (grid) sistemini kullanmaktadır.

Bootstrap ızgara sistemi 3 ana yapıdan oluşur:

1- Kapsayıcı (.container)

2- Satırlar (.row)

3- Kolonlar (col-\*) (Örnek: .col-md-8)

Her bir sütun, 12 kolondan meydana gelmekte ve 12'lik Grid sistemi oluşturmaktadır. 12'lik ızgara sisteminde, kolon sayısı varyasyonları ile istenildiği gibi tasarım yapılabilmektedir.

Her bir sayfayı 12 dikey parçadan olduğunu düşünürsek genelde sayfalar 12'lik yapıdan oluşur. Container yani ana tutucu dediğimiz bizim sayfada gördüğümüz genel yapının 12 parçadan oluştuğunu düşünürsek bu yapıyı 12 parçaya ayırmak için "row" sistemini kullanıyoruz yani satırları. 12 lik yapının içerisinde kaç tane kolon kullanacağımız belirtmek içn de "col" u kullanıyoruz.
Örnek:

```
 <div class="row">
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
    <div class="col">Kolon</div>
 </div>  ---> bu tek satırlık 12 parça oluşturur.
```

```
<div class="row">
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
    <div class="col-2">Kolon</div>
</div>  ---> bu 2 satırlık 6 adet parça oluşturur.
```

```
<div class="row">
    <div class="col-3">Kolon</div>
    <div class="col-3">Kolon</div>
    <div class="col-3">Kolon</div>
    <div class="col-3">Kolon</div>
</div>  ---> bu 3 satırlık 4 adet kolon oluşturur.
```

### EŞİT OLMAYAN KOLONLAR

Kolon sayılarının 12'ye tamamlanma zorunluluğu yoktur. Tasarıma göre istenilen sayıda kolonlar oluşturulabilir ve istenilen yerlerde boşluk bırakılabilir.

1 adet 2'li kolon (.col-[sınıfAdı]-2) ile 1 adet 10'lu kolon (.col-[sınıfAdı]-10) ya da 1 adet 8'li kolon (.col-[sınıfAdı]-8) ile 1 adet 4'lü kolon (.col-[sınıfAdı]-4) 12'ye tamamlanabilir.

Tek bir adet 8'li kolon (.col-[sınıfAdı]-8), tek bir adet 6'lı kolon (.col-[sınıfAdı]-6) ya da 1 adet 4'lü kolon (.col-[sınıfAdı]-4) ile 1 adet 5'li kolon (.col-[sınıfAdı]-5) kolon 12'ye tamamlanmadan bıraklabilir. Böylece eksik bırakılan kolon değeri kadar yan tarafta boşluk kalmış olur.

Verilen kolon değerlerinin toplamı 12'den fazla olması durumunda son kolon bloğu bozmayacağı için alt tarafa geçer.

- Örneğin; 1 adet 8'li kolondan sonra 1 adet 6'lı kolon değeri verilir ise 8 + 6 = 14 toplam kolon sayısı 12'den büyük olacağı için 6'lı kolon 8'li kolonun altına geçer.

```
<div class="row">
    <div class="col-2">2 Kolon</div>
    <div class="col-10">10 Kolon</div>
</div>  --> önce 2 kolonluk bir kutucuk, yanına 10 kolonluk bir kutucuk gelir.
```

```
<div class="row">
    <div class="col-8">8 Kolon</div>
    <div class="col-4">4 Kolon</div>
</div>  --> önce 2 kolonluk bir kutucuk, yanına 10 kolonluk bir kutucuk gelir.
```

```
<div class="row">
    <div class="col-8">8 Kolon</div>
    <div class="col-6">6 Kolon</div>
</div>  --> sığmadığı için 6 numaralı kolon 8 numaralı kolonun altına geçer.
```

Kolonların arasında da boşluk bırakmak mümkün. Bunun için col sınıfının yanına öntanımlı margin ve margin yönünü (ml-auto gibi) belirten bir sınıf adı daha eklenmelidir. Kolonun solunda boşluk bırakmak için margin (m) left (l) yani ml-auto sınıfı eklemeli, aynı şekilde sağ tarfında boşluk bırakılmak istenirse margin (m) right (r) yani mr-auto sınıfı eklemelidir.

- Örneğin; col-4 mr-auto sınıfı olan bir kolonun sağ tarafında, col-4 ml-auto sınıfı ise kolonun solunda boşluk bırakır.

```
<div class="row">
    <div class="col-4 mr-auto">4 Kolon</div>
    <div class="col-5">5 Kolon</div>
</div>  --> 4 numaralı kolonun sağına boşluk bırakır.

<div class="row">
    <div class="col-4">4 Kolon</div>
    <div class="col-5 ml-auto">5 Kolon</div>
</div>  --> 5 numaralı kolonun soluna boşluk bırakır.
```

![Örnek 1](örnek1.png)

## KOLONLARIN SIRALANMASI

Öntanımlı order-[sıra numarası] sınıfını ekleyerek kolonları sıralayabiliriz.

- Örneğin; col-3 order-3 üç kolonluk bölümü üçüncü sıraya yerleştirecektir.

```
<div class="row">
    <div class="col-3 order-3">3 Kolon</div>
    <div class="col-4 order-2">4 Kolon</div>
    <div class="col order-1">5 Kolon</div>
</div>
```

![Örnek 2](örnek2.png)

## İÇ İÇE IZGARA SİSTEMİ

Bir satırdaki (row) kolonun (col) içine başka bir satır eklenerek yine kolonlara bölünebilir.

Örneğin; 4'lük bir kolon (.col-[sınıfAdı]-4) ile 8'lik bir kolondan (.col-[sınıfAdı]-8) oluşan satırdaki 8'lik kolonun içinde yeni bir satır (row) eklenerek 2 adet 6'lık kolon (.col-[sınıfAdı]-6) oluşturulabilir.

```
<div class="row">
    <div class="col-4">4 Kolon</div>
    <div class="col-8">
        8 Kolon
        <div class="row">
            <div class="col-6">6 Kolon</div>
            <div class="col-6">6 Kolon</div>
        </div>
    </div>
</div>
```

![Örnek 3](örnek3.png)

## ROW VE COLUMN YAPISI

Row(satır), column(sütun) sistemi Bootstrap'in grid system(ızgara sistemi) denilen düzenini oluşturuyor. Grid system ile bir web sayfası 12 adet sütuna bölünmüş ve sayfanın içeriği bu sütunların boyutlarına göre düzenlenmiş diyebiliriz. Genel olarak göstermek gerekirse aşağıdaki resim örnek bir sayfanın 12 adet sütuna bölündüğünde hangi içeriğin hangi sütunlar boyutunda olacağını, aralarındaki boşlukları göstermektedir.

![Örnek 4](örnek4.png)

İçeriklerimizin genişliğini sütun yapısına göre belirliyoruz demiştik. Yani sayfamızda paylaşmak istediğimiz bir yazı, 12 sütunun 3 tanesini kapsayacak genişlikte olsun, kalan 9 sütun ise bir resim için ayrılmış olsun. Peki içeriklerin uzunluğunu neye göre belirliyoruz? İşte burada da satırları kullanıyoruz. Sayfamızı yukardan aşağıya satırlara bölüyoruz ve her satırın içerisinde ayrı ayrı sütun sayısı, boyutu belirleyebiliyoruz. Bu şekilde satırları ve sütunları bir container içerisinde kullandığımızda grid system uygulamış oluyoruz. Kafa karıştırıcı gibi gözükebilir ancak aşağıdaki resmi incelediğimizde her şey çok net anlaşılacaktır.

![Örnek 5](örnek5.png)

- İlk Satır Birbirine Eşit Boyutta 12 Adet Sütundan

- İkinci Satır Birbirine Eşit Boyutta 3 Adet Sütundan

- Üçüncü Satır 2 Farklı Boyutta Sütundan

- Dördüncü Satır 2 Eşit Boyutta Sütundan

- Beşinci Satır İse Tek Bir Sütundan Oluşmaktadır.

Görüldüğü gibi 12 adet sütun yapısını istediğimiz biçimde birleştirerek, ayırarak satırlar ile birlikte kullanarak tasarımımızı yapabiliriz.

Son olarak ise grid yapısını oluşturmak için nasıl bir kod yapısı kullanmamız gerektiğini basit bir örnek ile anlamaya çalışalım.

![Örnek 6](örnek6.png)

- Bu resimde gördüğümüz 2 satırdan oluşan grid yapısını aşağıdaki kod ile oluşturabiliriz.

```
<div class="container">
  <div class="row">
    <div class="col">
      1 of 2
    </div>
    <div class="col">
      2 of 2
    </div>
  </div>
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col">
      2 of 3
    </div>
    <div class="col">
      3 of 3
    </div>
  </div>
</div>
```

div HTML tag'lerine class="row" veya class="col" sınıfları vererek bu tag'lerin ne amaçla kullanılacağını belirttik. Ayrıca dikkat ederseniz bu grid bir class="container" içerisinde bulunmakta.

## BOOTSTRAP - EKRAN ÇÖZÜNÜRLÜĞÜ / CİHAZ DUYARLI (RESPONSİVE) KOLON YAPISI KULLANIMLARI

## GRİD OPTİONS

[İlgili Video](https://youtu.be/9_mdnDE5UnA)

## Bootstrap Renk Strandartları, Tipografi, Margin ve Padding Kullanımı

[İlgili Video](https://academy.patika.dev/tr/courses/bootstrap/bootstrap-renk-strandartlari,-tipgrafi,-margin-ve-padding-kullanimi)

## DİSPLAY ÖZELLİKLERİ

### Bootstrap’te Display Özellikleri ile Responsive Yapıya Göre İstenilen Blokların Gösterilmesi / Gizlenmesi

Bootstrap 5’teki display özellikleri sayesinde, CSS’teki display özelliği daha kolay bir kullanıma kavuşuyor.

CSS’teki display özelliğini kısaca hatırlayalım.

```
display: none;
/* Elemanı sayfadan tamamen kaldırır */

display: block;
/* Elemente blok seviyesi elementlerin (<div>, <header>, <h1> gibi) görünüm özelliğini kazandırır. */

display: inline;
/* Elemente <span>, <a>, <img> elementlerinde olduğu gibi, satır içi yerleşim özelliği kazandırır. Element satırı tamamen kaplamaz, içeriği kadar yer kaplar. */

display: inline-block;
/* Elementleri satır içi element gibi yan yana dizmek için kullanılır. */

display: flex;
/* Element inline element gibi davranır ve bunun yanında flexbox modeline uygun görünüme sahip olur. */

display: grid;
/* Element, blok level bir element gibi davranır ve grid model görünümüne uygun davranır. */
```

Bootstrap display özelliği sayesinde çok daha kolay bir şekilde responsive uyumlu hazır grid sistemler inşa edebiliriz. Bunun için oluşturacağımız element için class değerine d.{value} girmemiz yeterlidir.

{value} değeri aşağıdakilerden herhangi biri olabilir:

```
none
inline
inline-block
block
grid
table
table-cell
table-row
flex
inline-flex
```

### Breakpoint’ler

Bootstrap’te ekran boyutları için hazır tanımlamalar bulunmaktadır. Bu tanımlamalara göre elementlerin görünürlüğünü açık/kapalı olarak class tag’inde belirtebiliriz. Bu sayede responsive uyumlu dinamik bir görünüm elde ederiz:

#### Alıştırma

Şimdi, Bootstrap özelliklerini kullanarak 5 adet h1 oluşturalım ve bu h1 elementlerinin display özelliklerini ayarlayalım.

Bootstrap display class’larında ilk belirtilen değer aksi belirtilmedikçe diğer ekran boyutlarında da geçerli olmaktadır. Örneğin XS (mobil) boyutu için görünür olmayan bir element ekstra bir tanım yapılmadıkça diğer ekran boyutlarında da görünür olmayacaktır. XS boyutunda d-none (CSS’teki display:none; ile eşdeğer) olarak tanımlanmış bir elementi MD (Laptop) boyutunda ekranda görünür hale getirmek için

- İlk elementimiz mobil yani “xs” boyutu için görünür olmalı. Bunun için class tag’ine d-block yazmamız gerekiyor ve bu da CSS’teki display:block; satırına eşdeğer. Fakat bir sonraki boyut ve sonrasında elementi gizlemek için display:none; olarak ayarlamamız gerekiyor. Bunun için Bootstrap’te sonraki boyut olan “sm” boyutu için d-sm-none tanımlamasını yapıyoruz. Böylece sm ve daha sonraki ekran boyutları için display:none tanımlamasını yapmış oluyoruz:

```
<h1 class="d-block d-sm-none bg-warning p-5 text-white mx-auto">XS - Birinci Element - Mobil Görünüm</h1>
```

- Bir sonraki h1 elementi için ise sadece sm ekran boyutunda görünür olmasını istiyoruz. Bunun için standart olarak d-none özelliği tanımlayıp ardından sm ekran boyutu için d-sm-block tanımlaması yapıyoruz. Sonraki ekran boyutları için elementi gizlemenin yolu ise, bir sonraki ekran boyutunda yine display:none tanımlaması yapmak. Bunun için d-md-none yazabiliriz:

```
<h1 class="d-none d-sm-block d-md-none bg-primary p-5 text-white mx-auto">SM - İkinci Element - Tablet Görünüm</h1>
```

- Sonraki h1 elementinde sadece md ekran boyutunda görünür olması için varsayılan olarak d-none tanımlaması yapıp ardından d-md-block yazmalıyız. Sonraki ekran boyutlarında görünürlüğü kapatmak için ise d-lg-none yazmamız yeterli olacaktır:

```
<h1 class="d-none d-md-block d-lg-none bg-success p-5 text-white mx-auto">MD - Üçüncü Element - Laptop Görünüm</h1>
```

- Sonraki h1 elementinde önce d-none, ardından lg ekran boyutunda görünür hale getirmek için d—lg-block, sonraki ekran boyutlarında gizli hale getirmek için ise d-xl-none yazabiliriz:

```
 <h1 class="d-none d-lg-block d-xl-none bg-danger p-5 text-white mx-auto">LG - Dördüncü Element - Normal Ekran Görünüm</h1>
```

- Son ekran boyutunda görünmesini istediğimiz h1 elementini ise varsayılan olarak d-none şeklinde ayarlıyoruz. Ardından d-xl-block yazmamız yeterli olacaktır. Bu ekrandan daha büyük tanımlı bir ekran bulunmadığı için, başka bir tanımlama yapmamıza gerek yoktur:

```
<h1 class="d-none d-xl-block bg-info p-5 text-white mx-auto">XL - Beşinci Element - Büyük Ekran Görünüm</h1>
```

## OFFSET KULLANIMI

Offset container daki yapımızda değişiklik yapmamıza ve yeriyle oynamamızı sağlar. örneğin 6 sütunluk bir yapı sola dayalı bir şekilde duruyorsa bunu 3 sütun sağda ve 3 sütun sola boş kalacak şekilde kaydırarak container ımızı ortalayabiliriz.

Örnek kullanım için "offset.html" sayfasında footer kısmına bakabilrsin.

## Bootstrap Sıralama Özelliklerini Kullanarak Responsive Yapıya Göre Tepklierin Düzenlenmesi

Bootstrap'de sıralama özelliği(order), içeriklerin HTML'de yazılan sırayla değil (kodlar yukarıdan aşağı okunarak sıralanır) bizim belirlediğimiz sıraya göre sıralamamızı sağlayan bir kavramdır. Genellikle responsive yapılar oluştururken kullanılır. Kullanırken kapsayıcı div'imizin display:flex classının yani 'd-flex' olması gerekmektedir, kapsayıcı div'in içinde en fazla 5 tane içeriği sıralayabileceğimizi unutmamamız gerekiyor.

Bir örnek ile order yapısına başlayalım:

Örneğin xl genişliğinde çalışıyorsunuz ve web siteniz 3 parçadan oluşuyor, fakat siz sm genişliğinde ki ekranlarda;1. içeriğinizin ilk gözükmesini değil son gözükmesini istiyorsunuz. 3.içeriğinizin ise ilk görülmesini istiyorsunuz. Yani aslında;

Web sitenizin xl görüntüsü bu şekilde olsun istiyorsunuz fakat sm genişliğinde ise aşağıdaki görüntü oluşsun istiyorsunuz

Tam olarak Order kavramı bu işlemi yapmanıza yardımcı oluyor peki nasıl?
´´´

<div class="d-flex">
  <div class="p-2 ">1. İçeriğimiz</div>
  <div class="p-2 ">2. İçeriğimiz</div>
  <div class="p-2">3. İçeriğimiz</div>
</div>
´´´
Bu bizim sitemizin genel içeriğini oluşturan kodlarımız. Fakat biz sm ekranlarda dizilimi değiştirmek istiyoruz o zaman yapmamız gereken tek şey:
´´´
<div class="d-flex">
  <div class="order-sm-3 p-2">1. İçeriğimiz</div>
  <div class="order-sm-2 p-2">2. İçeriğimiz</div>
  <div class="order-sm-1 p-2">3. İçeriğimiz</div>
</div>
´´´
Artık sitemiz sm genişliklerede farklı gözükecetir.

İstediğimizi gerçekleştirmiş olduk Order kavramı Bootstrap bütün kırılma noktaları(xs-sm-md-lg-xl-xxl) için tanımlanmış class'lara sahiptir.

Bunlar:

order-0
order-1
order-2
order-3
order-4
order-5
order-sm-0
order-sm-1
order-sm-2
order-sm-3
order-sm-4
order-sm-5
order-md-0
order-md-1
order-md-2
order-md-3
order-md-4
order-md-5
order-lg-0
order-lg-1
order-lg-2
order-lg-3
order-lg-4
order-lg-5
order-xl-0
order-xl-1
order-xl-2
order-xl-3
order-xl-4
order-xl-5
order-xxl-0
order-xxl-1
order-xxl-2
order-xxl-3
order-xxl-4
order-xxl-5

İstediğimiz kırılma noktalarında istediğiniz sıralamayı gerçekleştirebilirsiniz, tek kullanım şekli bu değildir.

Aşağıdaki class'ları kullanarak da sıralama işlemlerinizi gerçekleştirebilirsiniz.

order-first
order-last
order-sm-first
order-sm-last
order-md-first
order-md-last
order-lg-first
order-lg-last
order-xl-first
order-xl-last
order-xxl-first
order-xxl-last

Bir örnek daha gerçekleştirelim Bootstrap ile hazırladığımız yapı ilk haliyle şu şekil olsun
´´´

<div class="container-fluid">
			<div class="row">
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex ">
						<h3>1.İçerik</h3>
				</div>
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex ">
						<h3>2.İçerik</h3>
				</div>
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex ">
						<h3>3.içerik</h3>
				</div>
			</div>
		</div>
´´´
![Örnek 7](örnek7.png)

Medium kırılma noktasından daha küçük genişliklerde 3.içeriğimizin ilk sıraya geçmesini istiyoruz. Fakat daha büyük genişliklerde bu sırayla kalmasını istiyoruz bunun için:
´´´

<div class="container-fluid">
			<div class="row">
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex order-3 order-md-1 ">
						<h3>1.İçerik</h3> 
				</div> 
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex order-2 order-md-2 ">
						<h3>2.İçerik</h3> 
				</div> 
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex order-1 order-md-3 ">
						<h3>3.içerik</h3>
				</div>
			</div>
		</div>
´´´
![Örnek 8](örnek8.png)

Farklı bir örnek daha
´´´

<div class="container-fluid">
			<div class="row">
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex order-3 order-md-1 ">
						<div class="row">
							<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-3 order-md-2 order-lg-1">
								<h3>1.İçeriğin 1.maddesi</h3>
							</div>
							<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-2 order-md-3 order-lg-2">
								<h3>1.İçeriğin 2.maddesi</h3>
							</div>
							<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-4 order-md-1 order-lg-3">
								<h3>1.İçeriğin 3.maddesi</h3>
							</div>
							<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-1 order-md-4 order-lg-4">
								<h3>1.İçeriğin 4.maddesi</h3>
							</div>
						</div>
				</div> 
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex order-2 order-md-2 ">
					<div class="row">
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-2 order-md-4 order-lg-1">
							<h3>2.İçeriğin 1.maddesi</h3>
						</div>
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-4 order-md-1 order-lg-2">
							<h3>2.İçeriğin 2.maddesi</h3>
						</div>
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-3 order-md-3 order-lg-3">
							<h3>2.İçeriğin 3.maddesi</h3>
						</div>
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-1 order-md-2 order-lg-4">
							<h3>2.İçeriğin 4.maddesi</h3>
						</div>
					</div>
				</div> 
				<div class="col-md-4 col-12 bg-dark text-white border-danger border d-flex order-1 order-md-3 ">
					<div class="row">
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-2 order-md-4 order-lg-1">
							<h3>3.İçeriğin 1.maddesi</h3>
						</div>
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-4 order-md-1 order-lg-2">
							<h3>3.İçeriğin 2.maddesi</h3>
						</div>
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-1 order-md-2 order-lg-3">
							<h3>3.İçeriğin 3.maddesi</h3>
						</div>
						<div class="col-md-4 col-12 bg-info text-white border-primary border d-flex order-3 order-md-3 order-lg-4">
							<h3>3.İçeriğin 4.maddesi</h3>
						</div>
					</div>
				</div>
			</div>
		</div>
´´´
![Örnek 9](örnek9.png)

## Bootstrap Bileşenlerine(UI Components) Genel Bakış
[İlgili Video](https://youtu.be/-5ZTS86imFM)