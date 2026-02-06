# OpenClaw-Kurulum-ve-lk-Sohbet-Kurulumu-Rehberi

Bu rehber, sisteminizde yerel olarak çalışan ve Telegram, WhatsApp veya Discord gibi mesajlaşma platformlarına bağlanan, sohbet öncelikli bir yapay zeka botu olan OpenClaw'ın (eski adlarıyla Moltbot veya Clawbot) nasıl kurulacağını anlatır.

Bu rehberde OpenClaw'ı 20 dakikadan kısa bir sürede kurmayı, tercih ettiğiniz AI modeliyle yapılandırmayı ve onunla sohbet etmeye başlamayı öğreneceksiniz.

# OpenClaw Nedir? 

OpenClaw, Peter Steinberger tarafından geliştirilen ve GitHub'da açık kaynak olarak sunulan bir AI ajanıdır. Diğer botlardan farkı, karmaşık yapılandırma dosyaları yerine doğal dil ile (sohbet ederek) etkileşime geçilebilmesidir.

Not: Proje adı daha önce ClawdBot ve MoltBot olarak değişmiştir, şu anki adı OpenClaw'dır. Bazı eski kaynaklarda bu isimleri görebilirsiniz.

# Gereksinimler
Kuruluma başlamadan önce şunlara sahip olduğunuzdan emin olun:

Bir Sosyal Medya hesabı.

Terminal/Komut Satırı kullanımına aşinalık.

Sisteminizde Node.js'in kurulu olması. (https://nodejs.org/en/download)

# 1. Adım
OpenClaw'ı yüklemek için terminalinizi açın ve aşağıdaki komutu çalıştırın:

curl -fsSL https://openclaw.ai/install.sh | bash

Yükleyici, işletim sisteminizi otomatik olarak algılayacak ve her şeyin düzgün çalışıp çalışmadığını doğrulayacaktır. Kurulum tamamlandığında etkileşimli bir terminal arayüzü (TUI) başlatılacaktır.
Kurulum tamamlandığında, resimde gösterildiği gibi kurulumu ve sürüm ayrıntılarını doğrulayan ilerleme çıktısını göreceksiniz:

<img width="2696" height="772" alt="setup-step1" src="https://github.com/user-attachments/assets/c24bdfe9-9076-4254-8ad4-d3920ee1472e" />

# 2. Adım (İlk Ayarlar ve "QuickStart")

Kurulum sonrası terminal arayüzünde (TUI) şu adımları izleyin:

1- Devam etmek istediğinizi onaylayın.

2- Onboarding Mode (Karşılama Modu) seçimi ekranında, Space (Boşluk) tuşuna basarak QuickStart seçeneğini işaretleyin ve Enter'a basın.

<img width="2712" height="1206" alt="onboarding" src="https://github.com/user-attachments/assets/905a3f61-fecb-4d7b-a2e0-62f2a1adf52c" />

QuickStart, güvenli varsayılan ayarlarla botu hızlıca çalışır hale getirmenizi sağlar.

# 3. Adım (AI Modelini Seçme)
Hızlı başlangıç işlemi tamamlandığında, bir model sağlayıcısı seçmeniz istenecektir. Bu rehberde Google Gemini örneği üzerinden gidilecektir:

Openclaw yerel bir ağ geçidi kurar ve size modelinizi kurmanız için buna benzer bir uyarı gösterir:

![models](https://github.com/user-attachments/assets/0a574422-adf1-4e9b-9b03-50fb8994a889)
Burada Google model/kimlik doğrulama sağlayıcısını kullanacağız. Enter tuşuna bastığınızda, size üç seçenek sunulacak ve bunlardan Google Antigravity OAuth seçeneğini seçmeniz gerekecek:

Seçenekler arasından Google Antigravity OAuth seçeneğini seçin.

![auth-selection](https://github.com/user-attachments/assets/f8f45bf5-e24c-4aaf-911f-ec18395d6263)

Ardından Gmail hesabınıza giriş yapmanız istenecek ve izin verdikten sonra kimlik doğrulama işleminin tamamlandığı mesajıyla bilgilendirileceksiniz.

Kimlik doğrulama tamamlandıktan sonra, bot terminalinin Gemini aboneliğinize bağlı olarak farklı model seçenekleri sunduğunu fark edeceksiniz. Biz gemini-3-flash modelini kullanıyoruz, ancak dilediğiniz modeli kullanabilirsiniz.

<img width="2610" height="1358" alt="model-selection" src="https://github.com/user-attachments/assets/8d16874f-21b3-4371-8a67-69b9f7559e1c" />

Not: OpenAI veya Anthropic (Claude) gibi diğer sağlayıcıları da benzer şekilde yapılandırabilirsiniz.
# 4. Adım (OpenClaw'ı Telegram'a Bağlama)
Artık botumuz modele erişim sağladığına göre, bizden sohbet arayüzünü şu şekilde kurmamızı isteyecektir:

![chat-selection](https://github.com/user-attachments/assets/92eed6db-30ff-4609-bf8f-602a562134b2)

Botumuzla sohbet etmek için bu rehberimizde Telegram'ı kullanacağız . Telegram seçeneğini seçin ve aşağıdaki adımları izleyin:

1-Arayüzde Telegram seçeneğini seçtik.

2-Telefonunuzdan veya bilgisayarınızdan Telegram'ı açın.

3-@BotFather kullanıcısını bulun ve sohbeti başlatın.

4-/newbot komutunu gönderin ve yönergeleri izleyerek botunuza bir isim verin.

5-BotFather size bir API Token verecektir. Bu token'ı kopyalayın.

![botfather](https://github.com/user-attachments/assets/3802c4a3-dc5d-42a9-a9b4-0ce0eb906796)


OpenClaw terminal ekranına geri dönün ve token'ı yapıştırın.

![telegram-token](https://github.com/user-attachments/assets/666b40c9-6d0b-4d78-8847-7fcaacbbded8)

Hepsi bu kadar, Temel olarak Telegram kurulumunu tamamladık.

# 6.Adım (Botu Başlatma (Hatching))

OpenClaw iki farklı etkileşim yolu sunar: Control UI (Tarayıcı tabanlı) ve TUI (Terminal tabanlı). İlk kurulum için TUI önerilir.

"Hatch in TUI" seçeneğini seçin ve Enter'a basın.

Botun kişiliğini oluşturmak için size birkaç basit soru soracaktır (Botun adı ne olsun? Size nasıl hitap etsin?).

Bu soruları yanıtladıktan sonra bot, yapılandırdığınız kişiliğe uygun bir karşılama mesajı verecektir.

Şimdilik herhangi bir beceri ayarlamayacağız, bu nedenle "Şimdilik atla" seçeneğinde boşluk tuşuna basın ve ardından Enter tuşuna basın.

![skills](https://github.com/user-attachments/assets/4821fc93-f409-4c62-a158-4f0f41923412)


OpenClaw için API Anahtarlarını Yapılandırma

Sonraki adımda, Openclaw sizden varsa farklı API anahtarlarını sağlamanızı isteyecektir. Bizim durumumuzda, sağlayabileceğimiz herhangi bir API anahtarımız yoktu, bu nedenle her biri için "Hayır" seçeneğini işaretledik:

![api-keys](https://github.com/user-attachments/assets/a214a800-8741-4198-b41b-581a3b45f41c)


# 7.Adım (OpenClaw nasıl çalıştırılır ve test edilir?)

OpenClaw, yapay zekâ asistanınızla etkileşim kurmanız için iki yol sunar:

1-Kontrol Arayüzü

2-TUI

<img width="2716" height="1804" alt="ui-selection" src="https://github.com/user-attachments/assets/5955ac36-aff5-4ce8-8fbd-a5f8decb4d73" />

Kontrol Arayüzü (Tarayıcı Tabanlı Arayüz)

Kontrol Arayüzü, tarayıcınızda açılan web tabanlı bir kontrol panelidir. Erişmek için, terminalinizde gösterilen Web Arayüzü bağlantısını herhangi bir tarayıcıya yapıştırın. Tarayıcı tabanlı arayüzün görünümü şöyledir:

<img width="3428" height="1970" alt="clawdbot-cui" src="https://github.com/user-attachments/assets/b6721138-ce21-4a4c-9ff5-dbfce98e5f1f" />

TUI (Terminal Kullanıcı Arayüzü)

Terminal arayüzü her şeyi komut satırınızda tutar. Openclaw'ın kişilik yapılandırmasını tamamlamasıyla ilgili doğrudan ve anında geri bildirim sağladığı için ilk kurulum için önerilen seçenektir. TUI, daha sonra Telegram'da göreceğiniz aynı konuşma akışını göstererek Openclaw'ın nasıl yanıt verdiğini anlamayı kolaylaştırır.

Ve şimdi TUI ve Control UI arasındaki farkı anladığınıza göre, hepimizin beklediği an geldi! Botumuzu oluşturma zamanı. "TUI'de Oluştur" seçeneğini seçin ve "Enter" tuşuna basın. Ardından size botun adı ve size nasıl hitap edebileceği gibi bazı basit sorular soracak; bunları cevap çubuğuna yazabilirsiniz.

Kişilik yapılandırmasının uygulamadaki görünümü şöyledir:

<img width="2700" height="1538" alt="maltbot-ques" src="https://github.com/user-attachments/assets/ed4d4866-1aa2-42a2-a3b4-4858cbd53ce1" />

Bu soruları yanıtladıktan sonra, Openclaw, yapılandırdığınız kişiliği yansıtan kişiselleştirilmiş bir yanıtla kurulumunu onaylayacaktır:

<img width="2696" height="570" alt="maltbot-reply" src="https://github.com/user-attachments/assets/1503781d-f7ca-425d-900e-90ffae79eb4c" />

OpenClaw asistanınız artık benzersiz bir kimliğe sahip, kim olduğunuzu anlıyor ve hem terminal üzerinden hem de bağlı mesajlaşma platformunuz aracılığıyla komutları almaya hazır.

# Telegram üzerinden OpenClaw ile sohbet etmek

Botumuz artık çalışır durumda ve onunla her yerden iletişim kurmak istiyoruz, bu yüzden Telegram'a ihtiyacımız var. Telefonunuzdan terminale erişemezsiniz, değil mi? Şimdiye kadar işimiz neredeyse bitti. Şimdi, daha önce oluşturduğumuz Telegram botuyla bağlantı kurmak için botumuza biraz daha bilgi vermemiz gerekiyor. Telegram botunuza gidin ve "/start" komutunu çalıştırın.

Bu size, kopyalamanız ve botunuzun Telegram botuna bağlanmasını sağlamanız için gereken yapılandırma ayrıntılarını sağlayacaktır.

![tele-info](https://github.com/user-attachments/assets/f6fe249a-3d39-4f99-a237-d0b693c30698)

Botun Telegram'ın kullanıma hazır olduğunu onaylamasının ardından aldığımız yanıt bu şekildedir, ancak bu yanıt kullanıcıdan kullanıcıya değişebilir:

<img width="2722" height="378" alt="tele-bot-reply" src="https://github.com/user-attachments/assets/f8725fe1-88fd-4b5f-825c-1d00c75843b8" />

Telegram bot kurulumu tamamlandı, kendi asistanınız ile dilediğiniz şekilde sohbet edebilirsiniz. 

# Ek Adımlar (OpenClaw'ın web aramaları yapmasına nasıl izin verilir)

Burdan sonraki adımlarda makine öğrenmesini kullanabiliriz. Şu anda botumuz bazı basit görevleri yerine getirebiliyor, ancak web aramaları içeren karmaşık görevler söz konusu olduğunda başarısız oluyor. Bu yüzden, Becky'ye botumuzun bizim için web aramaları yapmasını nasıl sağlayabileceğimizi sormaya ne dersiniz?

![tele-chat3](https://github.com/user-attachments/assets/2ac51a12-6055-449b-b3e5-acb1dfe86b5f)

Bize sunduğu adımları izleyelim:

Brave Web Arama API konsoluna gidin ve API sekmesini açın.

<img width="3402" height="1982" alt="brave-api" src="https://github.com/user-attachments/assets/5254373c-fc3e-4e76-94bb-911c4bc18864" />

API anahtarını kopyalayın ve Telegram sohbeti aracılığıyla botunuza gönderin.

![tele-chat4](https://github.com/user-attachments/assets/ffe1c06e-af0c-40a6-a715-1309ba8cc7c4)

Bu sayede botumuz artık web'de de arama yapabiliyor ve verdiğimiz görevleri yerine getirme yeteneği artıyor. Dilerseniz kişisel asistanınızın, size diğer insanlardan gelen mesajları cevaplaması gibi üst düzey asistan özelliklerini dahi ekleyebilirsiniz lakin bu başka bir rehberin konusu :)






















