# Temel Git Komutları

				LOCAL					|	REMOTE
Working Directory  =>	 Staging Area    =>	Local Repository	|||		Remote Repository
			(Working Tree)


--------------------------------------------------
Proje dosyasının içerisine boş bir git repository oluşturur
```
git init
```
--------------------------------------------------
git'in durumun nedir, dosya geçiş bölgesinde mi working area'da mı görülür.
```
git status
```
sadece modified yapılanları listeler
```
git status -s
```
--------------------------------------------------
Staging Area'ya geçiş	(Changes to be commited - alanı)
```
git add .
```
--------------------------------------------------
Yaptığın tüm değişikliklerin stagin area'ya gitmesini sağlar
```
git add -A
```
--------------------------------------------------
Böyle yaparsan Vim Editör açar, mesaj girmeni ister. 
```
git commit
```
Editörden çıkmak için ESC'ye bas ve bu komutu yaz => :x! 

--------------------------------------------------
Staging area'dakileri, lokal repo alanına gönderir. Mesajda kısmında commit log mesajı yazılır.
```
git commit -m 'mesaj'
```
--------------------------------------------------
Deneme.txt'yi daha önce staging area'ya açmıştım. O değişikliği geri çekmek için...Sonrasında git status'de yine kırmızı görünür.
```
git restore --staged Deneme.txt
```
--------------------------------------------------
Yaptığın değişiklikleri working directory'nde de geri alıp görebilirsin
```
git restore Deneme.txt
```
--------------------------------------------------
Son yapılan değişikliği gösterir
```
git show
```
--------------------------------------------------
Yapılan tüm commitlerin listesini çıkarmak için;
```
git log
```
Daha sade bir şekilde commit listesi için;
```
git log --oneline
```
Son 2 log'u görmek için;
```
git log -p -2
```
Q'ya basarak tekrar Bash'e dönebilirsin

30 dakika içerisinde yapılan commit'leri gösterir (30minutes yerine => 5hours, 3days, 2weeks gibi gibi)
```
git log --since=30minutes
```
--------------------------------------------------
xxxxx log'una geri döner.Buradan devam edersen ilerisini kaybedersin.
```
git checkout xxxxxx
```
Tekrar ileri eski yerine gider
```
git checkout master
```
Aradan bir commit'i/log'u iptal edip çıkartmak için
```
git revert xxxxxx
```
--------------------------------------------------
### RESET !!!TEHLİKELİ!!!
Girdiğin commit id'ye kadar olan tüm logları siler ve eskiye döner
```
git reset --soft COMMIT_ID
```
Repoyu resetler	
```
git reset --mixed COMMIT_ID
```
Repo+Stating Area resetler
```
git reset --hard COMMIT_ID
```
Herşeyi resetler

--------------------------------------------------
.ignore projenin başında atmazsan, sorun olur yine status'de istemediğin dosyayı görürsün
çözüm;
```
git rm -r --cached .
```
track edilen tüm dosyaları siler/dosyaları kaldırmaz, izlemeden kaldırır
```
git add .
```
tüm dosyaları tekrar eklersin
```
git commit -m 'git ignore sorunu çözüldü'
```
--------------------------------------------------
### .gitignore
log.txt
sadece bu dosyayı izlemez

directory/xxx
xxx dosya yolundakileri izlemez

*.xyz
.xyz uzantılı dosyaları izlemez


node_modules/
dist/
#Visual Studo 2015 cache/options directory
.vs/
