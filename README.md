# sql-notlar
## SQL(Structured Query Language) 
Veritabanı ile iletişim kurmak için kullanılan bir dildir.
<br/><br/>
### SQL'de vari tipleri?
- Numeric : bit, tinyint, smallint, int, bigint, decimal, numeric, float, real

- Date/Time : Date, Time, Datetime, Timestamp, Year

- Character/String : char, Varchar, Varchar(max), Text

- Unicode Character/String : NChar, NVArchar, NVArchar(max), NText
(uluslararası tüm diller içinde bulunur.)

- Binary : Binary, Varbinary, Varbinary(max), image

- Miscellaneous : Clob, Blob, XML, JSON
<br/><br/>
### SQL içindeki yerleşik function'lar
* AVG(): Kolonun ortalam değerini bulur.
* COUNT(): Satır sayısını bulur
* ROUND(): Ondalıklı sayıyı yuvarlamak için kullanılır.
* FIRST(): İlk değeri verir
* LAST(): Son değeri verir
* MAX(): En büyük değeri verir
* MIN(): En küçük değeri verir
* SUM(): Kolonu toplar
* LCASE(): Metinleri küçük harfe çevirir
* UCASE(): Metinleri büyük harfe çevirir
* LEN(): bir metin alanındaki değerin uzunluğunu döndürür.
* MID(): Metinden parça alır.
* NOW(): An'ın tarihini ve saatini verir
* FORMAT(): Verinin gösterilme biçimini değiştirir.

NOT: metinsel ifadeler tek tırnak ile gösterilir.

### SQL sorguları
- Distinct : benzersiz kayıtları getirmek için kullanırız yani bir kolonda her şeyden bir tane getir 
(DISTINCT: SELECT deyimi ile kullanılır. Kayıt yinelenen değerler içeriyorsa, DISTINCT deyimi yinelenen kayıtlar arasında farklı değerler seçmek için kullanılır.)
- FROM : verileri çekmek istediğiniz tabloyu belirler
- WHERE : bir sorguyu daha spesifik olacak şekilde filtrelemenize olanak tanır

#### Operator	Açıklama
"="  : Eşit<br/>
"<>" : EşitDeğil. Note: Bazı versiyonlarda “!=” kullanılabilir.<br/>
">"  : Büyüktür<br/>
"<"  : Küçüktür.<br/>
">=" : Büyük Eşit<br/>
"<=" : Küçük Eşit<br/>

BETWEEN		İki koşul arasında arama yapmamızı sağlar<br/>
LIKE		Belirtilen bir değeri aramak için kullanılır.(Genellikle % birlikte kullanılır. % :Birden fazla harf ya da rakamın yerini tutar.)<br/>
IN		Bir sütun için birden çok olası değerleri belirtmek için<br/>


- ORDER BY : SELECT deyiminde belirttiğiniz alanlardan herhangi birine göre sıralama yapmanızı sağlar.(defaultta asc'dir ama desc olabilir. Artan sıralama ASC, Azalan sıralama DESC)
- GROUP BY : verileri belirtilen özniteliğe göre gruplandırır.
- HAVING : GROUP BY yan tümcesi ile bağlantılı olarak kullanılır. Her bir sonuç grubuna veya tüm sonuca tek bir grup olarak uygulanır. WHERE cümlesine çok benzer ancak tek fark onu GROUP BY cümlesi olmadan kullanamamanızdır.
- LIMIT : sorguyu sınırlamanıza izin verir.

- INSERT INTO : Kayıt eklemek için kullanılır.

- UPDATE : Kayıtlar üzerinde değişiklik güncelleme yapmak için kullanılır.
- DELETE : Tablodan kayıt silmek için kullanılır.

- ALIASES : SQL tablosunda yer alan sütunlara geçici bir ad vermek için kullanılır.

- COUNT() : belirtilen ölçütlerle eşleşen satır sayısını döndürür.
- AVG() : NULL değerleri hariç (boş), bir kolonun ortalamasını hesaplar
- SUM() : Kolonun toplamını döner

- JOIN
Bir SQL sorgusunda iki farklı tablodaki bilgilere erişmeniz gereken zamanlar kullanılabilir. Bu komut sayesinde iki table’ı bir bütün haline getirebilir veya bir table’dan diğerine veri aktarabilirsiniz.

- CASE
Karşılanan koşula bağlı olarak sorgunuza farklı sonuçlar döndürmek istediğinizde bir CASE deyimi kullanın.

<br/><br/>
### Normalizasyon(normalization)
İlişkisel veritabanı tasarlanması aşamasında verinin tekrarlanmasını, kaybını veya yetersizliğini önlemek için normalization yapılır<br/>

#### Normalization Amacı
- Veri bütünlüğünü sağlamak
- Uygulamadan bağımsızlık
- Performansı Arttırmak
<br/><br/>
#### İşlevsel Bağımlılık
X ve Y birer kümedir. Eğer X nitelik kümesinin değerleri Y nitelik kümesinin değerlerini belirliyorsa ;<br/>
"Y niteliği X niteliğine işlevsel bağımlıdır" denir ve "X -> Y" şeklinde gösterilir.
<br/><br/>
#### Normalleştirme Aşamaları
- Birinci Normal Form(1NF)
- İkinci Normal Form(2NF)
- Üçüncü Normal Form(3NF)
- Boyce-Codd Normal Form(BCNF)
- Dördüncü Normal Form(4NF)
<br/>

1.NF<br/>
* Her satır bir eşsiz key ile tanımlanmalıdır.(Unique Key-Primary Key)<br/>
* Her kolonda yanlızca bir değer bulunabilir.<br/>
* Aynı tablo içinde tekrarlayan kolonlar bulunamaz(bir ürünü alan kişilerin adlarının aynı yerde tutulmaması gerekir)<br/><br/>

2.NF<br/>
- 1.NF uymalı<br/>
- Key olmayan değerler ile bileşik keyler arasında kısmi bağımlılık durumu oluşmamalıdır.<br/>
- Herhangi bir veri alt kümesi birden çok satırda tekrarlanmamalıdır. Bu tür veriler için yeni tablolar oluşturulmalı<br/>
- Ana tablo ile yeni tablolar arasında foreign key kullanılarak ilişkiler tanımlanmalıdır.<br/>
(Benzersiz key'i olan kayıtlar ayrı tablolara taşınıdı ve ana tablo ile ilişkilendirildi)<br/><br/>

3.NF<br/>
- 2.NF uygun olmalı<br/>
- Key olmayan bir alanlar varsa, keyleri oluşturulur ve foreign keyler ile ilişkilendirilmeli<br/>
(Benzersiz keyi olmayan alanlar belirlendi ve benzersiz keyler oluşturlur ve ilgili tablolara bağlanır.)<br/><br/>


