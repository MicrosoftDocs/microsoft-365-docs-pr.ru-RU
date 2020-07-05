---
title: Этап 2. Готовность каталогов и сети
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как оценить готовность каталогов и сети в среде.
ms.openlocfilehash: 78087b7e0c1cb7031954d3a9ac4188b59879db20
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679018"
---
# <a name="step-2-directory-and-network-readiness"></a>Этап 2. Готовность каталогов и сети

Ensure your directory and the network are configured and ready to support to your shift to Windows 10 and Microsoft 365 Apps for enterprise. This will require Azure Active Directory Services to be in place for users, and your network must have the capacity to handle both its regular traffic and the movement of potentially vast amounts of data as PCs are upgraded, and users’ files, settings and applications are restored.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong>Этап 2. Проверка готовности каталогов и сети</strong></p>
<p>Cloud connected services in Microsoft 365 Apps for enterprise and new deployment options like Windows Autopilot require Azure Active Directory. Your network and connectivity are also important areas to plan when moving Windows images, apps, drivers and related files to your PCs. Learn how new tools and deployment options reduce and streamline network traffic.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Обеспечение готовности каталогов и сети — второй этап рекомендуемого нами процесса развертывания, при котором основное внимание уделяется Azure Active Directory и оптимизации сети. Полный процесс развертывания для настольных ПК описан в статье [Центр развертывания компьютеров](https://aka.ms/HowToShift).
>

Directory and Network readiness is fundamental to ensuring a smooth OS and desktop deployment. As with any automated deployment, it is important to ensure your file shares can be reached, and your network will need to be able to support the transfer of very large files, possibly to hundreds or even thousands of PCs at a time.

With your shift to Windows 10 and Microsoft 365 Apps for enterprise you also now need to make sure that cloud-based identity is set up with Azure Active Directory. This is key not only to activating Microsoft 365 Apps for enterprise, it also allows you to take advantage of modern provisioning solutions like Windows Autopilot.

В этой статье мы рассмотрим инструменты и варианты подготовки служб каталогов, а также разрешения для пользователей и устройств, готовые к развертыванию в Windows 10 и в приложениях Microsoft 365 для предприятий.

## <a name="adding-azure-active-directory"></a>Добавление Azure Active Directory

Если в вашей организации уже используются Office 365, Exchange Online, Microsoft Intune или другие веб-службы Майкрософт, то спешим вас обрадовать: вы уже используете Azure Active Directory. Если это так, то вам достаточно убедиться, что пользователи, на компьютерах которых выполняется развертывание, зарегистрированы в Azure Active Directory и им назначены лицензии.

Если в настоящее время вы не используете службу Azure Active Directory, существует [множество ресурсов](https://docs.microsoft.com/azure/active-directory/), которые помогут вам настроить ее. Возможно, вам доступна индивидуальная поддержка через Microsoft FastTrack в рамках вашей лицензии. Подробнее о Microsoft FastTrack см. [здесь](https://fasttrack.microsoft.com).

После настройки Azure Active Directory пользователи смогут входить в свои приложения Microsoft 365 для предприятий и активировать их, а вы сможете автоматически развертывать приложения и политики с помощью Microsoft Intune или Windows Autopilot.

## <a name="network-readiness"></a>Готовность сети

Планируя развертывание, следует учитывать требования к пропускной способности. Три основных компонента развертывания, которые повлияют на сеть — это создание образов ПК, обновления программного обеспечения и персонализация пользователей. Сочетание этих факторов может добавлять до 20 ГБ на компьютер при первоначальной миграции, а зачастую — от 1 ГБ в месяц на обновление каждого компьютера.

Для начала рассмотрим требования к каждому из этих трех компонентов:

### <a name="pc-imaging"></a>Создание образа ПК

Как правило, для образов Windows без модификаций следует выделять по 3 ГБ на компьютер, а для настроенных образов с приложениями может потребоваться до 6 ГБ или даже больше. Кроме того, может потребоваться учесть пакеты драйверов. Они могут занимать по несколько сотен мегабайт на каждом компьютере, иногда до 1 ГБ.

### <a name="software-updates"></a>Обновления программного обеспечения

Вам потребуется запланировать полосу пропускания для обновлений ПО. В Windows 10 и в приложениях Microsoft 365 для предприятий используется новая модель обслуживания с доставкой ежемесячных и полугодовых обновлений. Если вы не знакомы с этой моделью, дополнительные сведения о принципе ее работы можно найти [здесь](https://docs.microsoft.com/windows/deployment/update/waas-overview).

The new servicing model includes Feature Updates for Windows twice a year, Office Semi-Annual Enterprise Channel Updates, and monthly Quality Updates. Feature Updates are typically 2 – 4GB in size, and Office Semi-Annual Enterprise Channel updates are 300 – 400 MB per update. Then there are the monthly Quality Updates. These may range from a few hundred megabytes to over a gigabyte. This is because monthly updates are cumulative, so these increase in size over the servicing lifetime for each Windows 10 version. That said, there are tools that can help reduce the amount of data that must pass over the network to implement updates. We will cover this in more detail below.

### <a name="user-personalization"></a>Персонализация пользователей

The third component to consider is user personalization. Here you need to plan network bandwidth to accommodate the restoring of user files, their settings, and their applications as part of the PC refresh or replacement process. Together, these items often exceed 20 GB per PC; for some users these may exceed 100 GB.

## <a name="limiting-bandwidth"></a>Ограничение пропускной способности

One way to limit the impact of deployment-related traffic on the network is to throttle it using the BITS (Background Intelligent Transfer Service) setting on clients. BITS uses an Adaptive Bit Rate (ABR) to adjust bandwidth available for deployment purposes; it can be configured on clients using Group Policy.

[Сведения о BITS](https://docs.microsoft.com/windows/desktop/bits/about-bits)

Если вы используете Microsoft Endpoint Configuration Manager (Current Branch), вы также можете настроить точки распространения с поддержкой BITS или включить многоадресную рассылку с WDS.

Throttling specific traffic means that normal network traffic is less impacted by PCs downloading updates and applications. But carving out a certain percentage of bandwidth for these tasks helps ensure productivity isn’t impacted by Windows or Office deployment and processes continue to run as needed, it can worsen deployment-related downtime, with users locked out of their PCs while a deployment runs.

К счастью существуют новые инструменты, которые помогут вам управлять воздействием крупномасштабного развертывания на сеть, в том числе LEDBAT для оптимизации использования доступной полосы пропускания и параметры одноранговой передачи (P2P), позволяющие отводить трафик развертывания от центра сети к ее периметру.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-3.png)

## <a name="scavenging-bandwidth"></a>Очистка полосы пропускания

Фоновый транспорт с низкой добавочной задержкой (LEDBAT), поддерживаемый в Windows Server 2019 и Microsoft Endpoint Configuration Manager (Current Branch), предназначен для оптимизации сетевого трафика, адресованного клиентам Windows.

[10 лучших сетевых функций в Windows Server 2019: \#9. LEDBAT — фоновый транспорт с оптимизированной задержкой](https://blogs.technet.microsoft.com/networking/2018/07/25/ledbat/)

Unlike traditional throttling, LEDBAT can use all available network bandwidth as a background task, instantly yielding bandwidth when other traffic requests it. Unlike BITS there is no delay; everything is automated – no manual tuning or scheduling required, and everything is setup server side. This affords potentially massive performance gains.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-4.png)

## <a name="peer-to-peer-options"></a>Параметры одноранговой передачи

Peer-to-Peer options are increasingly being used in Windows 10 migrations, for PC imaging, software updates and user personalization. They are also valuable in facilitating build-to-build upgrades after your initial Windows 10 deployment. Here we will cover several examples to help move Windows 10 and Office-related traffic away from the center of the network, reducing the need for classic throttling approaches, and allowing PCs to find the update files they need on peers in their local network rather than downloading them from a distribution point or the internet.

**BranchCache** can help you download content in distributed environments without saturating the network. It comes in two options: Hosted Cache Mode, which lets you use local servers to cache content, and Distributed Cache Mode (a mode supported in Configuration Manager), which lets clients share already downloaded content with each other.

**Одноранговый кэш.** Клиенты, поддерживаемые в Configuration Manager, также могут использовать одноранговый кэш. Благодаря этому на компьютерах, доступных в сети, можно размещать источники для распространения контента. Его следует включать не на всех компьютерах, а только на тех узлах, где имеется надежное сетевое подключение (например, настольных компьютерах, а также компьютерах в корпусах "мини-башня" или "башня"). Одноранговый кэш может работать даже для задач развертывания, выполняемых на этапах Windows PE во время установки.

Примечание: BranchCache и одноранговый кэш дополняют друг друга и могут совместно работать в одной среде.

[BranchCache и одноранговый кэш](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/)

**Оптимизация доставки.** Оптимизация доставки — это еще одна технология однорангового кэширования, предоставляющая сетевые средства управления для развертываний. Оптимизация доставки Windows 10 предназначена для обновления встроенных приложений UWP, а также для установки приложений из Microsoft Store и обновления программного обеспечения при помощи экспресс-обновлений. Она была доступна с ранних версий Windows 10, но только недавно была интегрирована с Microsoft Endpoint Configuration Manager (Current Branch). Начиная с Windows 10 версии 1803, новые параметры конфигурации позволяют независимо задавать ограничения пропускной способности для фоновых обновлений и задач переднего плана, таких как установка приложений из Microsoft Store. Оптимизация доставки Windows теперь также обеспечивает поддержку приложений Microsoft 365 для предприятий во время обновления клиентов для всех поддерживаемых каналов. Скоро будет доступна поддержка оптимизации доставки Windows во время первоначальной установки клиента.  

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-5.png)

**Дополнительные соображения для приложений Microsoft 365 для предприятий**

Можно использовать не только оптимизацию доставки, но и еще три элемента, которые помогут вам сократить нагрузку на сеть во время развертывания приложений Microsoft 365 для предприятий.

**Binary Delta Compression** Microsoft 365 Apps for enterprise uses Binary Delta Compression to reduce bandwidth consumed by software updates when updating from the most recent release of Microsoft 365 Apps for enterprise to the next release. By only pulling the binary level changes from the previous release, the impact from month-over-month growth of cumulative updates is minimized. This has the potential of saving several hundred megabytes of data, per PC, each month. In order to use this capability though, you cannot skip releases. If you do, then the full cumulative update must be downloaded.

[Скачивание обновлений для приложений Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-process-microsoft-365-apps#download-the-updates-for-microsoft-365-apps)

**Файлы данных Outlook.** Outlook часто настраивают на локальное кэширование всего почтового ящика пользователя для автономного использования. При любом развертывании Windows, кроме обновления на месте, для этого требуется, чтобы файлы данных Outlook пользователя восстановились после обновления. Этот процесс автоматизирован, но так как ограничения почтовых ящиков Outlook обычно составляют 100 ГБ, для повторного локального кэширования всего почтового ящика потребуется передать много данных Чтобы снизить нагрузку на сеть, вы можете использовать групповую политику, уменьшив значение параметра "Почта, которая должна храниться локально". В Outlook в составе приложений Microsoft 365 для предприятий и Office 2016 по умолчанию задано значение 12 месяцев. Рекомендуем задать срок действия автономного кэша от 1 до 6 месяцев. Изменение этого параметра не повлияет на размер почтового ящика в Интернете, и при наличии сетевого подключения по-прежнему можно будет выполнять поиск по всему почтовому ящику через Outlook.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-6.png)

**Файлы по запросу и перенос известных папок в OneDrive.** OneDrive — отличное средство для синхронизации и защиты файлов пользователя с компьютеров и других устройств в облаке. При переносе известных папок вы можете принудительно синхронизировать файлы из папок "Рабочий стол", "Документы" и "Изображения" в хранилище OneDrive пользователя, делая эти файлы доступными при входе на новое устройство или компьютер, переустановленный из образа. Однако помните, что по причине огромного размера и количества файлов в этих папках следует тщательно распланировать развертывание политик, включающих и применяющих OneDrive на компьютерах. Один из вариантов — использовать сетевые средства управления групповыми политиками, чтобы регулировать полосу пропускания, используемую службой синхронизации OneDrive.

![](../media/step-2-directory-and-network-readiness-media/step-2-directory-and-network-readiness-media-7.png)

[Настройка переноса известных папок](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/Migrate-Your-Files-to-OneDrive-Easily-with-Known-Folder-Move/ba-p/207076)

[Файлы OneDrive по запросу](https://www.microsoft.com/microsoft-365/blog/2017/05/11/introducing-onedrive-files-on-demand-and-additional-features-making-it-easier-to-access-and-share-files/)

Если вы еще не развернули OneDrive, то переход с Windows 7 на Windows 10 станет отличной возможностью для включения службы OneDrive. Кроме того, эта служба отлично интегрируется с приложениями Microsoft 365 для предприятий. Рекомендуем начать это развертывание при подготовке приложений и устройств. Благодаря этому синхронизация файлов начнется до перемещения образов Windows и развертывания приложений в сети.

## <a name="next-step"></a>Следующий этап 

## <a name="step-3-office-and-lob-app-delivery"></a>[Этап 3. Доставка приложений Office и бизнес-приложений](https://aka.ms/mdd3)

## <a name="previous-step"></a>Предыдущий этап:

## <a name="step-1-device-and-app-readiness"></a>[Этап 1. Проверка готовности устройств и приложений](https://aka.ms/mdd1)

## <a name="feedback"></a>Отзывы

We'd love to hear your thoughts. Choose the type you'd like to provide:

Отзыв о продукте. Войдите, чтобы оставить отзыв о документации.

Our new feedback system is built on GitHub Issues. Read about this change in our blog post.
