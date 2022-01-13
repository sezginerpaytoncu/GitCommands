# Git & Github


Local'de bulunan repoya remote repoyu tanıtmak
git remote add origin https://github.com/sezginerpaytoncu/FirstGitHubTrial.git
------------------------------
git branch -M main
git push -u origin main
------------------------------
git push -u origin master
------------------------------
tek bir branch üzerinden çalışıyorsan sadece;
git push
yazabilirsin
------------------------------
download: zip olarak indirir, dosyaları kopyalar, projeyi açarsın. Git'ten bağımsız olur.
------------------------------
git clone https://.................
projeyi git repository olarak klonlar.
------------------------------
git remote -v
Remote'da gidilen dosyayı/linki gösterir
------------------------------------------------------------
git commit -am "Açıklama" 
git status'de modified olan tek dosyayı yüklerken bu komutu kullanabilirsin

veya
git commit -am repo/İçerisindeki/dosya/yolu/ "mesaj"
belirlediğin klasörü gönderir
------------------------------------------------------------

hem sen değişiklik yaptın, hem de remote'da başka bir değişiklik varsa git push hata verir
![rejected] master->master (fetch first)
-----
git fetch
remote'da yapılan değişikliği kendi lokal repo'na alırsın.
Uzak bağlantıdaki değişiklikleri kopyalar, ancak merge etmez. 
Yani değişiklikte herhangi bir problem var mı kontrol etmene olanak sağlar.
-----
remote'daki değişiklikleri lokal repo'na almak için
git merge 
editör gelir
:wq	yazarak editörden çıkarsın
merge'den sonra remote'da olan değişikliği, lokal repo'ndan alıp çalışma alanına uygulatırsın.
-----
git pull = git fetch + git merge => demektir
-----

--------------------------------------------------------------------------------

ÇEŞİTLİ SENARYOLAR
------------------------------------------------------------
Hem sen hem de remote repo'da aynı dosyalar değiştirildiyse conflict hatası alırsın
git pull 
Yaparken oto merge kısmında conflict hatası çıkar. Belirtilen dosyayı açtığında;
<<<<<<HEAD	olarak belirtilen kendi oluşturduğumuz, lokalde yaptığımız değişikliktir.
==========	altında yer alan değişiklik remote'da yapılan değişikliktir.
------------------------------
Lokaldesin ve yeni bir branch üzerinden değişiklik göndereceksin. Bu branch remote'da yoksa;
git checkout -b cssfeature
cssfeature isminde yeni bir branch oluşturup, o branch'e geçer
-----
git push origin cssfeature
değişiklikler gidecek, compare&pull request'e girersin. Açıklamanı yazarsın ve talebi gönderirsin.
Github'da üzerinden yeni bir branch bildirimi gider.(Ekip liderine)
Ekip lideri=> Merge pull requst'e bakıp değişikliği görür.
------------------------------------------------------------

branch üzerinde yapıtğın değişikliği push ile gönderdin. Ekip lideri kabul etti. ve senin branch'i sildi, master branch üzerine merge etti.
Senin tekrar git pull ile master branch'i alman ve kendi repo'nu güncellemen gerekir.
------------------------------
git branch -d xxx
xxx branch'ini siler(bir üstteki örnekte kendi oluşturduğun branch açıkta kalır, çünkü ekip lideri senin pull request'ini kabul edip branch'i sildi
branch silmeden önce iyi düşün!


