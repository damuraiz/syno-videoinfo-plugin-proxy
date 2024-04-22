# *Syno*logy Video Info Plugin

[![GitHub Release](https://img.shields.io/github/v/release/C5H12O5/syno-videoinfo-plugin?logo=github&style=flat&color=blue)](https://github.com/C5H12O5/syno-videoinfo-plugin/releases)
![GitHub Stars](https://img.shields.io/github/stars/C5H12O5/syno-videoinfo-plugin?logo=github&style=flat&color=yellow)
![GitHub Downloads](https://img.shields.io/github/downloads/C5H12O5/syno-videoinfo-plugin/total?logo=github&style=flat&color=green)
![Python Support](https://img.shields.io/badge/Python-3.6+-green?logo=python&style=flat&color=steelblue)
[![GitHub License](https://img.shields.io/github/license/C5H12O5/syno-videoinfo-plugin?logo=apache&style=flat&color=lightslategray)](LICENSE)

###### 📖 English / 📖 [简体中文](README.zh-CN.md)

##Важно!!!
**Это форк от плагина который реализовал C5H12O5. В нем нет ничего нового кроме добавление еще одного источника получения информации
 который находится по [***этому адресу***](https://hammerhead-app-ff8ar.ondigitalocean.app)**
 
 * Что это за источник? Это по сути это тот же tmdb.org
 * Это копия? Нет это простое прокси. 
 * Зачем так сложно? У меня один провайдер и он блокирует любые VPN соединения, а так можно без VPN
 * Как пользоваться? Скачиваете/собираете по инструкции, устанавливаете в Video Station, заходите в настройки плагина, убирайте все ненужные источники, добавляете ваш API ключ от TMDB в настройке и сохраняете.
 * Не доверяю я чужим прокси сервисам? Не вопрос [***тут***](https://github.com/damuraiz/get-request-proxy) исходники прокси. Скачивай, разворачивай на своем сервере, ну и замени адрес в этом плагине на свой. 


This project is a video information plugin for Synology **Video Station**. It provides a way to fetch metadata from websites
other than the default ones.


* Implemented in Python without any third-party dependencies.
* Supports multiple sources, and can be easily extended to support more.
* Has a simple configuration page where you can customize your plugin.

![preview](preview.png)

## Usage

Install the plugin:

1. Download the latest release from [***here***](https://github.com/C5H12O5/syno-videoinfo-plugin/releases).
2. Open your **Video Station**, go to ***Settings*** > ***Video Info Plugin***.
3. Click **[Add]**, select the downloaded file, and click **[OK]**.

Configure the plugin:

1. Open your browser, go to `http://[NAS_IP]:5125` (replace `[NAS_IP]` with your NAS IP address) page.
2. Change the configuration as you want, and click **[ :floppy_disk: ]** button in the upper right corner.
3. Go back to your **Video Station**, the configuration should be applied automatically.
> [!NOTE]
> If you upgrade the plugin but the configuration page is not updated, you can restart the configuration service by following steps:
> 1. Open the configuration page, click **[Exit]** button in the upper right corner to close the service.
> 2. Go back to **Video Station**, go to ***Settings*** > ***Video Info Plugin***, and click **[Test Connection]** button to restart the service.

## Requirements

* Python 3.6+
* Video Station 2.5.0+ for DSM 6.0
* Video Station 3.0.0+ for DSM 7.0

## References

* [The Video Station Metadata](https://kb.synology.com/en-id/DSM/help/VideoStation/metadata?version=7)
* [The Video Station API documentation](https://download.synology.com/download/Document/Software/DeveloperGuide/Package/VideoStation/All/enu/Synology_Video_Station_API_enu.pdf)

> Tips for naming video files:
>
> Movie:
>
> * Naming format: Movie_Name (Release_Year).ext
> * Example: Avatar (2009).avi
>
> TV Show:
> * Naming format: TV_Show_Name.SXX.EYY.ext (***S*** as a shorthand for ***Season*** and ***E*** for ***Episode***)
> * Example: Gossip Girl.S03.E04.avi

## Development

You can develop your own plugin based on this project easily. Here are the steps:

1. Clone this repository to your local machine:

```shell
git clone https://github.com/C5H12O5/syno-videoinfo-plugin
```

2. Modify the code as you want, and test it like this:

```shell
python main.py --type movie --input "{\"title\":\"{movie_title}\"}" --limit 1 --loglevel debug
```

3. Package the plugin using the following command:

```shell
python setup.py sdist --formats=zip
```

## License

[Apache-2.0 license](LICENSE)