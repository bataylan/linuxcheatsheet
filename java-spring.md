# REST ve OpenApi ile calisma

## Yeni bir api servisi ekleme

**api.yaml** dosyasinda ekleyecegimiz servis icin bir **path** olusturuyoruz. path icerisinde tanimladigimiz **tags** kisminda belirttigimiz tag a gore api interface ve controller generate ediliyor, **operationId** bu controller icerisinde bulunacak action'in ismini, responses da ise **200** ile basarili responseda dondurulecek response'u ve **default**'ta varsayilan hata response'unu tanimliyoruz. 

Path icerisinde belirttigimiz **response** ve **schema** yi asagida components->responses ve components->schema kisimlarinda tanimliyoruz.

api.yaml dosyasindaki tanimlamalar bittikten sonra `mvn clean compile` ile tanimlamamiza gore responselari ve ilgili interface/controller'lar generate ediliyor.

## REST Controller'a ilgili methodun eklenmesi

**Controller** -> Oncelikle controllerimiz generate edilen **api controllerini** `implements` ile kalitlmali. Ardindan api controllerinda generate edilerek olusturulan, operationId kisminda ismini belirttigimiz action'i `@Override` annotation i ile kendi rest controllerimizda yaziyoruz.

**Servis** -> Controllerda kullanmak icin olusturacagimiz servisi interface e ekledikten sonra Implemantation adinda olanina yani interface'i kalitan class a giderek bu servisi yaziyoruz. Eger servis ozel bir response donduruyorsa, bu response'u da ServiceResponses altinda olusturarak methodumuzun dondurecegi tur olarak belirtiyoruz.

**Converter** -> ModelMapper'i varsayilan degerlerinden farkli kullanmak icin converter klasorunun altinda `api_response_ismi(sonunda response olmadan) + Converter` adinda yeni bir class olusturuyoruz. Ardindan bu converter class'in kullanilabilmesi icin config -> MapperConfig classinin icerisine ekliyoruz.
