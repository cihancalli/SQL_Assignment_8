# SQL_Assignment_8

## Sorgu Senaryoları

* test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.


```bash
CREATE TABLE employee (
  id INTEGER PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  birthday DATE NOT NULL,
  email VARCHAR(100) NOT NULL
);
```



* Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

```bash
Mockaroo'ya gidin ve "Employee" şablonu ile yeni bir veri kümesi oluşturun.
Gerekli alanları (id, name, birthday, email) ekleyin ve veri tiplerini doğru şekilde eşleştirin.
50 adet kayıt oluşturun ve JSON formatında indirin.
SQL Server Management Studio (SSMS) veya tercih ettiğiniz bir SQL istemcisini kullanarak veritabanına bağlanın.
"Import Data" seçeneğini kullanarak JSON dosyasını employee tablosuna içe aktarın.
```



* Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
* ID'ye göre isim güncelleme:


```bash
UPDATE employee
SET name = 'Ahmet'
WHERE id = 1;
```

* Doğum gününe göre email güncelleme:


```bash
UPDATE employee
SET email = 'yeni_email@example.com'
WHERE birthday BETWEEN '1980-01-01' AND '1985-12-31';
```

* Email'e göre isim ve doğum günü güncelleme:


```bash
UPDATE employee
SET name = 'Ayşe', birthday = '1990-05-15'
WHERE email LIKE '%@gmail.com';
```

* ID'ye göre maaş ekleme (Varsayılan değer):


```bash
UPDATE employee
SET salary = 5000
WHERE id = 10;
```

* Doğum gününe göre maaş güncelleme (CASE WHEN):


```bash
UPDATE employee
SET salary = CASE
  WHEN birthday BETWEEN '1980-01-01' AND '1985-12-31' THEN 6000
  ELSE 7000
END
WHERE birthday IS NOT NULL;
```



* Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
* ID'ye göre satır silme:

```bash
DELETE FROM employee
WHERE id = 20;
```

* İsim'e göre satır silme:

```bash
DELETE FROM employee
WHERE name = 'Mehmet';
```

* Email'e göre satır silme:

```bash
DELETE FROM employee
WHERE email LIKE '%hotmail.com';
```

* Doğum gününe göre satır silme:

```bash
DELETE FROM employee
WHERE birthday < '1995-01-01';
```

* Maaş'a göre satır silme:

```bash
DELETE FROM employee
WHERE salary IS NULL;
```