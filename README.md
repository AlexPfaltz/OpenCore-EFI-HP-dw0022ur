<h1 align="center"> 🍎 HP 15-dw0043ur - OpenCore Hackintosh </h1>
<img src="https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/blob/main/Preview.png">
<a href="https://apps.apple.com/ua/app/macos-ventura/id1638787999?mt=12"><img src="https://img.shields.io/badge/macOS-Ventura%2013.7.8-brightgreen"></a>
<a href="https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.6"><img src="https://img.shields.io/badge/OpenCore-1.0.6-blue"></a>

OpenCore EFI для HP 15-dw0043ur с процессором Intel Core i3-7020U (Kaby Lake) и графикой Intel HD Graphics 620.
## 📋 СОДЕРЖАНИЕ
- [Спецификация ноутбука](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#-%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F-%D0%BD%D0%BE%D1%83%D1%82%D0%B1%D1%83%D0%BA%D0%B0)
- [Версии ПО](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%BF%D0%BE)
- [Статус компонентов](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#-%D1%81%D1%82%D0%B0%D1%82%D1%83%D1%81-%D0%BA%D0%BE%D0%BC%D0%BF%D0%BE%D0%BD%D0%B5%D0%BD%D1%82%D0%BE%D0%B2)
- [Настройки BIOS](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#%EF%B8%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-bios)
- [Пост-установка](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#-%D0%BF%D0%BE%D1%81%D1%82-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0)
- [Известные проблемы](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#%EF%B8%8F-%D0%B8%D0%B7%D0%B2%D0%B5%D1%81%D1%82%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D1%8B)
- [Благодарности](https://github.com/AlexPfaltz/OpenCore-EFI-HP-dw0022ur/edit/main/README.md#-%D0%B1%D0%BB%D0%B0%D0%B3%D0%BE%D0%B4%D0%B0%D1%80%D0%BD%D0%BE%D1%81%D1%82%D0%B8)

## 💻 СПЕЦИФИКАЦИЯ НОУТБУКА

Компонент	|Модель	
:---------|:---------
Модель	|HP 15-dw0043ur
Процессор	|Intel Core i3-7020U (Kaby Lake)
Графика	|Intel HD Graphics 620
ОЗУ	|16 GB DDR4 (2 x 8 GB Kingston 2133MHz)
SSD	|Samsung SSD 980 500GB
Wi-Fi/Bluetooth	|Broadcom BCM94360CS2
Ethernet |Realtek RTL8111
Аудио	|Realtek ALC236
Тачпад |Synaptics I2C/PS2
BIOS версия	|F.68

## 🖥 ВЕРСИИ ПО

Компонент |	Версия
:---------|:---------
macOS	Ventura |13.7.8
OpenCore	|1.0.6
Lilu	|1.7.1
WhateverGreen	|1.7.0
AppleALC	|1.9.6
VirtualSMC	|1.3.7
RealtekRTL8111	|2.5.0
NVMeFix	|1.1.3
VoodooPS2Controller	|2.3.7
VoodooI2C	|2.9.1

## ✅ СТАТУС КОМПОНЕНТОВ

Компонент	|Статус	|Примечание
:---------|:---------|:---------
Сон/Пробуждение	|✅ Отлично	|Работает, DarkWake исправлен
Графика	|✅ Отлично	|2048 MB VRAM, ускорение Metal
Яркость	|⚠️ Работает	|Клавиши F2/F3 не работают.
Аудио |✅ Отлично	|Динамики, наушники, микрофон
Ethernet	|✅ Отлично	|RealtekRTL8111
Wi-Fi, Bluetooth	|⚠️ Работает	|Только 2.4 Hz, AirDrop, Handoff
USB	|✅ Отлично	|Все порты 2.0/3.0/Type-C, камера
Card-reader |✅ Отлично
Тачпад	|✅ Отлично	|Мультитач, жесты
Клавиатура	|✅ Отлично	|Все клавиши, Fn
Батарея	|✅ Отлично	|Индикатор, датчики, калибровка
NVMe SSD	|✅ Отлично	|TRIM включен
iMessage/FaceTime	|⚠️ Работает	|Требуется генерация серийников
App Store	|✅ Работает	
Обновления	|✅ Работают	|System Settings

## ⚙️ НАСТРОЙКИ BIOS

- Intel SGX → **Disabled**
- TPM → **Disabled**
- Virtualization Technology → **Enabled**
- Legacy Support → **Disabled**
- Secure Boot → **Disabled**
- Action Keys Mode → **Enabled** (для F1-F12 как функциональные клавиши)

## 🔧 ПОСТ-УСТАНОВКА

### 1. Генерация серийных номеров
```
# Скачайте GenSMBIOS
git clone https://github.com/corpnewt/GenSMBIOS
cd GenSMBIOS
./GenSMBIOS.command

# Выберите MacBookPro14,1
# Сгенерируйте новые MLB, Serial, UUID
```
Замените в config.plist:
- SystemSerialNumber → новый серийник
- MLB → новый MLB
- SystemUUID → новый UUID
- ROM → MAC-адрес вашей сетевой карты en0 в Base64

### 2. Включение TRIM для SSD
```
  sudo trimforce enable
```

### 3. Настройки питания
```
# Оптимальные настройки для ноутбука
sudo pmset -a standbydelay 10800  # Переход в глубокий сон через 3 часа
sudo pmset -a standby 1            # Включить глубокий сон
sudo pmset -a autopoweroff 1       # Автоотключение питания
sudo pmset -a autopoweroffdelay 259200  # Через 3 дня
sudo pmset -a hibernatemode 3      # Режим гибернации (как на Mac)
sudo pmset -a proximitywake 0      # Отключить пробуждение от устройств поблизости
sudo pmset -a tcpkeepalive 0        # Предотвратить пробуждение соединения каждые 2 часа
sudo pmset -a powernap 0            # Отключает периодическое пробуждение ноутбука для работы в сети и обновлениях

# Для батареи
sudo pmset -b disksleep 5           # Отключение дисков через 5 мин на батарее
sudo pmset -b displaysleep 3        # Отключение дисплея через 3 мин
sudo pmset -b sleep 10               # Сон через 10 мин

# Для сети (от батареи)
sudo pmset -b halfdim 1             # Уменьшение яркости при питании от батареи
sudo pmset -b lessbright 1          # Еще больше уменьшить яркость
```

### 4. Включить поддержку масштабирования

Способ Через RDM + one-key-hidpi. Это самый безопасный и простой способ для внутренних экранов ноутбуков.
1. Установите one-key-hidpi:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"
```
2. В меню выберите:
- **(1) Enable HIDPI**
- Display Icon → **(3) MacBook Pro**
- resolution config → **(2) 1920x1080 Display** (use 1424x802, fix underscaled after sleep)

3. После перезагрузки выбрать, в настройках Дисплея, удобный вариант масшатбирования.

## ⚠️ ИЗВЕСТНЫЕ ПРОБЛЕМЫ
### Регулировка яркости
Можно настроить маппинг через hidutil

## 🙏 БЛАГОДАРНОСТИ
- [Acidanthera](https://github.com/acidanthera) за OpenCore и кексты
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) за руководства
- [CorpNewt](https://github.com/corpnewt) за утилиты
- [xzhih](https://github.com/xzhih/one-key-hidpi) за фикс масштабирования
- Сообществу [r/hackintosh](https://reddit.com/r/hackintosh)
