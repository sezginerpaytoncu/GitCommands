# Working With Branches

``git branch``
Proje içerisinde bulunan branch'leri gösterir.
---
``git branch develop``
develop isminde bir branch oluşturur
---
``git branch -a``
tüm branch'leri gösterir
---
``git checkout -b cssfeature``
cssfeature isminde yeni bir branch oluşturup, o branch'e geçer.
Bu işlem hangi branch'de yapılırsa, dallanma o branch'den gerçekleşir.
---
``git checkout cssbranch``
css branch'ine gider (satırda en sağda branch ismi değişir. master'dan cssbranch'e geçer)
---
İlgili branch'de(örneğin cssfeature) değişikliğini yaptıktan sonra;
``git add feature1.css``
``git commit -m 'Sayfa görünümü değişti'``
komutları çalıştırılırsa sadece cssfeature branch'inde değişiklik olur.
Eğer başka bir branch'e geçiş yapılırsa, cssfeature branch'de yapılan değişiklikler görünmez.
---
git merge cssbranch htmlbranch
cssbranch ve htmlbranch branch'larında yapılan değişiklikleri o sırada bulunulan branch'e uygular. 
Otomatik olarak merge branches mesajı gelir, insert etmek için i'ye basıp :x! ile çıkış yaparsın
---
``git push origin cssfeature``
cssfeature branch'indeyken yapılan commit'lerin uzak repodaki cssfeature branch'ine gönderilmesidir.
---
Örnek senaryo; main'den cssfeature branch'ine geçildi. Ancak bu sırada main'de değişiklik yapıldı. Bu değişikliği cssfeature branch'ine almak için;
(cssfeature branch'indeyken)
``git fetch origin main``
Ardından commit log'larından doğru olup olmadığı kontrol edilebilir
``git log``