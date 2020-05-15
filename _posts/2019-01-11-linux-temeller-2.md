---
title: "vim 🇹🇷"
lay out: post
date: 2019-01-11 09:04
image: /assets/images/Icon-Vim.svg
headerImage: true
tag:
- linux
- terminal
- komut
- vim
- nftp
- wget
- scp
- html
category: blog
author: mrturkmen
description: Linuxa başlamak ve basit komutları ögrenmek
---

## Özet

Terminal üzerinden kullanılan en meşhur yazı düzenleme programı VIM hakkında komutlar ve bazı kullanışlı linux komutları


- [Özet](#%c3%96zet)
- [Script nasıl yazılır.](#script-nas%c4%b1l-yaz%c4%b1l%c4%b1r)
- [VIM](#vim)
    - [Birden fazla dosya üzerinde çalışmak](#birden-fazla-dosya-%c3%bczerinde-%c3%a7al%c4%b1%c5%9fmak)
    - [Hece Kontrolü & Sözlük](#hece-kontrol%c3%bc--s%c3%b6zl%c3%bck)
    - [Dosyayı yazdırma](#dosyay%c4%b1-yazd%c4%b1rma)
    - [Birleştime / Ekleme Komutu](#birle%c5%9ftime--ekleme-komutu)
    - [Geri Alma / Yeniden Alma](#geri-alma--yeniden-alma)
    - [Kopyalama & Yapıştırma](#kopyalama--yap%c4%b1%c5%9ft%c4%b1rma)
    - [Silme/Kesme (NORMAL modda uygulanır. Yani Vim komut satırında değil. EXE modunda değil. )](#silmekesme-normal-modda-uygulan%c4%b1r-yani-vim-komut-sat%c4%b1r%c4%b1nda-de%c4%9fil-exe-modunda-de%c4%9fil)
    - [Dosya içerisinde arama (Vim) (bu kısımda genelde düzenli ifadeler kullanılır )](#dosya-i%c3%a7erisinde-arama-vim-bu-k%c4%b1s%c4%b1mda-genelde-d%c3%bczenli-ifadeler-kullan%c4%b1l%c4%b1r)
    - [Düzenli ifadeler ile metin yönetimi](#d%c3%bczenli-ifadeler-ile-metin-y%c3%b6netimi)
    - [HTML Düzenleme](#html-d%c3%bczenleme)
    - [Vim içerisinden terminal komutu çalıştırma](#vim-i%c3%a7erisinden-terminal-komutu-%c3%a7al%c4%b1%c5%9ft%c4%b1rma)
    - [Tablo düzenleyicisi olarak Vim' i kullanmak](#tablo-d%c3%bczenleyicisi-olarak-vim-i-kullanmak)
    - [Vim ayarlarını değiştirmek](#vim-ayarlar%c4%b1n%c4%b1-de%c4%9fi%c5%9ftirmek)
- [Kullanışlı terminal komutları](#kullan%c4%b1%c5%9fl%c4%b1-terminal-komutlar%c4%b1)
    - [Kullanışlı tek satır komutlar](#kullan%c4%b1%c5%9fl%c4%b1-tek-sat%c4%b1r-komutlar)
    - [Basit Perl Komutları](#basit-perl-komutlar%c4%b1)
    - [WGET (terminal üzerinden linki verilen dosya indirimini gerçekleştirir.)](#wget-terminal-%c3%bczerinden-linki-verilen-dosya-indirimini-ger%c3%a7ekle%c5%9ftirir)
    - [SCP (İki makine arasında güvenli kopyalama işlemi sağlar. )](#scp-%c4%b0ki-makine-aras%c4%b1nda-g%c3%bcvenli-kopyalama-i%c5%9flemi-sa%c4%9flar)
    - [NFTP : (Dosya transfer işlemlerinizi kolay şekilde terminal üzerinden yapmanızı sağlar )](#nftp--dosya-transfer-i%c5%9flemlerinizi-kolay-%c5%9fekilde-terminal-%c3%bczerinden-yapman%c4%b1z%c4%b1-sa%c4%9flar)



## Script nasıl yazılır.

* Dosya oluşturulur ve dosyanın başına terminalin yolu eklenir `#!/bin/bash`
*  terminal komutlarını bu yolun altına yazınız.
* daha sonra dosyanın iznini ayarlayınız. chmod +x dosya_ismi
* terminal scriptini şu şekilde çalıştırılabilirsiniz. ./dosya_ismi

* örnek bash scripti

{% gist mrturkmen06/76b9ab5cdd10874d79ade7ceef69ef6f %}

## VIM


#### Birden fazla dosya üzerinde çalışmak 

{% highlight bash %}
$ vim *.txt # birden fazla txt ile dosyasını aynı anda açmanızı sağlar (eğer birden fazla dosya mevcut ise)
$ :wall veya :qall # bütün açık dosyalardan yaz veya çık komutudur.
$ vim -o *.txt # birden fazle txt dosyasını açar ve yatay düzlemde gösterir, dikey düzlem için -O parametresi kullanılara
$ :args *.txt # txt ile biten bütün dosyaları argument listesine aktarır.
$ :all # bütün dosyaları yatay düzlemde ayırır
$ CTRL-w # birden fazla pencere arasında gezmenizi sağlar
$ :split # aynı dosyayı iki farklı pencerede gösterir.
$ :split <acılacak_dosya> # dosyayı yeni bir pencerede açar
$ :vsplit # brden fazla pencereyi dikey komunda ayırır, tablolar için çok kullanışlıdır. ":set scrollbind " komutu ile açık dosyalar da aynı anda yukarı aşağı yapabilirsiniz. 
$ :close # bulunduğunuz pencereyi kapatır
$ :only # bulunduğunuz pencere hariç diğerlerinin tamamını kapatır. 
{% endhighlight  %}   

#### Hece Kontrolü & Sözlük 

{% highlight bash %}
$ aspell -c <dosya> # verilen dosyada heceleri kontrol eder, terminal komutudur
$ aspell -l <dosya> # terminal komutu
$ :! dict <cumle> # cümlenin anlamını kontrol etmenizi sağlar
$ :! wn 'cumle' -over # cümlenin eş anlamlılarını gösterir
{% endhighlight  %}   

  
#### Dosyayı yazdırma 
{% highlight bash %}
 $ :ha # bütün dosyayı yazdırır
 $ :#,#ha # (#,#) ile belirtilen alandaki metini yazdırır
{% endhighlight %}
#### Birleştime / Ekleme Komutu 
{% highlight bash %}
 $ :r <dosya_ismi> # açık olan dosya içerisine,
                   # aynı dizinde olan başka bir dosyayı eklemek için bu komut kullanılabilir,
                   # imlecin hizasından sonra ekleme yapar
{% endhighlight %}
#### Geri Alma / Yeniden Alma 
 {% highlight bash %}
 $ u # en son yaptığınız değişikliği geri alır
 $ U # yaptığınız bütün değişiklikleri geri alır
 $ CTRL-R # geri alınmış bir kısmı yeniden getirmenizi sağlar.
 {% endhighlight %}

#### Kopyalama & Yapıştırma
 {% highlight bash %}
 $ yy # imlecin bulunduğu satırı kopyalar, 2 satır kopyalamak için 2yy kullanılabilir.
 $ p # kesilen/kopyalanan içeriği imleçten başlayacak şekilde yapıştırır 
 {% endhighlight %}

#### Silme/Kesme (NORMAL modda uygulanır. Yani Vim komut satırında değil. EXE modunda değil. )
 {% highlight bash %}
 $ x # imlecin üzerinde bulunduğu karakteri siler.
 $ dw # imlecin bulunduğu kelimeyi sonuna kadar siler (Boşluklar dahil )
 $ de # imlecin bulunduğu kelimeyi sonuna kadar siler (Boşluklar hariç )
 $ cw # kelimenin geriye kalan kısmını siler ve sizi ekleme moduna alır, ekleme modundan ESC ile çıkabilirsiniz.
 $ c$ #  bulunduğu satırı tamamen siler ve sizi ekleme moduna alır ekleme modundan ESC ile çıkabilirsiniz. 
 $ d$ # imlecten itibaren satırı siler e
 $ dd # satırı tamamen siler, imlecin nerede olduğunun önemi yoktur
 $ 2dd # ileriki 2 satırı siler, benzer sekilde 3dd : uc satır siler, 4dd: dort satır siler, (imlecten bagımsız)
    Koyma  

 $ p # kesilen/kopyalanan içeriği imleçten başlayacak şekilde yapıştırır 
 {% endhighlight %}

#### Dosya içerisinde arama (Vim) (bu kısımda genelde düzenli ifadeler kullanılır )
 {% highlight bash %}
 $ /aramak_istediğiniz_düzen # yazdığınız ifadeyi açık olan belge içerisinde arar ve hepsini işaretler
 $ ?aramak_istediğiniz_düzen # yazdığınız ifadeyi açık olan belge içerisinde arar ama işaretlemez, n ile ileriki kelimeyi görebilirsiniz. 
 $ :set ic # kelimelerin büyük/küçük harf ayrımını ortadan kaldırır
 $ :set hls # aranan ve bulunan kelimeleri vurgulu şekilde gösterir.
{% endhighlight %}

#### Düzenli ifadeler ile metin yönetimi 
 {% highlight bash %}
 $ :s/harf1/harf2/ # harf1, harf2 ile değiştirilir fakat sadece ilk karşılaşmada yapılır
 $ :s/harf1/harf2/g # bütün dosya içerisindeki harf1, harf2 ile değiştirilir.
 $ :s/harf1/harf2/gc # yukarıdaki işlemin aynısını onay alarak yapmak için "c" eklenir
 $ :#,#s/harf1/harf2/g #  (#,#) arasındaki satırlarda bulunan harf1, harf2 ile değiştirilir.
 $ :%s/harf1/harf2/g # tüm dosyadaki harf1 ifadesi harf2 ile değiştirilir.
 $ :%s/\(harf1\)\(.*\)/\1/g # harf1 sonrakisindeki bütün satırları siler.
 $ :%s/\(SL\dm\d\d\d\d\d\.\d\)\(.*\)/\1\t\2/g #  SL1m12345.1 ve tanımı arasına TAB boşluğu ekler 
 $ :%s/\n/ifade/g #Satır verilen ifade ile değiştirilir.
 $ :%s/\(^SL\dm\d\d\d\d\d.\d\t.\{-}\t.\{-}\t.\{-}\t.\{-}\t\).\{-}\t/\1/g  #  5 ve 6.ncı TAB taki (5. Kolondaki), içeriği "{-}" ile degiştirir. 
 $ :#,#s/\( \{-} \|\.\|\n\)/\1/g # (#,#) verilen aralıkta ne kadar cümle olduğunu hesaplar
 $ :%s/\(E\{6,\}\)/<font color="green">\1<\/font>/g # 6 dan fazla E geçen kısımları, HTML renkleri ile vurgular.
 $ :%s/\([A-Z]\)/\l\1/g # Büyük harfleri, küçük harfler ile değiştirir, '%s/\([A-Z]\)/\u\1/g' , bu ise küçük harfleri büyük harfler ile değiştirir.
 $ :g/ifade/ s/\([A-Z]\)/\l\1/g | copy $ # ifade yeni oluşturulan ifade ile değiştirilir eşdeğer olanlar copy $ ile yazdırılır. 
 {% endhighlight %}
#### HTML Düzenleme 
 {% highlight bash %}
 -metini HTML formatına cevirme
 $ :runtime! syntax/2html.vim # vim içerisinde bu komutu çalıştırınız.
 {% endhighlight %}
#### Vim içerisinden terminal komutu çalıştırma 
 {% highlight bash %}
 $ :!<terminal_komutu> <ENTER> # terminal komutunu vim içerisinden çalıştırır
 $ :sh terminal ile vim arasında gezmenizi sağlar
 {% endhighlight %}
#### Tablo düzenleyicisi olarak Vim' i kullanmak 
 {% highlight bash %} 
 $ v # karakterleri seçmek için görsel mod başlatılır.
 $ V # satırları seçmek için görsel mod başlatılır.
 $ CTRL-V # blok görsel seçim yapmanızı sağlar.
 $ :set scrollbind # aynı ayna ayrılan iki ayrı dosyada gezinti yapmanızı sağlar. 
  {% endhighlight %}

####  Vim ayarlarını değiştirmek 
 
   __- .vimrc dosyası içerisindeki parametreler isteğinize göre değiştirilebilir.__


## Kullanışlı terminal komutları
{% highlight bash %}
 $ cat <dosya1> <dosya2> > <sonuc> # dosya1 ve dosya2 yi sonuc dosyasina kopyalar ve sonuc dosyasini olusturur.
 $ paste <dosya1> <dosya2> > <p_sonuc> # iki farklı kaynaktan gelen girdiyi, aralarında TAB boşluğu olacak şekilde aynı dosya (p_sonuc) içerisine yapıştırır.
 $ cmp <dosya1> <dosya2> # iki dosyanın aynı olup olmadıgını size bildirir.
 $ diff <dosya1> <dosya2> # iki dosya arasındaki farklılıkları gösterir
 $ head -<numara> <dosya> # verdiğiniz numara kadar ilk X satırı yazdırır.
 $ tail -<numara> <dosya> # verdiğiniz numara kadar son X satırı yazdırır. 
 $ split -l <numara> <dosya> # dosyanın satırılarını ayırır.
 $ csplit -f out dosya_ismi "%^>%" "/^>/" "{*}" # dosya_ismini > den itibaren birçok farklı küçük dosyalar oluşturur.
 $ sort <dosya_ismi> # dosya içerisindekileri sıralar -b argument kullanılırsa boşlukları yok sayar.
 $ sort -k 2,2 -k 3,3n girdi_dosyası > cıktı # -k argument i kolon için, -n sayısal olarak sıralar ve tablo şeklinde kaydeder. 
 $ sort girdi_dosyası | uniq > cıktı # uniq komutu aynı olan verileri dahil etmez.
 $ join -1 1 -2 1 <tablo1> <tablo2> #  tablo1 ve tablo2 yi birleştirir, -1 dosya1, 1:kolon1; -2dosya2, col2. 
 $ sort tablo1 > tablo1a; sort tablo2 > tablo2a; join -a 1 -t "`echo -e '\t'`" tablo1a tablo2a > tablo3 # '-a <tablo>' : verilen tablonun bütün kayıtlarını yazdırır.  Normalde yazdırma işlemi iki tabloda ortak olan kısımları yazdırır.  '-t "`echo -e '\t'`" ->' 
 : TAB boşluğu kullanarak tabloları çıktı dosyasına yazdırır. 
 $ cat tablom | cut -d , -f1-3 # cut komutu : tablonun belirlenen kısımları alır, -d alanların nasıl ayrılacağını belirtilsiniz. -d : burada , olarak belirlenmiştir, normalde TAB boşluk, -f tablonun kolonlarını belirtir, kolon 1 den 3 e. 
{% endhighlight  %}


#### Kullanışlı tek satır komutlar 

{% highlight bash %}
 $ for i in *.input; do mv $i ${i/isim\.eski/isim\.yeni}; done # isim.eski adındaki dosyanın ismini, isim.yeni olarak değiştirir. Komutu test etmek için,  do mv komutu önüne "echo" konulabilir.  
 $ for i in *.girdi; do ./uygulama $i; done #  bir çok dosya için verilen uygulamayı çalıştırır. 
 $ for i in *.girdi; do komut -d /veri/../veri_tabanı -i $i > $i.out; done #  komut for döngüsü içerisinde *.girdi üzerinde çalışır ve *.out dosyası oluşturur. 
 $ for i girdi *.pep; do hedef -db /usr/../veri_tabanı -seed $i -out $i; done # hedef in üzerinde for döngüsü çalıştırılır ve çıktı dosyası yazdırılır.
 $ for j girdi 0 1 2 3 4 5 6 7 8 9; do grep -iH <ifade> *$j.seq; done # 
 verilen ifadeyi girdi > 10.000 dosyaya kadar arar ve ne kadar o ifade geçtiğini yazdırır.
 $ for i in *.pep; do echo -e "$i\n\n17\n33\n\n\n" | ./program $i > $i.out; done # etkileşimli programı çalıştırır ve girdi/çıktı sorar. 
{% endhighlight  %}


#### Basit Perl Komutları 

{% highlight bash %}
 $ perl -p -i -w -e 's/ifade1/ifade2/g' girdi_dosyası #  girdi dosyası içerisindekileri verilen ifadelere göre değişimini yapar. '-p'  bu komut yedek bir dosya oluşturur 
 $ perl -ne 'print if (/ifade1/ ? ($c=1) : (--$c > 0)) ; print if (/ifade2/ ? ($d = 1) : (--$d > 0))' girdi_dosyası > cıktı_dosyası # ifade1 ve ifade2 içeren satırları ayrıştırır (parse eder.)  
{% endhighlight %}


#### WGET (terminal üzerinden linki verilen dosya indirimini gerçekleştirir.)

{% highlight bash %}
 $ wget ftp://ftp.itu.edu.tr.... # verilen linkteki dosya wget komutunun çalıştırıldığı dizine iner. 
{% endhighlight %}


#### SCP (İki makine arasında güvenli kopyalama işlemi sağlar. )

{% highlight bash %}
 Genel Kullanım.
 $ scp kopyalanacak_dosya kopyalanacak_yer #
 Örnekler 
 Sunucudan dosya kopyalamak için (bilgisayarınızın terminalinden)
 $ scp kullanıcı@sunucu_ip:dosya_adı . # '.'  en sona nokta koyulması, sunucu üzerindeki kopyalanacak dosyayı bulunduğunuz yere kopyalamasını sağlar. 
 Bilgisayarınızdan sunucuya kopyalama yapmak için. (Bilgisayar terminalinden)
 $ scp resim.jpg kullanıcı@sunucu_ip:~/belgeler/resimler/
 Sunucu üzerinde bulunan klasörü bilgisayarımıza kopyalamak için. (Bilgisayar terminalinden)
 $ scp -r kullanıcı@sunucu_ip:dizin/ ~/Masaustu
 Bilgisayar üzerinde bulunan klasörü sunucuya kopyalamak için. (Bilgisayar terminalinden)
 $ scp -r klasör/ kullanıcı@sunucu_ip:dizin/
  {% endhighlight  %}

#### NFTP : (Dosya transfer işlemlerinizi kolay şekilde terminal üzerinden yapmanızı sağlar )

{% highlight bash %}
 $ open ncftp
 $ ncftp> open sunucu_url  # sunucuya baglantı sağlanıyor..
 $ ncftp> cd /root/Masaustu. # masaustune gecildi
 $ ncftp> get resimler.gz    # masaustunde bulunan resimler.gz indirildi.
 $ ncftp> bye    # gule gule mesajı alındı
{% endhighlight %}

