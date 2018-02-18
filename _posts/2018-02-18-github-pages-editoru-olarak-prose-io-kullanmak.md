---
layout: post
published: true
date: '2018-02-18 22:25 +0300'
excerpt_separator: <!--more-->
title: 'Github Pages Editörü Olarak Prose.io Kullanmak '
tags:
  - Github Pages
  - Jekyll
  - Prose.io
categories:
  - web-uygulamalari
---
Aşağıda örnek prose.io ekran görüntüsünü yer almaktadır.

![prose.io yazı editörü]({{site.baseurl}}/assets/media/prose.io-yazi-editoru.PNG)

Merhaba arkadaşlar. Github Pages ile yazı yazmaya başladıltan sonra yazı yazmak için bir yazı editörü ihtiyacı doğdu. Araştırmalarım sonucu değişik ücretli ve ücretsiz uygulamalar içinden **prose.io** nun bu iş için biçilmiş kaftan olduğunu gördüm. İlk önceleri çok kullanışlı değil gibi gelmişti. Sonradan farkettim ki prose.io ile ilgili _config.yml dosyasında yaptığımız ayarlar ile prose.io oldukça kullanışlı hale gelmekte.

<!--more-->

Prose.io ile resim eklemek oldukça kolay. Daha önde eklenilen resimlerin sağ tarafta yer alması resim ekelemede sıkıntı yaşayan Github Pages kullanıcılarının işini oldukça kolaylaştıracaktır.

![prose.io ile resim ekleme]({{site.baseurl}}/assets/media/prose.io-ile-resim-ekleme.PNG)

Yazınıza belli başlı metatag alanlarının doğrudan eklenmesini sağlayıp yazıya odaklanabilirsiniz. Örnek bir prose.io ayarı şu şekilde (tabi ki siz aşağıda paylaştığımız kaynaklar ile çok daha detaylı ayarlar yapabilirsiniz):

```yaml
# languages: &languages
#  - name: 'Türkçe'
#    value: 'tr'
#  - name: 'İngilizce'
#    value: 'en'  
    
prose:
  rooturl: "_posts"
  siteurl: "https://erata.github.io/"
  relativeLinks: 'https://erata.github.io/links.jsonp'
  media: 'assets/media'
  #ignore: ['CNAME', '_config.yml', '*.json', '.gitignore', 'readme.md', '*.xml', 'admin.html']
  metadata:
    _posts:
    #  - name: "lang"
    #    field:
    #      element: "select"
    #      label: "Select language"
    #      placeholder: "Tükçe"
    #      options: *languages
    #      selected: "tr"
      - name: "published"
        field:
          element: "checkbox"
          label: "Publish now"
          help: "Keep this unchecked if you do not want to   publish the article right now"
          value: "true"
      - name: "layout"
        field:
          element: "hidden"
          label: "Layout"
          value: "post"
      - name: "title"
        field:
          element: "text"
          label: "Enter title of the Article"
          placeholder: "Enter Title"
      - name: "date"
        field:
          element: "text"
          label: "Date"
          value: "CURRENT_DATETIME"
   #   - name: "author"
   #     field:
   #       element: "hidden"
   #       value: "Aybüke Erata"
      - name: "categories"
        field:
          element: "multiselect"
          label: "Add Category"
          placeholder: "Add Category"
          options:
            - name: "Bilgi Güvenliği"
              value: "Bilgi Güvenliği"
            - name: "Linux/Bash Script"
              value: "Linux/Bash Script"  
            - name: "Mobil Programlama"
              value: "Mobil Programlama"
            - name: "Diğer"
              value: "Diğer"  
          alterable: true
     #   field:
     #     element: "hidden"
     #     value: "blog"
     #     alterable: "true"
      - name: "tags"
        field:
          element: "multiselect"
          label: "Add Tags"
          placeholder: "Add Tags"
          options:
            - name: "Android"
              value: "Android"
            - name: "KALI"
              value: "KALI"  
            - name: "Program İnceleme"
              value: "Program İnceleme"   
          alterable: true
      - name: "excerpt_separator"
        field:
          element: "text"
          value: "<!--more-->" 
```         

Yazıyı yayınlama düğmesine yıkladığınızda aşağıdaki yazı inceleme ekranı ve sağ tarafında yayınlama düğmesi (commit) görünecektir.

![prose.io-ile-yaziyi-yayinlama]({{site.baseurl}}/assets/media/prose.io-ile-yaziyi-yayinlama.PNG)

Umarım yararlı olmuştur.

### Kaynaklar ve Örnek prose.io ayarları
- [https://github.com/prose/prose/wiki/Getting-Started](https://github.com/prose/prose/wiki/Getting-Started)
- [https://github.com/prose/prose/wiki/Prose-Configuration](https://github.com/prose/prose/wiki/Prose-Configuration)
- [https://github.com/MailTape/MailTape.github.io/blob/master/_config.yml](https://github.com/MailTape/MailTape.github.io/blob/master/_config.yml)
- [https://github.com/PanicInitiative/panicbutton.io/blob/master/_config.yml](https://github.com/PanicInitiative/panicbutton.io/blob/master/_config.yml)
- [https://github.com/web-being/proakpp/blob/master/_config.yml](https://github.com/web-being/proakpp/blob/master/_config.yml)
