---
title: Развертывание Microsoft Defender для конечной точки на Linux с помощью Puppet
ms.reviewer: ''
description: Описывает развертывание Microsoft Defender для конечной точки на Linux с помощью Puppet.
keywords: Microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 413f8113d2f782c0a57d648a6db8178f2e522270
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903886"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a>Развертывание Microsoft Defender для конечной точки на Linux с помощью Puppet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

В этой статье описывается развертывание Defender для конечной точки для Linux с помощью Puppet. Успешное развертывание требует выполнения всех следующих задач:

- [Скачайте пакет onboarding](#download-the-onboarding-package)
- [Создание манифеста Puppet](#create-a-puppet-manifest)
- [Развертывание](#deployment)
- [Проверка состояния onboarding](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Необходимые условия и требования к системе

 Описание необходимых условий и системных требований к текущей версии программного обеспечения см. на главной странице [Defender for Endpoint для Linux.](microsoft-defender-endpoint-linux.md)

Кроме того, для развертывания Puppet необходимо ознакомиться с задачами администрирования Puppet, настроить puppet и уметь развертывать пакеты. Puppet имеет множество способов выполнения одной и той же задачи. В этих инструкциях предполагается наличие поддерживаемых модулей Puppet, например *apt,* которые помогут развернуть пакет. Ваша организация может использовать другой рабочий процесс. Подробные сведения можно найти в [документации Puppet.](https://puppet.com/docs)

## <a name="download-the-onboarding-package"></a>Скачайте пакет onboarding

Скачайте бортовой пакет из Центра безопасности Защитника Майкрософт:

1. В Центре безопасности Защитника Майкрософт перейдите в **параметры > управления устройствами > onboarding.**
2. В первом выпадаемом меню выберите **Linux Server** в качестве операционной системы. Во втором выпадаемом меню выберите предпочтительный инструмент управления конфигурацией **Linux** в качестве метода развертывания.
3. Выберите **пакет загрузки.** Сохраните файл как WindowsDefenderATPOnboardingPackage.zip.

    ![Снимок экрана Центра безопасности Защитника Майкрософт](images/atp-portal-onboarding-linux-2.png)

4. С командной подсказки убедитесь, что у вас есть файл. 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. Извлечение содержимого архива.
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>Создание манифеста Puppet

Необходимо создать манифест Puppet для развертывания Defender для конечной точки для Linux на устройствах, управляемых сервером Puppet. В этом примере используются модули *apt* и *yumrepo,* доступные из кукольных плит, и предполагается, что модули были установлены на сервере Puppet.

Создание папок *install_mdatp файлов* и *install_mdatp/манифестов* в папке модулей установки Puppet. Эта папка обычно расположена в */etc/puppetlabs/code/environments/production/modules* на сервере Puppet. Скопируйте mdatp_onboard.jsна созданном выше файле в *папку install_mdatp/файлов.* Создание *init.pp* файл, содержащий инструкции по развертыванию:

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>Содержимое файла `install_mdatp/manifests/init.pp`

Защитник для конечной точки для Linux можно развернуть с одного из следующих каналов (обозначается ниже как *[канал]):* *инсайдеры-быстрые,* инсайдеры-медленные или *prod*.  Каждый из этих каналов соответствует репозиторию программного обеспечения Linux.

Выбор канала определяет тип и частоту обновлений, предлагаемых вашему устройству. Устройства в *инсайдерской* быстрой являются первыми, которые получают обновления и новые функции, а затем инсайдеры *медленно* и, *наконец, prod*.

Для предварительного просмотра новых функций и обеспечения ранней обратной связи рекомендуется настроить  некоторые устройства в вашем предприятии, чтобы использовать как инсайдеры-быстрые, так и *инсайдеры-медленные*.

> [!WARNING]
> Переключение канала после начальной установки требует повторной установки продукта. Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство для использования нового канала и выполните действия в этом документе, чтобы установить пакет из нового расположения.

Обратите внимание на рассылку и версию и определите ближайшую запись для нее в `https://packages.microsoft.com/config/` статье .

В приведенных ниже командах *замените [distro]* *и [version]* данными, которые вы определили:

> [!NOTE]
> В случае RedHat, Oracle EL и CentOS 8 *замените [distro]* на rhel.

```puppet
# Puppet manifest to install Microsoft Defender for Endpoint on Linux.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>Развертывание

Включите вышеперечисленный манифест на сайте.pp файл:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

Устройства агентов, зарегистрированные на регистрацию, периодически оповессовыв их и устанавливая новые профили и политики конфигурации, как только они будут обнаружены.

## <a name="monitor-puppet-deployment"></a>Монитор развертывания Puppet

На устройстве агента можно также проверить состояние бортового устройства, заверив:

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **лицензировано.** Это подтверждает, что устройство привязано к организации.

- **orgId.** Это идентификатор организации Defender for Endpoint.

## <a name="check-onboarding-status"></a>Проверка состояния onboarding

Вы можете проверить, правильно ли устройства были на борту, создав скрипт. Например, следующий сценарий проверяет зарегистрированные устройства на наличие состояния бортового устройства:

```bash
mdatp health --field healthy
```

Вышеуказанная команда печатает, если продукт находится на борту и `1` функционирует как ожидалось.

> [!IMPORTANT]
> Когда продукт запускается в первый раз, он скачивает последние определения противомалярийных программ. В зависимости от подключения к Интернету это может занять до нескольких минут. В течение этого времени вышеуказанная команда возвращает значение `0` .

Если продукт не здоров, код выхода (который можно проверить) указывает `echo $?` на проблему:

- 1, если устройство еще не установлено.
- 3, если подключение к daemon невозможно установить.

## <a name="log-installation-issues"></a>Проблемы с установкой журнала

 Дополнительные сведения о том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в примере Проблемы установки [журнала.](linux-resources.md#log-installation-issues)

## <a name="operating-system-upgrades"></a>Обновления операционной системы

При обновлении операционной системы до новой основной версии необходимо сначала удалить Defender для конечной точки для Linux, установить обновление и, наконец, перенастроить Defender для конечной точки для Linux на вашем устройстве.

## <a name="uninstallation"></a>Uninstallation

Создание модуля *remove_mdatp* аналогично *install_mdatp* со следующим контентом *в init.pp* файл:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
