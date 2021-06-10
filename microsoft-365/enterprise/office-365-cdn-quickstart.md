---
title: Office 365 сеть доставки содержимого (CDN) Quickstart
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
description: Office 365 сеть доставки содержимого (CDN) Quickstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921598"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 сеть доставки содержимого (CDN) Quickstart

Встроенные Office 365 сеть доставки содержимого **(CDN)** можно использовать для статических активов (изображения, JavaScript, Stylesheets, WOFF-файлы), чтобы обеспечить лучшую производительность для SharePoint веб-страниц. Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку. Кроме того, Office 365 CDN протокол HTTP/2 используется для улучшения сжатия и http pipelining. Служба CDN Office 365 входит в состав подписки на SharePoint Online.

Дополнительные сведения см. в [Office 365 сеть доставки содержимого (CDN) с SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

>[!NOTE]
>Этот Office 365 CDN доступен только для клиентов в производственном (по всему миру) облаке. В настоящее время клиенты в облаках правительства США, Китая и Германии не поддерживают Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Используйте средство диагностики страниц для SharePoint для идентификации элементов, не CDN

Вы можете использовать страницу Диагностика для **расширения** SharePoint браузера, чтобы легко перечислить активы на SharePoint-страницы в Интернете, которые можно добавить в CDN происхождения.

Средство **диагностики** страниц для SharePoint является расширением браузера для нового Microsoft Edge (и браузеров Chrome, которые анализируют как современный портал SharePoint, так и классические страницы сайтов https://www.microsoft.com/edge) публикации. Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности. Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](./page-diagnostics-for-spo.md).

При запуске средства диагностики страниц для SharePoint на странице SharePoint Online можно  щелкнуть вкладку Диагностические тесты, чтобы увидеть список активов, которые не CDN. Эти активы будут указаны в заголовке сеть доставки содержимого **(CDN)** как показано на скриншоте ниже.

![Диагностика страниц](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.

## <a name="cdn-overview"></a>CDN Обзор

Эта Office 365 CDN предназначена для оптимизации производительности для пользователей путем распространения часто доступных объектов, таких как изображения и файлы javascript по высокоскоростной глобальной сети, сокращая время загрузки страниц и предоставляя доступ к объектам, которые находятся как можно ближе к пользователю. The CDN извлекает ваши активы из расположения, называемого _происхождением._ Происхождение может быть SharePoint, библиотекой документов или папкой, доступной по URL-адресу.

Раздел Office 365 CDN разделен на два основных типа:

- **Общедоступные CDN** предназначены для использования для JS (JavaScript), CSS (StyleSheets), Файла веб-шрифтов (WOFF, WOFF2) и несвободных изображений, таких как логотипы компании.
- **Частные CDN** предназначены для использования для изображений (PNG, JPG, JPEG и т.д.).

Вы можете выбрать общедоступные или частные истоки для вашей организации. Большинство организаций будут выбирать для реализации сочетания этих двух. Как общедоступные, так и частные параметры обеспечивают аналогичные преимущества производительности, но каждый из них имеет уникальные атрибуты и преимущества. Дополнительные сведения о государственных и частных CDN истоках см. в статью Выберите, должно ли каждое происхождение быть [общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Как включить общедоступные и частные CDN с конфигурацией по умолчанию
Прежде чем вносить изменения в параметры CDN клиента, необходимо убедиться, что он соответствует требованиям, политикам безопасности и конфиденциальности вашей организации.

Дополнительные параметры конфигурации или если вы уже включили CDN и хотите добавить дополнительные расположения (истоки), см. в разделе Настройка и настройка Office 365 CDN с помощью [SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Подключение клиенту с помощью SharePoint Online Management Shell:

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

[SharePoint Серия производительности — Office 365 CDN видеосериалов](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)