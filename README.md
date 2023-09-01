# Git Hile Sayfası (CheatSheet) by Cahit Karahan

## Başlangıç

- Git'i kurmak için: `git config --global user.name "Adınız"` ve `git config --global user.email "E-posta adresiniz"`
  - Örnek: `git config --global user.name "CahitKarahan"` ve `git config --global user.email "cahit@gofth.com"`
- Git'in kurulumunu kontrol etmek için: `git --version`
- Git'in yapılandırmasını görüntülemek için: `git config --list`


## Depo (Repository) Oluşturma

- Var olan bir depoyu klonlamak için: `git clone <url>`
  - Örnek: `git clone https://github.com/gofth/gofth-blog.git`
- Yeni bir yerel depo oluşturmak için: `git init`
  - Örnek: `git init yeni-projem`

## Değişiklikleri Takip Etme

- Çalışma dizinindeki dosyaların durumunu görmek için: `git status`
- İzlenen dosyalardaki değişiklikleri görmek için: `git diff`
  - Örnek: `git diff index.html`
- Yeni veya değiştirilmiş dosyaları izlemeye almak için: `git add <dosya>` veya `git add .` (tüm dosyalar için)
  - Örnek: `git add style.css` veya `git add .`
- Değişiklikleri kaydetmek için: `git commit -m "Mesaj"`
  - Örnek: `git commit -m "Stil dosyası eklendi"`
- Son commiti değiştirmek için: `git commit --amend`
  - Örnek: `git commit --amend -m "Yeni mesaj"`
- Son commiti geri almak için: `git reset --soft HEAD~1`
  - Örnek: `git reset --soft HEAD~1`

## Geçmişi Görüntüleme

- Commit geçmişini görmek için: `git log`
- Commit geçmişini tek satırda görmek için: `git log --oneline`
- Bir dosyanın geçmişini görmek için: `git log -p <dosya>`
  - Örnek: `git log -p index.html`
- Bir dosyada kimin ne zaman ne yaptığını görmek için: `git blame <dosya>`
  - Örnek: `git blame index.html`

## Dal (Branch) Yönetimi

- Mevcut dalları listelemek için: `git branch`
- Yeni bir dal oluşturmak için: `git branch <dal>`
  - Örnek: `git branch yeni-dal`
- Başka bir dala geçmek için: `git checkout <dal>`
  - Örnek: `git checkout yeni-dal`
- Yeni bir dal oluşturup ona geçmek için: `git checkout -b <dal>`
  - Örnek: `git checkout -b yeni-dal`
- Bir dalı silmek için: `git branch -d <dal>`
  - Örnek: `git branch -d yeni-dal`
- Bir dalı yeniden adlandırmak için: `git branch -m <yeni-dal>`
  - Örnek: `git branch -m eski-dal yeni-dal`

## Uzak (Remote) Depolarla Çalışma

- Uzak depoları listelemek için: `git remote -v`
- Yeni bir uzak depo eklemek için: `git remote add <isim> <url>`
  - Örnek: `git remote add origin git@github.com:gofth/gofth-blog.git`
- Uzak depodaki değişiklikleri indirmek için: `git fetch <uzak>`
  - Örnek: `git fetch origin`
- Uzak depodaki değişiklikleri indirip birleştirmek için: `git pull <uzak> <dal>`
  - Örnek: `git pull origin master`
- Yerel değişiklikleri uzak depoya göndermek için: `git push <uzak> <dal>`
  - Örnek: `git push origin master`
- Uzak depoyu kaldırmak için: `git remote rm <uzak>`
  - Örnek: `git remote rm origin`

## Birleştirme (Merge) ve Rebase

- Bir dalı mevcut dala birleştirmek için: `git merge <dal>`
  - Örnek: `git merge yeni-dal`
- Birleştirme çakışmalarını çözmek için: Çakışan dosyaları düzenleyin ve `git add <dosya>` ile işaretleyin
  - Örnek: index.html dosyasındaki çakışmaları düzenleyin ve `git add index.html` ile işaretleyin
- Bir dalın commitlerini mevcut dalın üzerine eklemek için: `git rebase <dal>`
  - Örnek: `git rebase yeni-dal`
- Rebase işlemini iptal etmek için: `git rebase --abort`

## Geri Alma

- Son commiti geri almak ve değişiklikleri korumak için: `git reset --soft HEAD~1`
- Son commiti geri almak ve değişiklikleri silmek için: `git reset --hard HEAD~1`
- Bir dosyadaki değişiklikleri geri almak için: `git checkout -- <dosya>`
  - Örnek: `git checkout -- index.html`
- Bir dosyayı belirli bir committeki haline geri döndürmek için: `git checkout <commit> <dosya>`
  - Örnek: `git checkout 2f3e34 index.html`

## İpuçları

- Git komutlarının yardım sayfalarını görmek için: `git help <komut>`
  - Örnek: `git help commit`
- Git komutlarının kısa açıklamalarını görmek için: `git <komut> -h`
  - Örnek: `git commit -h`
- Git komutlarının çıktılarını renklendirmek için: `git config --global color.ui auto`
- Git komutlarının takma adlarını oluşturmak için: `git config --global alias.<takma-ad> <komut>`
  - Örnek: `git config --global alias.ci commit`

## Etiket (Tag) Yönetimi

- Mevcut etiketleri listelemek için: `git tag`
- Yeni bir etiket oluşturmak için: `git tag <etiket>`
  - Örnek: `git tag v1.0`
- Bir commiti etiketlemek için: `git tag -a <etiket> -m "Mesaj" <commit>`
  - Örnek: `git tag -a v1.0 -m "Sürüm 1.0" 2f3e34`
- Bir etiketi silmek için: `git tag -d <etiket>`
  - Örnek: `git tag -d v1.0`
- Bir etiketi uzak depoya göndermek için: `git push <uzak> <etiket>`
  - Örnek: `git push origin v1.0`
- Tüm etiketleri uzak depoya göndermek için: `git push <uzak> --tags`
  - Örnek: `git push origin --tags`

## Stash

- Çalışma dizinindeki değişiklikleri saklamak için: `git stash`
- Saklanan değişiklikleri geri yüklemek için: `git stash pop`
- Saklanan değişiklikleri listelemek için: `git stash list`
- Saklanan değişiklikleri silmek için: `git stash drop`

## Diğer Faydalı Komutlar

- Bir dosyayı izleme dışı bırakmak için: `git rm --cached <dosya>`
  - Örnek: `git rm --cached index.html`
- Bir dosyayı yeniden adlandırmak veya taşımak için: `git mv <eski-dosya> <yeni-dosya>`
  - Örnek: `git mv index.html home.html`
- Bir dosyayı veya klasörü yoksaymak için: `.gitignore` dosyasına yoksayılacak dosya veya klasörün adını yazın
- Git komutlarının kısayollarını görmek için: `git help -a`
- Git komutlarının kılavuzunu görmek için: `git help -g`