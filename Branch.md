# Working With Branches

Proje içerisinde bulunan branch'leri görmek için;
```
git branch
```
------------
develop isminde bir branch oluşturmak için;
```
git branch develop
```
------------
tüm branch'leri görmek için;
```
git branch -a
```
------------
cssfeature isminde yeni bir branch oluşturup, o branch'e geçer.
Bu işlem hangi branch'de yapılırsa, dallanma o branch'den gerçekleşir.
```
git checkout -b cssfeature
```
------------
css branch'ine gider (satırda en sağda branch ismi değişir. master'dan cssbranch'e geçer)
```
git checkout cssbranch
```
------------
İlgili branch'de(örneğin cssfeature) değişikliğini yaptıktan sonra, aşağıdaki komutlar çalıştırılırsa sadece cssfeature branch'inde değişiklik olur.
Eğer başka bir branch'e geçiş yapılırsa, cssfeature branch'de yapılan değişiklikler görünmez.
```
git add feature1.css
git commit -m 'Sayfa görünümü değişti'
```
------------
cssbranch ve htmlbranch branch'larında yapılan değişiklikleri o sırada bulunulan branch'e uygular. 
Otomatik olarak merge branches mesajı gelir, insert etmek için i'ye basıp :x! ile çıkış yaparsın
```
git merge cssbranch htmlbranch
```
------------
cssfeature branch'indeyken yapılan commit'lerin uzak repodaki cssfeature branch'ine gönderilmesi için;
```
git push origin cssfeature
```
------------
Örnek senaryo; main'den cssfeature branch'ine geçildi. Ancak bu sırada main'de değişiklik yapıldı. Bu değişikliği cssfeature branch'ine almak için;
(cssfeature branch'indeyken)
```
git fetch origin main
```
Ardından commit log'larından doğru olup olmadığı kontrol edilebilir
```
git log
```