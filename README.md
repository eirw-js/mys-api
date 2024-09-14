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

const axios = require('axios');

async function fetchData() {
    const apiKey = 'test'; // API anahtarınızı buraya ekleyin
    const apiUrl = `https://discordpanel.vercel.app/api/user/{id}`; // İstek atılacak API URL'sini belirtin
    
    try {
        const response = await axios.get(apiUrl);
        
        console.log("İstek Başarılı!", response.data);

        const otherNames = response.data["GuildsDisplayNames"].map((x) => x).join("\n");
        console.log(otherNames);
    } catch (error) {
        console.error('Hata:', error);
    }
}

fetchData();

Bu örnek kod, API'den veri çekmek için kullanılabilir. İstek başarılı olduğunda GuildsDisplayNames alanındaki isimler konsola yazdırılacaktır.


---

Örnek Ekran Görüntüleri

Aşağıda, API'ye yapılan bir isteğin ekran görüntüsünü bulabilirsiniz:

https://private-user-images.githubusercontent.com/142053394/277836726-76141f14-6fe8-4b7b-a91a-7103d3cbac30.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjYyOTAwMTgsIm5iZiI6MTcyNjI4OTcxOCwicGF0aCI6Ii8xNDIwNTMzOTQvMjc3ODM2NzI2LTc2MTQxZjE0LTZmZTgtNGI3Yi1hOTFhLTcxMDNkM2NiYWMzMC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwOTE0JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDkxNFQwNDU1MThaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT1hZmFmZjQ4YmE4MTNiMGUwMmQxY2ZlOWM5YTQ3MmE3YjE1YjA0NmZkMjIzNDA1YTU0YmYxMjAyMGRmNGJlZTlkJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.JtPU7trJiraL5kMrP6hiWDLT80V6WnMPze92GXSCMQ4
