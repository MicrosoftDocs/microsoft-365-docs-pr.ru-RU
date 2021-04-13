---
title: Развертывание ATP Защитника Майкрософт для Linux с помощью Puppet
ms.reviewer: ''
description: Описывает развертывание ATP Microsoft Defender для Linux с помощью Puppet.
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
ms.openlocfilehash: 562433ee52b2e39716e933c67c706f030195bd2f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688421"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-puppet"></a><span data-ttu-id="2ef6c-104">Развертывание Microsoft Defender для конечной точки на Linux с помощью Puppet</span><span class="sxs-lookup"><span data-stu-id="2ef6c-104">Deploy Microsoft Defender for Endpoint on Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2ef6c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2ef6c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ef6c-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2ef6c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ef6c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ef6c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2ef6c-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2ef6c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ef6c-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2ef6c-110">В этой статье описывается развертывание Defender для конечной точки для Linux с помощью Puppet.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-110">This article describes how to deploy Defender for Endpoint for Linux using Puppet.</span></span> <span data-ttu-id="2ef6c-111">Успешное развертывание требует выполнения всех следующих задач:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="2ef6c-112">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="2ef6c-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="2ef6c-113">Создание манифеста Puppet</span><span class="sxs-lookup"><span data-stu-id="2ef6c-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="2ef6c-114">Развертывание</span><span class="sxs-lookup"><span data-stu-id="2ef6c-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="2ef6c-115">Проверка состояния onboarding</span><span class="sxs-lookup"><span data-stu-id="2ef6c-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="2ef6c-116">Необходимые условия и требования к системе</span><span class="sxs-lookup"><span data-stu-id="2ef6c-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="2ef6c-117">Описание необходимых условий и системных требований к текущей версии программного обеспечения см. на главной странице [Defender for Endpoint для Linux.](microsoft-defender-endpoint-linux.md)</span><span class="sxs-lookup"><span data-stu-id="2ef6c-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="2ef6c-118">Кроме того, для развертывания Puppet необходимо ознакомиться с задачами администрирования Puppet, настроить puppet и уметь развертывать пакеты.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="2ef6c-119">Puppet имеет множество способов выполнения одной и той же задачи.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="2ef6c-120">В этих инструкциях предполагается наличие поддерживаемых модулей Puppet, например *apt,* которые помогут развернуть пакет.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="2ef6c-121">Ваша организация может использовать другой рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="2ef6c-122">Подробные сведения можно найти в [документации Puppet.](https://puppet.com/docs)</span><span class="sxs-lookup"><span data-stu-id="2ef6c-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="2ef6c-123">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="2ef6c-123">Download the onboarding package</span></span>

<span data-ttu-id="2ef6c-124">Скачайте бортовой пакет из Центра безопасности Защитника Майкрософт:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="2ef6c-125">В Центре безопасности Защитника Майкрософт перейдите в **параметры > управления устройствами > onboarding.**</span><span class="sxs-lookup"><span data-stu-id="2ef6c-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="2ef6c-126">В первом выпадаемом меню выберите **Linux Server** в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="2ef6c-127">Во втором выпадаемом меню выберите предпочтительный инструмент управления конфигурацией **Linux** в качестве метода развертывания.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="2ef6c-128">Выберите **пакет загрузки.**</span><span class="sxs-lookup"><span data-stu-id="2ef6c-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="2ef6c-129">Сохраните файл как WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Снимок экрана Центра безопасности Защитника Майкрософт](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="2ef6c-131">С командной подсказки убедитесь, что у вас есть файл.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="2ef6c-132">Извлечение содержимого архива.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="2ef6c-133">Создание манифеста Puppet</span><span class="sxs-lookup"><span data-stu-id="2ef6c-133">Create a Puppet manifest</span></span>

<span data-ttu-id="2ef6c-134">Необходимо создать манифест Puppet для развертывания Defender для конечной точки для Linux на устройствах, управляемых сервером Puppet.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-134">You need to create a Puppet manifest for deploying Defender for Endpoint for Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="2ef6c-135">В этом примере используются модули *apt* и *yumrepo,* доступные из кукольных плит, и предполагается, что модули были установлены на сервере Puppet.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="2ef6c-136">Создание папок *install_mdatp файлов* и *install_mdatp/манифестов* в папке модулей установки Puppet.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="2ef6c-137">Эта папка обычно расположена в */etc/puppetlabs/code/environments/production/modules* на сервере Puppet.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="2ef6c-138">Скопируйте mdatp_onboard.jsна созданном выше файле в *папку install_mdatp/файлов.*</span><span class="sxs-lookup"><span data-stu-id="2ef6c-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="2ef6c-139">Создание *init.pp*</span><span class="sxs-lookup"><span data-stu-id="2ef6c-139">Create an *init.pp*</span></span> <span data-ttu-id="2ef6c-140">файл, содержащий инструкции по развертыванию:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-140">file that contains the deployment instructions:</span></span>

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

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="2ef6c-141">Содержимое файла `install_mdatp/manifests/init.pp`</span><span class="sxs-lookup"><span data-stu-id="2ef6c-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="2ef6c-142">Защитник для конечной точки для Linux можно развернуть с одного из следующих каналов (обозначается ниже как *[канал]):* *инсайдеры-быстрые,* инсайдеры-медленные или *prod*.  Каждый из этих каналов соответствует репозиторию программного обеспечения Linux.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-142">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="2ef6c-143">Выбор канала определяет тип и частоту обновлений, предлагаемых вашему устройству.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="2ef6c-144">Устройства в *инсайдерской* быстрой являются первыми, которые получают обновления и новые функции, а затем инсайдеры *медленно* и, *наконец, prod*.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="2ef6c-145">Для предварительного просмотра новых функций и обеспечения ранней обратной связи рекомендуется настроить  некоторые устройства в вашем предприятии, чтобы использовать как инсайдеры-быстрые, так и *инсайдеры-медленные*.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="2ef6c-146">Переключение канала после начальной установки требует повторной установки продукта.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="2ef6c-147">Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство для использования нового канала и выполните действия в этом документе, чтобы установить пакет из нового расположения.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="2ef6c-148">Обратите внимание на рассылку и версию и определите ближайшую запись для нее в `https://packages.microsoft.com/config/` статье .</span><span class="sxs-lookup"><span data-stu-id="2ef6c-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="2ef6c-149">В приведенных ниже командах *замените [distro]* *и [version]* данными, которые вы определили:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="2ef6c-150">В случае RedHat, Oracle EL и CentOS 8 *замените [distro]* на rhel.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

```puppet
# Puppet manifest to install Microsoft Defender ATP.
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

## <a name="deployment"></a><span data-ttu-id="2ef6c-151">Развертывание</span><span class="sxs-lookup"><span data-stu-id="2ef6c-151">Deployment</span></span>

<span data-ttu-id="2ef6c-152">Включите вышеперечисленный манифест на сайте.pp</span><span class="sxs-lookup"><span data-stu-id="2ef6c-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="2ef6c-153">файл:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="2ef6c-154">Устройства агентов, зарегистрированные на регистрацию, периодически оповессовыв их и устанавливая новые профили и политики конфигурации, как только они будут обнаружены.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="2ef6c-155">Монитор развертывания Puppet</span><span class="sxs-lookup"><span data-stu-id="2ef6c-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="2ef6c-156">На устройстве агента можно также проверить состояние бортового устройства, заверив:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="2ef6c-157">**лицензировано.** Это подтверждает, что устройство привязано к организации.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="2ef6c-158">**orgId.** Это идентификатор организации Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="2ef6c-159">Проверка состояния onboarding</span><span class="sxs-lookup"><span data-stu-id="2ef6c-159">Check onboarding status</span></span>

<span data-ttu-id="2ef6c-160">Вы можете проверить, правильно ли устройства были на борту, создав скрипт.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="2ef6c-161">Например, следующий сценарий проверяет зарегистрированные устройства на наличие состояния бортового устройства:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="2ef6c-162">Вышеуказанная команда печатает, если продукт находится на борту и `1` функционирует как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ef6c-163">Когда продукт запускается в первый раз, он скачивает последние определения противомалярийных программ.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="2ef6c-164">В зависимости от подключения к Интернету это может занять до нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="2ef6c-165">В течение этого времени вышеуказанная команда возвращает значение `0` .</span><span class="sxs-lookup"><span data-stu-id="2ef6c-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="2ef6c-166">Если продукт не здоров, код выхода (который можно проверить) указывает `echo $?` на проблему:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="2ef6c-167">1, если устройство еще не установлено.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="2ef6c-168">3, если подключение к daemon невозможно установить.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="2ef6c-169">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="2ef6c-169">Log installation issues</span></span>

 <span data-ttu-id="2ef6c-170">Дополнительные сведения о том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в примере Проблемы установки [журнала.](linux-resources.md#log-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="2ef6c-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="2ef6c-171">Обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="2ef6c-171">Operating system upgrades</span></span>

<span data-ttu-id="2ef6c-172">При обновлении операционной системы до новой основной версии необходимо сначала удалить Defender для конечной точки для Linux, установить обновление и, наконец, перенастроить Defender для конечной точки для Linux на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="2ef6c-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="2ef6c-173">Uninstallation</span><span class="sxs-lookup"><span data-stu-id="2ef6c-173">Uninstallation</span></span>

<span data-ttu-id="2ef6c-174">Создание модуля *remove_mdatp* аналогично *install_mdatp* со следующим контентом *в init.pp*</span><span class="sxs-lookup"><span data-stu-id="2ef6c-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="2ef6c-175">файл:</span><span class="sxs-lookup"><span data-stu-id="2ef6c-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
