---
title: Развертывание защитника для конечной точки на Linux с помощью Шеф-повара
description: Узнайте, как развернуть Defender для конечной точки в Linux с помощью Chef
keywords: Microsoft, defender, atp, linux, scans, antivirus, microsoft defender for endpoint (Linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903932"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Развертывание Defender для конечной точки в Linux с помощью Chef

Подготовка:

- Установите unzip, если он еще не установлен. Компоненты Chef уже установлены, и репозиторий Chef существует (шеф-повар создает репо), чтобы хранить поваренную книгу, которая будет использоваться для развертывания в Defender для конечной точки на управляемых серверах Linux <reponame> chef.

Вы можете создать новую книгу в существующем репозитории, заверив следующую команду из папки кулинарной книги, которая находится в репозитории шеф-повара:</br>
`chef generate cookbook mdatp`

Эта команда создаст новую структуру папок для новой кулинарной книги под названием mdatp.  Вы также можете использовать существующую поваренную книгу, если она уже используется для добавления развертывания MDE.
После создания кулинарной книги создайте папку файлов в только что созданной папке.

`mkdir mdatp/files`

Переложите почтовый файл для загрузки Linux Server, который можно скачать с портала Центра безопасности Защитника Майкрософт, в эту новую папку файлов.

На рабочей станции Chef перейдите в папку mdatp/recipes. Эта папка создается при сгенерировании кулинарной книги. Используйте предпочитаемый текстовый редактор (например, vi или nano), чтобы добавить следующие инструкции к концу файла default.rb:
-   include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

Затем сохраните и закроите файл default.rb.
Далее создайте новый файл рецептов с именем install_mdatp.rb в папке рецептов и добавьте этот текст в файл:

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

Чтобы соответствовать развертываемой версии и каналу, необходимо изменить имя версии, рассылку и репо.
Далее следует создать файл onboard_mdatp.rb в папке mdatp/recipies.  Добавьте следующий текст в этот файл:

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

Обязательно обновим имя пути к расположению бортового файла.
Чтобы протестировать развертывание на рабочей станции Chef, просто запустите ``sudo chef-client -z -o mdatp`` .
После развертывания следует рассмотреть возможность создания и развертывания файла конфигурации на серверах на основе набора предпочтений  [для Microsoft Defender для конечной](/linux-preferences.md)точки в Linux.  
После создания и тестирования файла конфигурации вы можете поместить его в папку cookbook/mdatp/files, где вы также разместили пакет onboarding.  Затем вы можете создать файл settings_mdatp.rb в папке mdatp/recipies и добавить этот текст:

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

Чтобы включить этот шаг в состав рецепта, просто добавьте include_recipe ':: settings_mdatp' в файл default.rb в папке рецептов.
Вы также можете использовать crontab для расписания автоматических обновлений Расписание обновления [Microsoft Defender для конечной точки (Linux).](linux-update-MDE-Linux.md)

Uninstall MDATP cookbook:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

