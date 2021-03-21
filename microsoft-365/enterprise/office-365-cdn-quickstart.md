---
title: Сеть доставки контента Office 365 (CDN) Quickstart
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Сеть доставки контента Office 365 (CDN) Quickstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921598"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Сеть доставки контента Office 365 (CDN) Quickstart

Встроенная сеть доставки **контента Office 365 (CDN)** может использовать встроенную сеть доставки контента (CDN) для статических активов (изображений, JavaScript, Stylesheets, WOFF-файлов), чтобы обеспечить лучшую производительность для страниц SharePoint Online. Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку. Кроме того, CDN Office 365 использует протокол HTTP/2 для улучшения сжатия и http pipelining. Служба CDN Office 365 входит в состав подписки на SharePoint Online.

Дополнительные сведения см. в раздел Использование сети доставки [контента Office 365 (CDN) с SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

>[!NOTE]
>CdN Office 365 доступен только для клиентов в производственном (по всему миру) облаке. Клиенты в облаках правительства США, Китая и Германии в настоящее время не поддерживают CDN Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Используйте средство диагностики страниц для SharePoint для идентификации элементов, не в CDN

Чтобы легко перечислить активы на страницах SharePoint Online, которые можно добавить в cdN-источник, можно использовать расширение браузера page **Diagnostics for SharePoint.**

Средство **Page Diagnostics for SharePoint** — это расширение браузера для нового браузера Microsoft Edge (и браузеры Chrome, которые анализируют современный портал SharePoint Online и классические страницы сайтов https://www.microsoft.com/edge) публикации. Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности. Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](./page-diagnostics-for-spo.md).

При запуске средства диагностики страниц для SharePoint на странице SharePoint Online можно нажать вкладку Диагностические тесты, чтобы увидеть список активов, не принимающихся cdN.  Эти активы будут перечислены в статье Проверка сети доставки контента **(CDN),** как показано на скриншоте ниже.

![Диагностика страниц](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.

## <a name="cdn-overview"></a>Обзор CDN

CDN Office 365 предназначен для оптимизации производительности для пользователей путем распространения часто доступных объектов, таких как изображения и файлы javascript по высокоскоростной глобальной сети, сокращая время загрузки страниц и обеспечивая доступ к объектам, которые находятся как можно ближе к пользователю. CDN извлекает ваши активы из расположения, называемого _происхождением._ Происхождение может быть веб-сайтОм SharePoint, библиотекой документов или папкой, доступной по URL-адресу.

CDN Office 365 разделен на два основных типа:

- **Общедоступный CDN** предназначен для использования для JS (JavaScript), CSS (StyleSheets), Файла веб-шрифтов (WOFF, WOFF2) и несвободных изображений, таких как логотипы компании.
- **Частный CDN** предназначен для использования для изображений (PNG, JPG, JPEG и т.д.).

Вы можете выбрать общедоступные или частные истоки для вашей организации. Большинство организаций будут выбирать для реализации сочетания этих двух. Как общедоступные, так и частные параметры обеспечивают аналогичные преимущества производительности, но каждый из них имеет уникальные атрибуты и преимущества. Дополнительные сведения о общедоступных и частных источниках CDN см. в выпуске Выберите, должно ли каждое происхождение быть [общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Как включить общедоступный и частный CDN с конфигурацией по умолчанию
Прежде чем вносить изменения в параметры CDN клиента, необходимо убедиться, что он соответствует требованиям, политикам безопасности и конфиденциальности вашей организации.

Дополнительные параметры конфигурации или если вы уже включили CDN и хотите добавить дополнительные расположения (истоки), см. в разделе Настройка и настройка [CDN Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) с помощью оболочки управления SharePoint Online

Подключение к клиенту с помощью оболочки управления SharePoint Online:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Чтобы позволить организации использовать общедоступные и частные истоки с конфигурацией по умолчанию, введите следующую команду:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Выход этих комлетов должен выглядеть следующим образом:

![Выход Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>См. также

[Используйте средство диагностики страниц для SharePoint Online](./page-diagnostics-for-spo.md)

[Использование сети доставки содержимого Office 365 с SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Сети доставки содержимого](./content-delivery-networks.md)

[Планирование сети и настройка производительности для Office 365](./network-planning-and-performance.md)

[Серия производительности SharePoint — видеосерия CDN Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)