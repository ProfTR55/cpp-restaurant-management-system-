# Restoran Sipariş ve Yönetim Sistemi (C++)

Bu proje, C++ dili kullanılarak geliştirilmiş konsol tabanlı bir Restoran Sipariş ve Yönetim Sistemi'dir. Proje, **Nesne Yönelimli Programlama (OOP)** prensiplerini uygulamalı olarak göstermek amacıyla bir dönem projesi olarak hazırlanmıştır.

## Projenin Amacı

Uygulamanın temel amacı, OOP'nin temel kavramlarını (Kalıtım, Çok Biçimlilik, Kapsülleme) kullanarak gerçek hayata benzer bir senaryoyu modellemektir. Sistem, müşteri ve restoran yönetimi gibi iki ana modülden oluşur.

Kullanıcılar sisteme girerek;
- Farklı restoranları listeleyebilir,
- Menüleri inceleyebilir,
- Sipariş oluşturabilir ve sipariş geçmişini görüntüleyebilir.

Yöneticiler ise;
- Menüye yeni ürün ekleyebilir,
- Yeni çalışanları sisteme dahil edebilir,
- Çalışan bilgilerini listeleyebilir.

## Sergilenen OOP Konseptleri

- **Sınıflar (Classes):** `Restaurant`, `User`, `Customer`, `Employee`, `Manager`, `MenuItem`, `Order` gibi iyi tanımlanmış sınıflar mevcuttur.
- **Kalıtım (Inheritance):** 
  - `User` sınıfından `Customer` ve `Employee` sınıfları türetilmiştir.
  - `Employee` sınıfından `Manager` ve `DeliveryPerson` sınıfları türetilmiştir.
  - `MenuItem` soyut sınıfından `FoodItem` ve `DrinkItem` sınıfları türetilmiştir.
- **Çok Biçimlilik (Polymorphism):** 
  - `displayInfo()` ve `work()` gibi `virtual` fonksiyonlar sayesinde, temel sınıf işaretçisi üzerinden türemiş sınıfın doğru metodunun çağrılması sağlanmıştır.
  - `MenuItem` işaretçisi dizisi, hem `FoodItem` hem de `DrinkItem` nesnelerini tutabilmektedir.
- **Soyut Sınıflar (Abstract Classes):** `MenuItem` ve `Employee` gibi soyut sınıflar, belirli fonksiyonların (`showItem()`, `work()` vb.) türemiş sınıflar tarafından zorunlu olarak uygulanmasını sağlamak için kullanılmıştır.
- **Kapsülleme (Encapsulation):** Sınıf veri üyeleri `private` veya `protected` olarak tanımlanmış ve bu üyelere yalnızca `public` arayüz (getter/setter metodları) üzerinden kontrollü erişim sağlanmıştır.

> **Not:** Bu projenin gereksinimleri doğrultusunda, bellek yönetiminin temelini anlamak amacıyla `std::vector`, `std::list` gibi **STL (Standard Template Library)** koleksiyonları **kullanılmamıştır**. Bunun yerine, dinamik diziler ve manuel bellek yönetimi (`new[]`, `delete[]`) tercih edilmiştir.

## Nasıl Derlenir ve Çalıştırılır?

Projeyi derlemek ve çalıştırmak için bir C++ derleyicisine (örneğin g++) ihtiyacınız vardır.

1.  **Terminali/Komut İstemi'ni açın** ve projenin klasörüne gidin (örneğin, GitHub'dan indirdikten sonra):
    ```bash
    cd path/to/your/project-folder # Kendi proje dizininizin yolunu buraya yazın
    ```

2.  **Aşağıdaki komutu kullanarak tüm `.cpp` dosyalarını derleyin:**
    ```bash
    g++ -o restaurant_uygulamasi main.cpp user.cpp customer.cpp employee.cpp manager.cpp delıveryperson.cpp restaurant.cpp order.cpp menuıtem.cpp foodıtem.cpp drınkıtem.cpp
    ```

3.  **Derleme işlemi tamamlandıktan sonra uygulamayı çalıştırın:**
    ```bash
    ./restaurant_uygulamasi.exe
    ```
