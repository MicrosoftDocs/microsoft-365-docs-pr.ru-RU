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
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="8bff6-104">Развертывание Defender для конечной точки в Linux с помощью Chef</span><span class="sxs-lookup"><span data-stu-id="8bff6-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="8bff6-105">Подготовка:</span><span class="sxs-lookup"><span data-stu-id="8bff6-105">Before you begin:</span></span>

- <span data-ttu-id="8bff6-106">Установите unzip, если он еще не установлен.</span><span class="sxs-lookup"><span data-stu-id="8bff6-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="8bff6-107">Компоненты Chef уже установлены, и репозиторий Chef существует (шеф-повар создает репо), чтобы хранить поваренную книгу, которая будет использоваться для развертывания в Defender для конечной точки на управляемых серверах Linux <reponame> chef.</span><span class="sxs-lookup"><span data-stu-id="8bff6-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="8bff6-108">Вы можете создать новую книгу в существующем репозитории, заверив следующую команду из папки кулинарной книги, которая находится в репозитории шеф-повара:</span><span class="sxs-lookup"><span data-stu-id="8bff6-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="8bff6-109">Эта команда создаст новую структуру папок для новой кулинарной книги под названием mdatp.</span><span class="sxs-lookup"><span data-stu-id="8bff6-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="8bff6-110">Вы также можете использовать существующую поваренную книгу, если она уже используется для добавления развертывания MDE.</span><span class="sxs-lookup"><span data-stu-id="8bff6-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="8bff6-111">После создания кулинарной книги создайте папку файлов в только что созданной папке.</span><span class="sxs-lookup"><span data-stu-id="8bff6-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="8bff6-112">Переложите почтовый файл для загрузки Linux Server, который можно скачать с Центр безопасности в Microsoft Defender в эту новую папку файлов.</span><span class="sxs-lookup"><span data-stu-id="8bff6-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="8bff6-113">На рабочей станции Chef перейдите в папку mdatp/recipes.</span><span class="sxs-lookup"><span data-stu-id="8bff6-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="8bff6-114">Эта папка создается при сгенерировании кулинарной книги.</span><span class="sxs-lookup"><span data-stu-id="8bff6-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="8bff6-115">Используйте предпочитаемый текстовый редактор (например, vi или nano), чтобы добавить следующие инструкции к концу файла default.rb:</span><span class="sxs-lookup"><span data-stu-id="8bff6-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="8bff6-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="8bff6-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="8bff6-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="8bff6-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="8bff6-118">Затем сохраните и закроите файл default.rb.</span><span class="sxs-lookup"><span data-stu-id="8bff6-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="8bff6-119">Далее создайте новый файл рецептов с именем install_mdatp.rb в папке рецептов и добавьте этот текст в файл:</span><span class="sxs-lookup"><span data-stu-id="8bff6-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="8bff6-120">Чтобы соответствовать развертываемой версии и каналу, необходимо изменить имя версии, рассылку и репо.</span><span class="sxs-lookup"><span data-stu-id="8bff6-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="8bff6-121">Далее следует создать файл onboard_mdatp.rb в папке mdatp/recipies.</span><span class="sxs-lookup"><span data-stu-id="8bff6-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="8bff6-122">Добавьте следующий текст в этот файл:</span><span class="sxs-lookup"><span data-stu-id="8bff6-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="8bff6-123">Обязательно обновим имя пути к расположению бортового файла.</span><span class="sxs-lookup"><span data-stu-id="8bff6-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="8bff6-124">Чтобы протестировать развертывание на рабочей станции Chef, просто запустите ``sudo chef-client -z -o mdatp`` .</span><span class="sxs-lookup"><span data-stu-id="8bff6-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="8bff6-125">После развертывания следует рассмотреть возможность создания и развертывания файла конфигурации на серверах на основе набора предпочтений  [для Microsoft Defender для конечной](/linux-preferences.md)точки в Linux.</span><span class="sxs-lookup"><span data-stu-id="8bff6-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender for Endpoint on Linux](/linux-preferences.md).</span></span>  
<span data-ttu-id="8bff6-126">После создания и тестирования файла конфигурации вы можете поместить его в папку cookbook/mdatp/files, где вы также разместили пакет onboarding.</span><span class="sxs-lookup"><span data-stu-id="8bff6-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="8bff6-127">Затем вы можете создать файл settings_mdatp.rb в папке mdatp/recipies и добавить этот текст:</span><span class="sxs-lookup"><span data-stu-id="8bff6-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="8bff6-128">Чтобы включить этот шаг в состав рецепта, просто добавьте include_recipe ':: settings_mdatp' в файл default.rb в папке рецептов.</span><span class="sxs-lookup"><span data-stu-id="8bff6-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="8bff6-129">Вы также можете использовать crontab для расписания автоматических обновлений Расписание обновления [Microsoft Defender для конечной точки (Linux).](linux-update-MDE-Linux.md)</span><span class="sxs-lookup"><span data-stu-id="8bff6-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="8bff6-130">Удалить MDATP книги:</span><span class="sxs-lookup"><span data-stu-id="8bff6-130">Uninstall MDATP cookbook:</span></span>

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

