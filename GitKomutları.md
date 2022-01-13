# Temel Git Komutları

				LOCAL					|	REMOTE
Working Directory  =>	 Staging Area    =>	Local Repository	|||		Remote Repository
			(Working Tree)


--------------------------------------------------
``git init``
Proje dosyasının içerisine boş bir git repository oluşturur
--------------------------------------------------
``git status``
git'in durumun nedir, dosya geçiş bölgesinde mi working area'da mı görülür.
``git status -s``
sadece modified yapılanları listeler
--------------------------------------------------
``git add .``
Staging Area'ya geçiş?	(Changes to be commited - alanı)
--------------------------------------------------
``git add -A``
Yaptığın tüm değişikliklerin stagin area'ya gitmesini sağlar
--------------------------------------------------
git commit
Böyle yaparsan Vim Editör açar, mesaj girmeni ister. 
Editörden çıkmak için ESC'ye, bas aşağıdaki komutu yaz.
:x! 
--------------------------------------------------
``git commit -m 'mesaj'``
Staging area'dakileri, lokal repo alanına gönderir. Mesajda kısmında commit log mesajı yazılır.
--------------------------------------------------
``git restore --staged Deneme.txt``
Deneme.txt'yi daha önce staging area'ya açmıştım. O değişikliği geri çekmek için...Sonrasında git status'de yine kırmızı görünür.
--------------------------------------------------
``git restore Deneme.txt``
Yaptığın değişiklikleri working directory'nde de geri alıp görebilirsin
--------------------------------------------------
``git show``
Son yapılan değişikliği gösterir
--------------------------------------------------
``git log``
Yapılan tüm commitlerin listesini çıkarır
``git log --oneline``
Daha sade bir şekilde commit listesini verir
``git log -p -2``
Son 2 logunu gösterir
Q'ya basarak tekrar Bash'e dönebilirsin
``git log --since=30minutes``
30 dakika içerisinde yapılan commit'leri gösterir (30minutes yerine => 5hours, 3days, 2weeks gibi gibi)
--------------------------------------------------
``git checkout xxxxxx``
xxxxx log'una geri döner.Buradan devam edersen ilerisini kaybedersin.
``git checkout master``
Tekrar ileri eski yerine gider
``git revert xxxxxx``
Aradan bir commit'i/log'u iptal edip çıkartmak için
--------------------------------------------------
### RESET !!!TEHLİKELİ!!!
Girdiğin commit id'ye kadar olan tüm logları siler ve eskiye döner
``git reset --soft COMMIT_ID``
Repoyu resetler	
``git reset --mixed COMMIT_ID``
Repo+Stating Area resetler
``git reset --hard COMMIT_ID``
Herşeyi resetler
--------------------------------------------------
.ignore projenin başında atmazsan, sorun olur yine status'de istemediğin dosyayı görürsün
çözüm;
``git rm -r --cached .``
track edilen tüm dosyaları siler/dosyaları kaldırmaz, izlemeden kaldırır
``git add .``
tüm dosyaları tekrar eklersin
``git commit -m 'git ignore sorunu çözüldü'``
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
# Visual Studo 2015 cache/options directory
.vs/
