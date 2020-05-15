---
title: "Linux Temeller - 1 🇹🇷"
lay out: post
date: 2019-01-10 09:04
image: /assets/images/bash_preview.jpg
headerImage: false
tag:
- linux
- terminal
- komut
category: blog
author: mrturkmen
description: Linuxa başlamak ve basit komutları ögrenmek
---

## Özet:

Bu yazıda linux ortamına biraz daha giriş yaparak, linux ortamında bulunan komutlar hakkında kısa bilgilendirme yapılması planlanmaktadır. 

## İçindekiler:

- [Özet:](#%c3%96zet)

- [Özet:](#%c3%96zet)
- [İçindekiler:](#%c4%b0%c3%a7indekiler)
- [Giriş](#giri%c5%9f)
    - [Neden Linux ?](#neden-linux)
- [Temeller](#temeller)
    - [Bu bilgilendirme dosyası için not](#bu-bilgilendirme-dosyas%c4%b1-i%c3%a7in-not)
    - [Windows bilgisayar üzerinden giriş için](#windows-bilgisayar-%c3%bczerinden-giri%c5%9f-i%c3%a7in)
    - [Mac veya Linux Bilgisayarlardan Erişim](#mac-veya-linux-bilgisayarlardan-eri%c5%9fim)
    - [Giriş yaptıktan sonra şifrenizi değiştirmek isterseniz](#giri%c5%9f-yapt%c4%b1ktan-sonra-%c5%9fifrenizi-de%c4%9fi%c5%9ftirmek-isterseniz)
    - [Listeleme](#listeleme)
    - [Dosyalar ve Klasörler](#dosyalar-ve-klas%c3%b6rler)
- [Kısayollar](#k%c4%b1sayollar)
- [Yardım Alma](#yard%c4%b1m-alma)
- [Aradığınız Dosyayı Bulma Yöntemleri](#arad%c4%b1%c4%9f%c4%b1n%c4%b1z-dosyay%c4%b1-bulma-y%c3%b6ntemleri)
    - [Arama yapmak](#arama-yapmak)
    - [Dosya içerisinde arama yapmak](#dosya-i%c3%a7erisinde-arama-yapmak)
- [İzinler & Hak Sahipliği](#%c4%b0zinler--hak-sahipli%c4%9fi)
    - [Kullanıcı haklarının alınması](#kullan%c4%b1c%c4%b1-haklar%c4%b1n%c4%b1n-al%c4%b1nmas%c4%b1)
    - [Hak sahipliğinin değiştirilmesi](#hak-sahipli%c4%9finin-de%c4%9fi%c5%9ftirilmesi)
- [Kullanışlı Linux Komutları](#kullan%c4%b1%c5%9fl%c4%b1-linux-komutlar%c4%b1)
- [İşlem Yönetimi](#%c4%b0%c5%9flem-y%c3%b6netimi)
- [Text dosyalarını okumak](#text-dosyalar%c4%b1n%c4%b1-okumak)
- [Metin Düzenleyicileri](#metin-d%c3%bczenleyicileri)
    - [VI ve VIM](#vi-ve-vim)
    - [EMACS](#emacs)
    - [XEMACS](#xemacs)
    - [PICO](#pico)
- [VIM Temelleri](#vim-temelleri)
    - [Temeller](#temeller-1)
    - [Yardım](#yard%c4%b1m)
    - [Dosya içerisinde gezme  (vim içerisinde)](#dosya-i%c3%a7erisinde-gezme-vim-i%c3%a7erisinde)
    - [Görüntü (vim içerisinde)](#g%c3%b6r%c3%bcnt%c3%bc-vim-i%c3%a7erisinde)
- [Arşivleme ve Sıkıştırma](#ar%c5%9fivleme-ve-s%c4%b1k%c4%b1%c5%9ft%c4%b1rma)
    - [Arşivleri görüntüleme](#ar%c5%9fivleri-g%c3%b6r%c3%bcnt%c3%bcleme)
    - [Çıkartma](#%c3%87%c4%b1kartma)
- [Basit yükleme işlemleri](#basit-y%c3%bckleme-i%c5%9flemleri)
    - [RPM yüklemeleri](#rpm-y%c3%bcklemeleri)
    - [Debian paketlerinin yüklenmesi](#debian-paketlerinin-y%c3%bcklenmesi)
- [Cihazlar](#cihazlar)
    - [Takma /Çıkarma usb/floppy/cdrom](#takma-%c3%87%c4%b1karma-usbfloppycdrom)
- [Çevresel Değişkenler](#%c3%87evresel-de%c4%9fi%c5%9fkenler)
  [Vim Temelleri](#vim-temelleri)
    - [Temeller](#temeller)
    - [Yardım](#yardım)
    - [Dosya içerisinde gezme  (vim içerisinde)](#dosya-i%c3%a7erisinde-gezme-vim-i%c3%a7erisinde)
    - [Görüntü (vim içerisinde)](#g%c3%b6r%c3%bcnt%c3%bc-vim-i%c3%a7erisinde))
- [Arşivleme ve Sıkıştırma ](#arşivleme-ve-sıkıştırma)
    - [Arşivleri görüntüleme ](#arşivleri-görüntüleme)
    - [Çıkartma](#çıkartma)
- [Basit yükleme işlemleri](#basit-yükleme-işlemleri)
    - [RPM yüklemeleri](#rpm-yüklemeleri)
    - [Debian paketlerinin yüklenmesi](#debian-paketlerinin-yüklenmesi)
- [Cihazlar](#cihazlar)
    - [Takma /Çıkarma usb/floppy/cdrom](#takma-%c3%87%c4%b1karma-usbfloppycdrom)
- [Çevresel Değişkenler](#%c3%87evresel-de%c4%9fi%c5%9fkenler)


## Giriş

#### Neden Linux ?

  * Birden fazla işlemi aynı anda kolay şekilde yapmanızı sağlar 
  * Uzaktan işlemlerinizi halletmede büyük kolaylık sağlar
  * Birden fazla kullanıcı aynı sunucuya erişebilir
  * Terminale, bir sistem üzerinde olan kaynaklara birden fazla erişim mümkündür
  * Arayüz olan sistemlere göre daha performanslı, Bedava , Güncel

## Temeller
   
#### Bu bilgilendirme dosyası için not

   -  __Bütün komutlar büyük ve küçük harfe duyarlıdır.__ 

   -  ` "$" `komutun başlangıcını temsil eder.
   - ` "#" ` komutun sonunu temsil eder.

#### Windows bilgisayar üzerinden giriş için


   - __PuTTY__ : windows bilgisayar üzerinden SSH ile baglantı sağlamak için gereklidir.
   - __PuTTY__ programında SSH ile bağlantı için sunucu IP adresi ve PORT numarasını bilmelisiniz.

#### Mac veya Linux Bilgisayarlardan Erişim

    Bu tür bilgisayarlar UNIX tabanlı olduğundan dolayı terminal üzerinden aşağıda verilen komutları yazmanız yeterli olacaktır ekstradan herhangi bir programa gerek duyulmamaktadır. 

    {% highlight bash %}
        $ ssh <kullanıcı_adı>@<sunucu_adresi(IP)>
        $ kullanıcı_adı: ...
        $ şifre: ...
    {% endhighlight  %}

#### Giriş yaptıktan sonra şifrenizi değiştirmek isterseniz

    {% highlight bash %}
        $ passwd # bu komutu kullanabilirsiniz. bu komut sayesinde giriş yapılan kullanıcı için yeni şifre 
    {% endhighlight  %}


#### Listeleme

    {% highlight bash %}
        $ pwd # şu anda bulunduğunuz konumu çıktı olarak yazdırır
        $ ls # bulunduğunuz konumdaki dosyaları ve klasörleri listeler
        $ ll # ls komutunun eşdeşi olarak tanımlı bir ifadedir genelde "ls -alF" olarak kayıtlıdır bash profilinde

        $ ll -R # dosyalar/klasörler listelenir, klasörler içerisindeki dosyalarda listelenir
        $ ll -t # listeleme işlemi kronolojik şekilde gerçekleşir.
        $ stat <dosya_adı> # dosyaya ait bilgileri meta bilgileri listeler
        $ whoami # sizin sistem tarafından kim olduğunuzu söyler, yani kullanıcı adınızı listeler
        $ hostname # bağlı olduğunu makinenin URL ni yada IP sini gösterir
    {% endhighlight  %}

#### Dosyalar ve Klasörler

    {% highlight bash %}
        $ mkdir <klasör_adı> # belirlenen isimde klasör oluşturur
        $ cd <klasör_adı> # klasör adı tanımlanan klasöre gidersini.
        $ cd .. # üst klasöre gitmenizi sağlar
        $ cd ../../ # iki üst klasöre gitmenizi sağlar
        $ cd # ana klasörüne gidersiniz
        $ rmdir <klasör_adı> #  klasörü siler
        $ rm <dosya_adı> # dosyayı siler
        $ rm -r <klasör_adı> # klasörü ve içerisindeki bütün dosyaları siler
        $ mv <dosyaadı1> <dosyaadı2> # isim değiştirmenizi sağlar, name
        $ mv <dosyaadı> <taşınacak_yol> # dosyayı belirtilen yere taşır
        $ cp <dosyaadı> <kopyalanacak_yol> # dosyayı belirtilen yere kopyalar, eğer klasör kopyalanacak ise -r parametresi eklenir. 
    {% endhighlight  %}

## Kısayollar


    {% highlight bash %}
        $ . # sadece nokta bulunduğunuz dizini ifade eder
        $ ~/ # kullanıcının ana dizinini ifade eder
        $ history # yazmış olduğunuz komutların kaydını tutar ve bu komut ile erişebilirsiniz
        $ !<komut_sıralaması> # daha önce yazmış oldunuz komutu sıralamasının numarasını vererek calıştırabilirsiniz.
        $ yukarı(asagı)_okları # geçmiş komutlar arasında gezmenizi sağlar
        $ <tamamlanmamış_yol_veya_dosyaadı> TAB # Tab a bastığınızda sistem otomatik tamamlama işlemini gerçekleştirir.
        $ <tamamlanmamış komut> SHIFT&TAB # komutu otomatik tamamlar
        $ Ctrl a # imlecin en başa gitmesini sağlar
        $ Ctrl e # imlecin en sona gitmesini sağlar
        $ Ctrl d # imlec altındaki karakteri siler
        $ Ctrl k # imlecin bulunduğu sağlar
        $ Ctrl y # Ctrl k ile alınan içerik yapıştırılır.
    {% endhighlight  %}

## Yardım Alma

    {% highlight bash %}
        $ man # genel yardım
        $ man wc # wc komutu hakkında yardım almanızı sağlar
        $ wc --help # wc komutu hakkında yardım almanızı sağlar
        $ info wc # wc komutu hakkında detaylı bilgi almanız sağlanır
        $ apropos wc # wc komutuna ait bütün yardım dosyaları güncellenir.
    {% endhighlight  %}

## Aradığınız Dosyayı Bulma Yöntemleri

#### Arama yapmak


{% highlight bash %}
    $ find -name "*aramakistediğinizdesen*" # girdiğiniz desene göre bulunduğunuz dizinde arama yapmanızı sağlar.
    $ find /usr/local -name "*klas*" # isminin içerisinde klas geçen dosyaları ve klaksörleri listeler.
    $ find /usr/local -iname "*klas*" # yukarıdaki komutuna benzer şekilde, isminin içerisinde klas geçen dosyaları ve klasörleri listeler fakat bu durumda büyük veya küçük harfte olması dikkate alınmaz

    $ find ~ -type f -mtime -2 # 2 gün içerisinde değiştirilmiş bütün dosyaları listeler
    $ locate <aramakistediğinizdesen> # aradığınız dosyayı veya klasörü sistem genelinde arar.
    $ which <uygulama_adı> # uygulamanın nerede bulunduğunu gösterir
    $ whereis <uygulama_adı> # uygulamanın çalıştırılabilir dosyasının yerini gösterir
    $ dpkg -l | grep aramakistediğinizpaketismi # Debian paketleri içerisinde arama yaparak verilen desende bulunan paketleri listel
{% endhighlight  %}

#### Dosya içerisinde arama yapmak

    {% highlight bash %}
        $ grep aranan_kelime dosya # dosya içerisinde aranan kelimenin nerelerde geçtiğini size aktarır
        $ grep -H aranan_kelime # -H çıktı dosyasını aranan kelimenin önüne koyar
        $ grep 'aranan_kelime' dosya | wc  # burada iki komut birleştirilmiştir, yani grep komutunun çıktısı wc komutuna girdi olmaktadir yani aranan kelime verilen dosyada 5 kere geçiyor ise bu durumda sonuc 5 olarak dönmektedir. 
        $ find /home/kullanıcı_adı -name '*.txt' | xargs grep -c ^.* # verilen dizinde txt dosyalarını bularak bu dosyalar içerisindeki satır sayısını hesaplayarak çıktı vermektedir. 
    {% endhighlight  %}


## İzinler & Hak Sahipliği


{% highlight bash %}
        $ ls -al # bu komut çalıştırıldıgında buna benzer bir çıktı görünebilir : drwxrwxrwx
{% endhighlight  %}

Burada bahsi geçen harflerin anlamları aşağıdaki gibi verilebilir.
  - __d:__ dizin
  - __rwx:__ oku, yaz, çalıştır
  - __ilk üçlü (rwx)__ : kullanıcı izinleri(u)
  -  __ikinci üçlü__: grup izinleri (g)
  -  __üçüncü üçlü__: diğer izinleri (o) ifade etmektedir. 
__En başta d olursa bu o dosyanın aslında bir klasör olduğunu ifade etmektedir.__

Kullanıcı ve grupa, yazma ve çalıştırma izni vermek:

    {% highlight bash %}
        $ chmod ug+rx dosya_ismi    
    {% endhighlight  %}

#### Kullanıcı haklarının alınması


    {% highlight bash %}
    
        $ chmod ugo-rwx dosya_ismi

        '+' izin eklemeyi sağlar
        '-' izin silmenizi sağlar

        $ chmod +rx dosya_ismi/ VEYA $ chmod 755 dosya_ismi/

    {% endhighlight  %}

#### Hak sahipliğinin değiştirilmesi 

    {% highlight bash %}
        $ chown <kullanıcı_adı> <dosya veya klasör> # kullanıcı hak sahibini değiştirir
        $ chgrp <grup> <dosya veya klasör> # grup hak sahibini değiştirir
        $ chown <kullanıcı_adı>:<grup> <dosya veya klasör> # kullanıcı ve grup hak sahipliğini değiştirir
    {% endhighlight  %}


## Kullanışlı Linux Komutları

    {% highlight bash %}
        $ df # sistem diskinin ne kadar dolu ve boş olduğu bilgisini gösterir
        $ free # ne kadar önbellek (RAM) alanının boş/dolu olduğunu gösterir
        $ uname -a # işletim sistemine ait temel bilgileri gösterir
        $ bc # terminal üzerinden hesap makinesi kullanmanızı sağlar
        $ /sbin/ifconfig # sunucunun ağ bilgilerini listeler.
        $ ln -s orjinal_dosyaismi yeni_dosyaismi # orjinal dosyaya link oluşturur
        $ du -sh # bulunduğunuz konumdaki disk kullanım bilgilerini listeler
        $ du -sh * # bulunduğunuz konumdaki dosyaların/klasörlerin kullanım bilgilerini gösterir
        $ du -s * | sort -nr # sıralanmış şekilde dosyaların/klasörlerin kullanımlarını listeler
    {% endhighlight  %}


## İşlem Yönetimi 

{% highlight bash %}
    $ who # sisteme kimin girdiğini gösterir
    $ w # sistemde kimlerin olduğunu gösterir
    $ ps # arka planda çalışan işlemler hakkındaki bilgileri listeler.
    $ ps -e # sistemdeki bütün işlemleri listeler
    $ ps aux | grep <kullanıcı_adı> # kullanıcıya ait çalıştırılan işlemleri listeler
    $ top # CPU ve RAM değerlerinin kullanım bilgilerini gösterir
    $ mtop # birden fazla CPU için top komutunun yaptığını yapar
    $ Ctrl z <enter> bg or fg <enter> # çalışan işlemleri durdurur, arka plana atar (bg) veya ön plana getirir (fg)
    $ Ctrl c # yeni başlamış olan işlemi durdurur
    $ kill <işlem_no> # belirlenen işlemi sonlandırır, işlem ID sine göre belirlenir
    $ renice -n <önemlilik_değeri> # işlemin önemlilik değerini değiştirmenizi sağlar 
{% endhighlight  %}

## Text dosyalarını okumak


    {% highlight bash %}
        $ less <dosya_ismi> # belirtilen dosyayı terminal üzerinden okumanızı sağlar G :dosyanın sonuna gider, g : dosyanın başına gider. 
        $ more <dosya_ismi> # dosya içeriğini gösterir çıkmak için q ya basılması gereklidir.
        $ cat <dosya_ismi> #dosya içeriğini terminale yazdırır
    {% endhighlight  %}

## Metin Düzenleyicileri

#### VI ve VIM
Terminal tabanlı güçlü metin düzenleyicidir. Vi genelde linux tabanlı bütün sistemlerde mevcuttur, vim, vi nin gelişmişidir. 

#### EMACS
Grafik tabanlı metin düzenleyicidir. Bu düzenleyiciye ait olan klavye düzeni hakkında bilginiz olmalıdır. Bütün linux ve unix tabanlı sistemlerde mevcuttur. 

#### XEMACS
EMACS in çok daha gelişmişidir, yazım hataları, web ve metini iyi bir şekilde kontrol etmek mümkündür fakat normalde yüklenmiş olmaz. 

#### PICO
Terminal tabanlı basit metin düzenleyicidir, buna ait klavye düzeni bilinmelidir. 

## VIM Temelleri

#### Temeller 

    {% highlight bash %}
        $ vim dosya_ismi # dosya_ismin de dosya oluşturur veya yazma modunda açar
        $ i # vim 'in içerisine girdikten sonra i açık olan dosyaya bir şeyler yazmanıza olanak sağlar.
        $ ESC # dosya düzenleme modundan çıkılır
        $ : # vim içerisinde kullanacağınız komutlar : ile başlar
        $ :w # vim içerisinde :w yaptığınızda yazdığınızı kaydeder.
        $ :q # bu komut vim den çıkmanızı sağlar
        $ :q! # hiç birşeyi kaydetmeden çıkmanızı sağlar.
        $ :wq # kaydederek çıkar
        $ R # vim içerisinde özellik değiştirmenizi sağlar
        $ r # imlecin bulunduğu karakteri değiştirmenizi sağlar
        $ q: # vim içerisinde yazdığınız komutların kaydını gösterir
        $ :w yeni_dosyaadı # yeni dosyaya kaydeder.
        $ :#,#w yeni_dosyaadı#  belirlenen (#,#)  aralıktaki metini yeni dosyaya kaydeder.
        $ :#  belirlenen (#) satıra gitmenizi sağlar
    {% endhighlight  %}


#### Yardım

    {% highlight bash %}
        $ vimtutor # vim içerisinde nasıl çalıştığına dair bilgileri içeren tur başlatılır.
        $ :help # vim içerisinde yardım açar, çıkmak için q komutu kullanılır.
        $ :help <konu> # belirlenen konu hakkında yardım açar
        $ :help <konu> CTRL-D # belirlenen konunun geçtiği bütün yardım dökümanını listeler.
        $ :<yukarı-asagı tusları> # daha önceki yaptığınız komutlar arasında gezmenizi sağlar.
    {% endhighlight  %}


#### Dosya içerisinde gezme  (vim içerisinde)

        {% highlight bash %}
            $ $ # bulunduğunuz satırın en sonuna gider
            $ A # bulunduğunuz satırın en sonuna yazma modunu açarak gider
            $ 0 (sıfır) # satırın başlangıcına gider
            $ CTRL-g # imlecin nerede olduğu ve o satır hakkında bilgi verir
            $ SHIFT-G # imleci dosyanın en sonuna getirir
        {% endhighlight  %}

#### Görüntü (vim içerisinde)

        {% highlight bash %}
            
            WRAPPING AND LINE NUMBERS

            $ :set nowrap # kelimelerin kaymamalarını sağlar
            $ :set number # satır numaralarını gösterir
        {% endhighlight  %}

## Arşivleme ve Sıkıştırma 

    {% highlight bash %}
        $ tar -cvf dosya_ismi.tar klasör/ # verilen klasör için arşiv oluşturur
        $ tar -czvf dosya_ismi.tgz klasör/ # verilen klasör için arşivlenmiş ve sıkıştırılmış dosya oluşturur. 
    {% endhighlight  %}

#### Arşivleri görüntüleme 

    {% highlight bash %}
        $ tar -tvf dosya_ismi.tar
        $ tar -tzvf dosya_ismi.tgz 
    {% endhighlight  %}

#### Çıkartma

    {% highlight bash %}
        $ tar -xvf dosya_ismi.tar
        $ tar -xzvf dosya_ismi.tgz
        $ gunzip dosya_ismi.tar.gz  
        $ tar zxf blast.linux.tar.Zs
    {% endhighlight  %}

## Basit yükleme işlemleri 

#### RPM yüklemeleri 

    {% highlight bash %}
        $ rpm -i uygulama_ismi.rpm
        $ rpm --query <paket_ismi> ## RPM versiyonunu kontrol etme için
    {% endhighlight  %}
    
#### Debian paketlerinin yüklenmesi


    {% highlight bash %}
        $ apt-cache search nmap # nmap adındaki uygulamayı debian deposundan arama yapar
        $ apt-cache show nmap # nmap hakkında tanımlamayı(bilgi) gösterir
        $ apt-get install nmap  # nmap 'i sisteme kurar.
        $ apt-get update # sistemdeki uygulamaları ve servisleri günceller
        $ apt-get upgrade -u #  uygulamaların yeni versiyonu var ise yükseltme yapar
        $ dpkg -i dosya.deb # indirilen debian dosyasının yüklenmesini sağlar
        $ aptitude # apt-get ile aynı işlemi görür
        $ aptitude search vim #  vim programını debian deposunda arar 
    {% endhighlight  %}

## Cihazlar

#### Takma /Çıkarma usb/floppy/cdrom


    {% highlight bash %}
        $ mount /media/usb
        $ umount /media/usb
        $ mount /media/cdrom
        $ eject /media/cdrom
        $ mount /media/floppy
    {% endhighlight  %}

## Çevresel Değişkenler 

    {% highlight bash %}
        $ xhost user@host # kullanıcı için çalıştırma izini ekler
        $ echo DISPLAY # ekranın ayarlarını gösterir
        $ export (setenv) DISPLAY=<lokal_IP>:0 # görüntü değişkeninin değerini değiştirir
        $ unsetenv DISPLAY # görüntü değişkenini siler
        $ printenv # kullanılan çevresel değişkenleri listeler
        $ $PATH # terminal üzerinde programların çalışmasını sağlayan yolları gösterir.
    {% endhighlight  %}

