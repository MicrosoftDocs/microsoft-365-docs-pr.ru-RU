---
title: Развертывание Microsoft Defender для конечной точки на Linux вручную
ms.reviewer: ''
description: Описывает, как развернуть Microsoft Defender для конечной точки на Linux вручную из командной строки.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 2b75a9f4446c875e73245aa7d51e8fcc15e8d23c
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53195025"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="b7531-104">Развертывание Microsoft Defender для конечной точки на Linux вручную</span><span class="sxs-lookup"><span data-stu-id="b7531-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b7531-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b7531-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7531-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b7531-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7531-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7531-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b7531-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b7531-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b7531-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b7531-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b7531-110">В этой статье описывается, как развернуть Microsoft Defender для конечной точки на Linux вручную.</span><span class="sxs-lookup"><span data-stu-id="b7531-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="b7531-111">Успешное развертывание требует выполнения всех следующих задач:</span><span class="sxs-lookup"><span data-stu-id="b7531-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="b7531-112">Развертывание Microsoft Defender для конечной точки на Linux вручную</span><span class="sxs-lookup"><span data-stu-id="b7531-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="b7531-113">Необходимые условия и требования к системе</span><span class="sxs-lookup"><span data-stu-id="b7531-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="b7531-114">Настройка репозитория программного обеспечения Linux</span><span class="sxs-lookup"><span data-stu-id="b7531-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="b7531-115">RHEL и варианты (CentOS и Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="b7531-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="b7531-116">SLES и варианты</span><span class="sxs-lookup"><span data-stu-id="b7531-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="b7531-117">Системы Ubuntu и Debian</span><span class="sxs-lookup"><span data-stu-id="b7531-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="b7531-118">Установка приложения</span><span class="sxs-lookup"><span data-stu-id="b7531-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="b7531-119">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="b7531-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="b7531-120">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="b7531-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="b7531-121">Сценарий установки</span><span class="sxs-lookup"><span data-stu-id="b7531-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="b7531-122">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="b7531-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="b7531-123">Обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="b7531-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="b7531-124">Uninstallation</span><span class="sxs-lookup"><span data-stu-id="b7531-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="b7531-125">Необходимые условия и требования к системе</span><span class="sxs-lookup"><span data-stu-id="b7531-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="b7531-126">Перед началом работы см. в [веб-сайте Microsoft Defender для конечной](microsoft-defender-endpoint-linux.md) точки на Linux описание необходимых условий и системных требований для текущей версии программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="b7531-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="b7531-127">Настройка репозитория программного обеспечения Linux</span><span class="sxs-lookup"><span data-stu-id="b7531-127">Configure the Linux software repository</span></span>

<span data-ttu-id="b7531-128">Защитник для конечной точки на Linux можно развернуть с одного из следующих каналов (обозначается ниже как *[канал]):* *инсайдеры-быстрые,* инсайдеры-медленные или *prod*.  Каждый из этих каналов соответствует репозиторию программного обеспечения Linux.</span><span class="sxs-lookup"><span data-stu-id="b7531-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="b7531-129">Ниже приведены инструкции по настройке устройства для использования одного из этих репозиториев.</span><span class="sxs-lookup"><span data-stu-id="b7531-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="b7531-130">Выбор канала определяет тип и частоту обновлений, предлагаемых вашему устройству.</span><span class="sxs-lookup"><span data-stu-id="b7531-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="b7531-131">Устройства в *инсайдерской* быстрой являются первыми, которые получают обновления и новые функции, а затем инсайдеры *медленно* и, *наконец, prod*.</span><span class="sxs-lookup"><span data-stu-id="b7531-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="b7531-132">Для предварительного просмотра новых функций и обеспечения ранней обратной связи рекомендуется настроить  некоторые устройства в вашем предприятии, чтобы использовать как инсайдеры-быстрые, так и *инсайдеры-медленные*.</span><span class="sxs-lookup"><span data-stu-id="b7531-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="b7531-133">Переключение канала после начальной установки требует повторной установки продукта.</span><span class="sxs-lookup"><span data-stu-id="b7531-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="b7531-134">Чтобы переключить канал продукта: удалить существующий пакет, перенастройте устройство для использования нового канала и выполните действия в этом документе, чтобы установить пакет из нового расположения.</span><span class="sxs-lookup"><span data-stu-id="b7531-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="b7531-135">RHEL и варианты (CentOS и Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="b7531-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="b7531-136">Установка, `yum-utils` если она еще не установлена:</span><span class="sxs-lookup"><span data-stu-id="b7531-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="b7531-137">Обратите внимание на рассылку и версию и определите ближайшую запись (по мажорной, затем второстепенной) для нее в `https://packages.microsoft.com/config/` статье .</span><span class="sxs-lookup"><span data-stu-id="b7531-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="b7531-138">Например, RHEL 7.9 ближе к 7.4, чем к 8.</span><span class="sxs-lookup"><span data-stu-id="b7531-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="b7531-139">В приведенных ниже командах *замените [distro]* *и [version]* данными, которые вы определили:</span><span class="sxs-lookup"><span data-stu-id="b7531-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7531-140">В случае Oracle Linux *замените [дистрибутив]* на "rhel".</span><span class="sxs-lookup"><span data-stu-id="b7531-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="b7531-141">Например, если вы работаете с CentOS 7 и хотите развернуть Defender для конечной точки на Linux из *прод-канала:*</span><span class="sxs-lookup"><span data-stu-id="b7531-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="b7531-142">Или, если вы хотите изучить новые функции на выбранных устройствах, вы можете развернуть Microsoft Defender для конечной точки на Linux в канале с быстрыми *инсайдерами:*</span><span class="sxs-lookup"><span data-stu-id="b7531-142">Or if you wish to explore new features on selected devices, you might want to deploy Microsoft Defender for Endpoint on Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="b7531-143">Установите общедоступный ключ Microsoft GPG:</span><span class="sxs-lookup"><span data-stu-id="b7531-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="b7531-144">Скачайте и сделайте возможными все метаданные для текущих репозиториев yum с включенной поддержкой:</span><span class="sxs-lookup"><span data-stu-id="b7531-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="b7531-145">SLES и варианты</span><span class="sxs-lookup"><span data-stu-id="b7531-145">SLES and variants</span></span>

- <span data-ttu-id="b7531-146">Обратите внимание на распространение и версию и определите ближайшую запись (по мажорной, затем второстепенной) для нее под `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="b7531-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="b7531-147">В следующих командах *замените [distro]* *и [версию]* данными, которые вы определили:</span><span class="sxs-lookup"><span data-stu-id="b7531-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="b7531-148">Например, если вы работаете с SLES 12 и хотите развернуть Microsoft Defender для конечной точки на Linux из *прод-канала:*</span><span class="sxs-lookup"><span data-stu-id="b7531-148">For example, if you are running SLES 12 and wish to deploy Microsoft Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="b7531-149">Установите общедоступный ключ Microsoft GPG:</span><span class="sxs-lookup"><span data-stu-id="b7531-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="b7531-150">Системы Ubuntu и Debian</span><span class="sxs-lookup"><span data-stu-id="b7531-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="b7531-151">Установка, `curl` если она еще не установлена:</span><span class="sxs-lookup"><span data-stu-id="b7531-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="b7531-152">Установка, `libplist-utils` если она еще не установлена:</span><span class="sxs-lookup"><span data-stu-id="b7531-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="b7531-153">Обратите внимание на рассылку и версию и определите ближайшую запись (по мажорной, затем второстепенной) для нее в `https://packages.microsoft.com/config` статье .</span><span class="sxs-lookup"><span data-stu-id="b7531-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="b7531-154">В приведенной ниже команде *замените [distro]* *и [version]* данными, которые вы определили:</span><span class="sxs-lookup"><span data-stu-id="b7531-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="b7531-155">Например, если вы работаете в Ubuntu 18.04 и хотите развернуть MDE для Linux из *прод-канала:*</span><span class="sxs-lookup"><span data-stu-id="b7531-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="b7531-156">Установка конфигурации репозиториев:</span><span class="sxs-lookup"><span data-stu-id="b7531-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="b7531-157">Например, если вы выбрали *канал prod:*</span><span class="sxs-lookup"><span data-stu-id="b7531-157">For example, if you chose *prod* channel:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- <span data-ttu-id="b7531-158">Установите `gpg` пакет, если он еще не установлен:</span><span class="sxs-lookup"><span data-stu-id="b7531-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="b7531-159">Если `gpg` нет, установите `gnupg` .</span><span class="sxs-lookup"><span data-stu-id="b7531-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="b7531-160">Установите общедоступный ключ Microsoft GPG:</span><span class="sxs-lookup"><span data-stu-id="b7531-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="b7531-161">Установите драйвер https, если он еще не присутствует:</span><span class="sxs-lookup"><span data-stu-id="b7531-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="b7531-162">Обновление метаданных репозиториев:</span><span class="sxs-lookup"><span data-stu-id="b7531-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="b7531-163">Установка приложения</span><span class="sxs-lookup"><span data-stu-id="b7531-163">Application installation</span></span>

- <span data-ttu-id="b7531-164">RHEL и варианты (CentOS и Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="b7531-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="b7531-165">Если на вашем устройстве настроено несколько репозиториев Майкрософт, можно уникать, из каких репозиториев установить пакет.</span><span class="sxs-lookup"><span data-stu-id="b7531-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="b7531-166">В следующем примере показано, как установить пакет из канала, если на этом устройстве также настроен канал `production` `insiders-fast` репозиториев.</span><span class="sxs-lookup"><span data-stu-id="b7531-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="b7531-167">Такая ситуация может произойти, если вы используете несколько продуктов Майкрософт на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="b7531-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="b7531-168">В зависимости от распространения и версии сервера псевдоним репозитория может быть иным, чем в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b7531-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- <span data-ttu-id="b7531-169">SLES и варианты:</span><span class="sxs-lookup"><span data-stu-id="b7531-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="b7531-170">Если на вашем устройстве настроено несколько репозиториев Майкрософт, можно уникать, из каких репозиториев установить пакет.</span><span class="sxs-lookup"><span data-stu-id="b7531-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="b7531-171">В следующем примере показано, как установить пакет из канала, если на этом устройстве также настроен канал `production` `insiders-fast` репозиториев.</span><span class="sxs-lookup"><span data-stu-id="b7531-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="b7531-172">Такая ситуация может произойти, если вы используете несколько продуктов Майкрософт на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="b7531-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- <span data-ttu-id="b7531-173">Система Ubuntu и Debian:</span><span class="sxs-lookup"><span data-stu-id="b7531-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="b7531-174">Если на вашем устройстве настроено несколько репозиториев Майкрософт, можно уникать, из каких репозиториев установить пакет.</span><span class="sxs-lookup"><span data-stu-id="b7531-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="b7531-175">В следующем примере показано, как установить пакет из канала, если на этом устройстве также настроен канал `production` `insiders-fast` репозиториев.</span><span class="sxs-lookup"><span data-stu-id="b7531-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="b7531-176">Такая ситуация может произойти, если вы используете несколько продуктов Майкрософт на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="b7531-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="b7531-177">Скачайте пакет onboarding</span><span class="sxs-lookup"><span data-stu-id="b7531-177">Download the onboarding package</span></span>

<span data-ttu-id="b7531-178">Скачайте бортовой пакет из Центр безопасности в Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="b7531-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="b7531-179">В Центр безопасности в Microsoft Defender перейдите **к Параметры > управления устройствами > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="b7531-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="b7531-180">В первом выпадаемом меню выберите **Linux Server** в качестве операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b7531-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="b7531-181">Во втором выпадаемом меню выберите локальный скрипт **(для до 10 устройств)** в качестве метода развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7531-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="b7531-182">Выберите **пакет загрузки.**</span><span class="sxs-lookup"><span data-stu-id="b7531-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="b7531-183">Сохраните файл как WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="b7531-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Центр безопасности в Microsoft Defender скриншот](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="b7531-185">С командной подсказки убедитесь, что у вас есть файл.</span><span class="sxs-lookup"><span data-stu-id="b7531-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="b7531-186">Извлечение содержимого архива:</span><span class="sxs-lookup"><span data-stu-id="b7531-186">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a><span data-ttu-id="b7531-187">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="b7531-187">Client configuration</span></span>

1. <span data-ttu-id="b7531-188">Скопируйте MicrosoftDefenderATPOnboardingLinuxServer.py на целевое устройство.</span><span class="sxs-lookup"><span data-stu-id="b7531-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="b7531-189">Изначально клиентские устройства не связаны с организацией.</span><span class="sxs-lookup"><span data-stu-id="b7531-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="b7531-190">Обратите внимание, что атрибут *orgId* пустой:</span><span class="sxs-lookup"><span data-stu-id="b7531-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="b7531-191">Запустите MicrosoftDefenderATPOnboardingLinuxServer.py и обратите внимание, что для запуска этой команды необходимо установить `python` на устройстве:</span><span class="sxs-lookup"><span data-stu-id="b7531-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py, and note that, in order to run this command, you must have `python` installed on the device:</span></span>

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="b7531-192">Убедитесь, что устройство теперь связано с организацией и сообщает допустимый идентификатор организации:</span><span class="sxs-lookup"><span data-stu-id="b7531-192">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="b7531-193">Через несколько минут после завершения установки можно увидеть состояние, вы выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b7531-193">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="b7531-194">Возвращаемая величина `1` обозначает, что продукт функционирует так, как ожидалось:</span><span class="sxs-lookup"><span data-stu-id="b7531-194">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="b7531-195">Когда продукт запускается в первый раз, он скачивает последние определения противомалярийных программ.</span><span class="sxs-lookup"><span data-stu-id="b7531-195">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="b7531-196">В зависимости от подключения к Интернету это может занять до нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="b7531-196">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="b7531-197">В течение этого времени вышеуказанная команда возвращает значение `false` .</span><span class="sxs-lookup"><span data-stu-id="b7531-197">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="b7531-198">Состояние обновления определения можно проверить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="b7531-198">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="b7531-199">Обратите внимание, что после завершения начальной установки может потребоваться настроить прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b7531-199">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="b7531-200">См. в публикации Configure Defender for Endpoint on Linux для обнаружения статического [прокси-сервера: конфигурация после установки.](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)</span><span class="sxs-lookup"><span data-stu-id="b7531-200">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="b7531-201">Запустите тест обнаружения, чтобы убедиться, что устройство правильно на борту, и сообщить об этом службе.</span><span class="sxs-lookup"><span data-stu-id="b7531-201">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="b7531-202">Выполните следующие действия на недавно созданном устройстве:</span><span class="sxs-lookup"><span data-stu-id="b7531-202">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="b7531-203">Убедитесь, что в режиме реального времени включена защита (обозначаемая в результате запуска `1` следующей команды):</span><span class="sxs-lookup"><span data-stu-id="b7531-203">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="b7531-204">Откройте окно терминала.</span><span class="sxs-lookup"><span data-stu-id="b7531-204">Open a Terminal window.</span></span> <span data-ttu-id="b7531-205">Скопируйте и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7531-205">Copy and execute the following command:</span></span>

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="b7531-206">Файл должен был быть карантином для Defender для конечной точки на Linux.</span><span class="sxs-lookup"><span data-stu-id="b7531-206">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="b7531-207">Чтобы перечислить все обнаруженные угрозы, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7531-207">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a><span data-ttu-id="b7531-208">Опыт использования обнаружение и нейтрализация атак на конечные точки (EDR) с имитацией атак</span><span class="sxs-lookup"><span data-stu-id="b7531-208">Experience Linux endpoint detection and response (EDR) capabilities with simulated attacks</span></span>

<span data-ttu-id="b7531-209">Чтобы проверить функциональные возможности EDR Linux, выполните ниже шаги, чтобы смоделировать обнаружение на сервере Linux и изучить этот случай.</span><span class="sxs-lookup"><span data-stu-id="b7531-209">To test out the functionalities of EDR for Linux, follow the steps below to simulate a detection on your Linux server and investigate the case.</span></span> 

1.  <span data-ttu-id="b7531-210">Убедитесь, что на борту linux-сервера отображается Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b7531-210">Verify that the onboarded Linux server appears in Microsoft Defender Security Center.</span></span> <span data-ttu-id="b7531-211">Если это первый бортовой аппарат, это может занять до 20 минут, пока он не появится.</span><span class="sxs-lookup"><span data-stu-id="b7531-211">If this is the first onboarding of the machine, it can take up to 20 minutes until it appears.</span></span> 

2.  <span data-ttu-id="b7531-212">Скачайте и извлеките [файл скрипта](https://aka.ms/LinuxDIY) на бортовой сервер Linux и запустите следующую команду: `./mde_linux_edr_diy.sh`</span><span class="sxs-lookup"><span data-stu-id="b7531-212">Download and extract the [script file](https://aka.ms/LinuxDIY) to an onboarded Linux server and run the following command: `./mde_linux_edr_diy.sh`</span></span>

3.  <span data-ttu-id="b7531-213">Через несколько минут обнаружение должно быть поднято в Центр безопасности в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b7531-213">After a few minutes, a detection should be raised in Microsoft Defender Security Center.</span></span>

4.  <span data-ttu-id="b7531-214">Посмотрите на сведения оповещений, временную шкалу машины и выполните типичные действия по расследованию.</span><span class="sxs-lookup"><span data-stu-id="b7531-214">Look at the alert details, machine timeline, and perform your typical investigation steps.</span></span>




## <a name="installer-script"></a><span data-ttu-id="b7531-215">Сценарий установки</span><span class="sxs-lookup"><span data-stu-id="b7531-215">Installer script</span></span>

<span data-ttu-id="b7531-216">Кроме того, вы можете [](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) использовать автоматический скрипт bash установки, предоставляемый в нашем [репозитории GitHub.](https://github.com/microsoft/mdatp-xplat/)</span><span class="sxs-lookup"><span data-stu-id="b7531-216">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="b7531-217">Сценарий определяет распределение и версию и настраивает устройство, чтобы вытащить последний пакет и установить его.</span><span class="sxs-lookup"><span data-stu-id="b7531-217">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="b7531-218">Вы также можете работать на борту с предоставленным скриптом.</span><span class="sxs-lookup"><span data-stu-id="b7531-218">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

<span data-ttu-id="b7531-219">Подробнее [здесь](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span><span class="sxs-lookup"><span data-stu-id="b7531-219">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="b7531-220">Проблемы с установкой журнала</span><span class="sxs-lookup"><span data-stu-id="b7531-220">Log installation issues</span></span>

<span data-ttu-id="b7531-221">Дополнительные [сведения о](linux-resources.md#log-installation-issues) том, как найти автоматически созданный журнал, созданный установщиком при ошибке, см. в дополнительных сведениях о проблемах установки журнала.</span><span class="sxs-lookup"><span data-stu-id="b7531-221">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="b7531-222">Обновления операционной системы</span><span class="sxs-lookup"><span data-stu-id="b7531-222">Operating system upgrades</span></span>

<span data-ttu-id="b7531-223">При обновлении операционной системы до новой основной версии необходимо сначала удалить Defender для конечной точки на Linux, установить обновление и, наконец, перенастроить Defender для конечной точки на Linux на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="b7531-223">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="b7531-224">Миграция из Insiders-Fast в канал Production</span><span class="sxs-lookup"><span data-stu-id="b7531-224">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="b7531-225">Удалить версию "Insiders-Fast channel" Defender для конечной точки на Linux.</span><span class="sxs-lookup"><span data-stu-id="b7531-225">Uninstall the “Insiders-Fast channel” version of Defender for Endpoint on Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="b7531-226">Отключение конечной точки Defender для Linux Insiders-Fast репо  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="b7531-226">Disable the Defender for Endpoint on Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7531-227">Вывод должен показывать "packages-microsoft-com-fast-prod".</span><span class="sxs-lookup"><span data-stu-id="b7531-227">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="b7531-228">Передиплой MDE для Linux с помощью "Производственного канала".</span><span class="sxs-lookup"><span data-stu-id="b7531-228">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="b7531-229">Uninstallation</span><span class="sxs-lookup"><span data-stu-id="b7531-229">Uninstallation</span></span>

<span data-ttu-id="b7531-230">Сведения о том, как удалить Defender для конечной точки на Linux с клиентских устройств, см. в материале [Uninstall.](linux-resources.md#uninstall)</span><span class="sxs-lookup"><span data-stu-id="b7531-230">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7531-231">См. также</span><span class="sxs-lookup"><span data-stu-id="b7531-231">See also</span></span>
- [<span data-ttu-id="b7531-232">Исследование проблем работоспособности агента</span><span class="sxs-lookup"><span data-stu-id="b7531-232">Investigate agent health issues</span></span>](health-status.md)
