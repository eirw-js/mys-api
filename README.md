Mys API

Mys API, kullanıcılara çeşitli bilgilere erişim sağlayan bir API'dir. Farklı endpointler aracılığıyla veriler sunar ve çeşitli hizmetler sağlar.

API Hakkında

Mys API, günlük yaşamda ihtiyaç duyulan çeşitli bilgilere erişim sağlar. Hava durumu, burç yorumları, döviz kurları ve namaz vakitleri gibi çeşitli hizmetler sunar. Aynı zamanda Discord kullanıcılarının bilgilerini analiz etme (stalklama) yeteneği ile öne çıkar.

Kullanım

API'yi kullanmak için aşağıdaki örnek endpointler mevcuttur:

/user/{id} - Kullanıcı Bilgisi

/burc/{isim} - Burç Bilgisi

/gunlukburc/{isim} - Günlük Burç Bilgisi

/haftalikburc/{isim} - Haftalık Burç Bilgisi

/aylikburc/{isim} - Aylık Burç Bilgisi

/weather/{isim}/ - Hava Durumu Bilgisi

/iltifat - İltifat

/doviz - Döviz Kuru Bilgisi

/namaz/{sehir}/{ilce} - Namaz Vakitleri

/nsfw - NSFW İçerik


Daha fazla endpoint ve kullanım bilgisi için API Dökümantasyonu sayfasını ziyaret edebilirsiniz.

NPM Paketi ile Veri Çekmek

NPM Paketi: mys-api.js

Veri Çekme Örneği

Aşağıda, Axios kullanarak API'den veri çekmek için bir örnek bulunmaktadır. API anahtarınızı ve apiUrl'yi ilgili alanlara ekleyerek kullanabilirsiniz.

`const axios = require('axios');`

`async function fetchData() {`
    `const apiKey = 'test'; // API anahtarınızı buraya ekleyin`
    `const apiUrl = https://discordpanel.vercel.app/api/user/{id}`; // İstek atılacak API URL'sini belirtin`
    
    try {
        const response = await axios.get(apiUrl);
        
        console.log("İstek Başarılı!", response.data);

        const otherNames = response.data["GuildsDisplayNames"].map((x) => x).join("\n");
        console.log(otherNames);
    } catch (error) {
        console.error('Hata:', error);
    }
`}`

`fetchData();`

Bu örnek kod, API'den veri çekmek için kullanılabilir. İstek başarılı olduğunda GuildsDisplayNames alanındaki isimler konsola yazdırılacaktır.


---

Örnek Ekran Görüntüleri

Aşağıda, API'ye yapılan bir isteğin ekran görüntüsünü bulabilirsiniz:

[![NPM version](https://img.shields.io/npm/v/mys-api.js)](https://www.npmjs.com/package/mys-api.js)
