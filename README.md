# ✨ Particle Playground

Fare hareketlerine tepki veren, fizik tabanlı, etkileşimli bir parçacık
animasyonu. Tek bir HTML dosyası, sıfır bağımlılık — açın ve oynayın.

## Özellikler

- 🧲 **4 etkileşim modu**: Çek (attract), İt (repel), Girdap (swirl),
  Serbest (none)
- 🎛️ Canlı ayarlanabilir parçacık sayısı, etki yarıçapı ve kuvvet
- 🕸️ Yakın parçacıklar arasında dinamik bağlantı çizgileri (takımyıldız efekti)
- 🎨 Hıza göre değişen renk ve boyut (hızlı parçacıklar daha büyük/parlak)
- 📱 Dokunmatik ekran desteği (mobil cihazlarda parmakla etkileşim)
- 📊 Gerçek zamanlı FPS göstergesi
- 🪶 Hiçbir kütüphane veya framework yok — saf Canvas API

## Kullanım

Kurulum gerekmez:

```bash
open index.html        # macOS
xdg-open index.html     # Linux
```

Fareyi ekranda hareket ettirin, parçacıkların tepkisini izleyin. Sol
üstteki panelden:

- **Mod** seçin: Çek (parçacıklar fareye doğru akar), İt (parçacıklar
  fareden kaçar), Girdap (parçacıklar fare etrafında döner), Serbest
  (fare etkisi olmadan doğal hareket)
- **Parçacık sayısı**, **etki yarıçapı** ve **kuvvet** kaydırıcılarıyla
  davranışı özelleştirin

## Nasıl çalışır?

Her parçacık basit bir fizik döngüsü ile güncellenir:

1. Fareye olan uzaklık hesaplanır
2. Uzaklık, seçilen etki yarıçapı içindeyse, moda göre bir kuvvet vektörü
   hesaplanır (çekme: fareye doğru, itme: fareden uzağa, girdap: teğetsel/dik yönde)
3. Bu kuvvet parçacığın hızına eklenir
4. Sürtünme katsayısı (`0.97`) uygulanır, böylece hız sonsuza kadar
   artmaz ve parçacıklar doğal şekilde yavaşlar
5. Konum güncellenir, kenarlardan basit bir "sekme" ile sınırlandırılır

Performans için, parçacıklar arası bağlantı çizgileri yalnızca parçacık
sayısı belirli bir eşiğin altındayken çizilir (yüksek parçacık
sayılarında O(n²) bağlantı hesabı FPS'i düşürebilir).

## Lisans

MIT
