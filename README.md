# Discord.js Bot Template

Prefix, slash komutları, buton, modal ve menü etkileşimleri için hazır dosya yapısı sunan, JavaScript ile yazılmış Discord bot şablonu. Komutlar ve olaylar klasörlerden otomatik yüklenir; yeni komut eklemek için ilgili klasöre bir dosya eklemek yeterlidir.

## Teknolojiler

- JavaScript, Node.js
- discord.js 14, @discordjs/voice
- quick.db (SQLite, better-sqlite3)
- dotenv

## Özellikler

- Prefix ile çalışan metin komutları (`sources/commands/base/`)
- Slash komutları (`sources/commands/home/`), global veya sunucuya özel kaydedilebilir
- Buton, modal, seçim menüsü ve context menu için boş şablonlar (`sources/admins/tools/`)
- Olay yöneticileri (`sources/events/client/`) ve cooldown yardımcıları (`sources/utils/client/`)
- İsteğe bağlı: botun belirli bir ses kanalında kalması

## Kurulum

Gereksinim: Node.js 18 veya üzeri.

```bash
git clone https://github.com/ahmetalpcinar/discord-js-bot-template.git
cd discord-js-bot-template
npm install
cp .env.example .env
```

`.env` dosyasını doldurun:

```env
prefix = "."
owner = "KULLANICI_ID"
guild = "SUNUCU_ID"
token = "BOT_TOKEN"
```

Token, [Discord Developer Portal](https://discord.com/developers/applications) üzerinde uygulamanızın Bot sayfasından alınır. `.env` dosyası `.gitignore` içindedir, repoya gönderilmez.

```bash
npm start
```

## Kullanım

- Prefix komutları için `sources/commands/base/<kategori>/` altına bir dosya ekleyin.
- Slash komutları için `sources/commands/home/<kategori>/` altına bir dosya ekleyin. Örnek için `ornek.js` dosyalarına bakın.
- `sources/events/client/ready.js` içinde `slashcommands(client, "Global")` ifadesini `"Guild"` yaparak komutları yalnızca tek sunucuya kaydedebilirsiniz.

<img src="https://raw.githubusercontent.com/ahmetalpcinar/ahmetalpcinar/main/PNG/Images/imageDC1.png" alt="Bot kurulum ekranı">

## Lisans

CC0 1.0. Bkz. [LICENSE](LICENSE).
