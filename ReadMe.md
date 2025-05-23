# Unity Gelişmiş Envanter Sistemi

Bu proje, Unity oyun motoru için geliştirilmiş, tıklanabilir dünya objelerinden eşya toplama, eşya yığınlama, maksimum kapasite kontrolü ve kullanıcı arayüzü (UI) üzerinden eşya kullanımı gibi özelliklere sahip kapsamlı bir envanter sistemidir.


[Envanter Sistemi Görseli](https://cdnb.artstation.com/p/assets/images/images/088/343/435/large/emirhan-hatipoglu-ekran-goruntusu-2025-05-23-215229.jpg?1748027047)

## 🎬 Tanıtım ve Demo Videosu

Sistemin nasıl çalıştığını görmek için aşağıdaki videoyu izleyebilirsiniz:

[![Envanter Sistemi Demosu](https://www.youtube.com/watch?v=LpLopWufD-s/0.jpg)](https://www.youtube.com/watch?v=LpLopWufD-s)

## ✨ Özellikler

*   **Item Editor'u(`Item.cs`):**
    *   `ItemEditorWindow.cs` ile Unity editörü üzerinden kolayca yeni eşyalar oluşturulabilir ve düzenlenebilir.
*   **Gelişmiş Envanter Yönetimi (`InventoryManager.cs`):**
    *   Singleton deseni ile kolay erişim.
    *   Belirlenen sayıda slot kapasitesi.
    *   Eşyaları envantere eklerken mevcut yığınları kontrol eder ve maksimum kapasiteye ulaşıldıysa yeni bir yığın oluşturur.
    *   Envanter doluysa eşya eklemez ve kullanıcıyı bilgilendirir.
    *   Eşya kaldırıldığında sonraki eşyaların yerini otomatik olarak kaydırır (Liste yapısı sayesinde).
    *   Envanterdeki değişikliklerde (eşya ekleme, çıkarma, kullanma) UI'ı güncellemek için olay (event) tabanlı sistem.
*   **Kullanıcı Arayüzü Yönetimi (`InventoryUI.cs`):**
    *   Belirlenen bir tuşla (varsayılan: 'E') envanter panelini açıp kapatma.
    *   Envanterdeki eşyaları slotlarda gösterme.
    *   `InventoryManager`'daki değişikliklere göre UI'ı otomatik güncelleme.
*   **Slot Yönetimi ve Eşya Kullanımı (`Slot_Script.cs`):**
    *   Her bir envanter slotunun görselini (ikon, miktar) ve davranışını yönetir.
    *   Slota tıklandığında ilgili eşyanın kullanılmasını sağlar.
    *   Tüketilebilir eşyaların miktarı azalır, bittiğinde envanterden kaldırılır.


## 🚀 Kurulum ve Kullanım

1.  **Projeyi Klonlayın/İndirin:**
    ```bash
    git clone https://github.com/xunbreakablex/Inventory-System.git
    ```
    veya ZIP olarak indirin.
2.  **Unity ile Açın:** Projeyi Unity Hub üzerinden açın (Unity 2019.4 veya üstü önerilir).
3.  **TextMeshPro Kurulumu:** Eğer projede TextMeshPro objeleri kullanılıyorsa (genellikle metin gösterimi için daha iyidir), Unity ilk açılışta "TMP Essentials" import etmenizi isteyebilir. Bunu onaylayın.
4.  **Ana Sahne:** Projeyi açtıktan sonra örnek bir sahne (varsa) veya kendi sahnenizi oluşturun.
5.  **Gerekli Prefab/Objeler:**
    *   `InventoryManager`: Boş bir GameObject oluşturup `InventoryManager.cs` script'ini ekleyin veya hazır bir prefab'ı sahneye sürükleyin. `Space` (slot sayısı) değerini ayarlayın.
    *   `InventoryUI`: Bir Canvas oluşturun. İçine `InventoryUI.cs` script'ini yönetecek bir GameObject (örn: "UIManager") ve envanter panelini (`inventoryPanel`), slotların ebeveynini (`itemsParent`) ve slot prefab'ını (`slotPrefab`) ayarlayın. Detaylar için `InventoryUI.cs` script'indeki tooltip'lere bakın.
6.  **Eşya Tanımlama:**
    *   Project penceresinde sağ tıklayarak `Inventory/Item` seçeneği ile yeni `Item` ScriptableObject'ları oluşturun veya `Inventory/Item Editor` penceresini kullanarak yeni eşyalar yaratın/düzenleyin.
    *   Bu eşyaların `itemName`, `icon`, `maximumCapacity`, `description` gibi özelliklerini ayarlayın.
7.  **Toplanabilir Eşyalar Oluşturma:**
    *   Sahnenize 3D objeler veya 2D Sprite'lar ekleyin.
    *   Bu objelere istediğiniz tetikleyiciyi ekleyin ve tetikleyici ile `InventoryManager.Add()` fonksiyonunu çağırın
    *   ``InventoryManager.Add()`` fonksiyonu ile `Item SO` alanına oluşturduğunuz `Item` ScriptableObject'larından birini ve `Quantity To Add` değerini atayın.
8.  **Çalıştırın!**
    *   'E' tuşuna basarak envanter panelini açıp kapatabilirsiniz.
    *   Envanterdeki bir slota tıklayarak eşyayı kullanabilirsiniz. Konsol çıktılarını takip ederek sistemin işleyişini görebilirsiniz.


## 🔧 Gelecekteki Olası Geliştirmeler

*   Eşyaları sürükleyip bırakarak yerlerini değiştirme.
*   Eşyaları envanterden dışarıya (dünyaya) bırakma.
*   Farklı eşya türleri (örn: ekipman, silah) ve bunlara özel kullanım mantıkları.
*   Basit bir crafting (eşya üretme) sistemi entegrasyonu.
*   Envanter durumunu kaydetme ve yükleme.

*   Daha Fazlası için Linkedin ve Artstation hesabıma bakmayı unutmayın
*   https://www.linkedin.com/in/emirhan-hatipo%C4%9Flu-9a3b31249/
*   https://www.artstation.com/xzeus08x5
