---
title: Развертывание служб, поддерживаемых Защитником Microsoft 365
description: Узнайте о службах безопасности Майкрософт, которые можно интегрировать с помощью Microsoft 365 Defender, их требованиях к лицензированию и процедурах развертывания
keywords: развертывание, лицензии, поддерживаемые службы, подготовка, настройка Защиты от угроз (Майкрософт), M365, право на получение лицензии, ATP в Microsoft Defender, MDATP, Office 365 ATP, Azure ATP, Microsoft Cloud App Security, MCAS, advanced threat protection, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928966"
---
# <a name="deploy-supported-services"></a>Развертывание поддерживаемых служб

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Защитник Microsoft 365](microsoft-threat-protection.md) интегрирует различные службы безопасности Майкрософт для централизованного обнаружения, предотвращения и исследования сложных атак. В этой статье описываются поддерживаемые службы, их требования к лицензированию, преимущества и ограничения, связанные с развертыванием одной или более служб, а также ссылки на то, как можно полностью развернуть их по отдельности.

## <a name="supported-services"></a>Поддерживаемые службы
Лицензия Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимая комбинация лицензий предоставляет доступ к следующим поддерживаемым службам и позволяет использовать Microsoft 365 Defender в Центре безопасности Microsoft 365. [См. требования к лицензированию](prerequisites.md#licensing-requirements)

| Поддерживаемая служба | Description |
| ------ | ------ |
| Microsoft Defender для конечной точки | Набор endpoint protection, построенный на мощных датчиках поведения, облачной аналитике и аналитике угроз |
|Microsoft Defender для Office 365 | Advanced protection for your apps and data in Office 365, including email and other collaboration tools |
| Microsoft Defender для удостоверений | Защита от сложных угроз, компрометации удостоверений и вредоносных пользователей в предварительной защите с помощью коррелирующих сигналов Active Directory |
| Microsoft Cloud App Security | Выявление и противодействие киберугрозам в облачных службах Майкрософт и сторонних поставщиков |

## <a name="deployed-services-and-functionality"></a>Развернутые службы и функции
Microsoft 365 Defender обеспечивает лучшую видимость, корреляцию и исправление при развертывании дополнительных поддерживаемых служб.

### <a name="benefits-of-full-deployment"></a>Преимущества полного развертывания
Чтобы получить все преимущества Microsoft 365 Defender, рекомендуем развернуть все поддерживаемые службы. Вот некоторые из ключевых преимуществ полного развертывания:
- Инциденты выявляются и сопоставляются на основе оповещений и сигналов событий от всех доступных датчиков и возможностей анализа, характерных для служб
- Книги автоматического исследования и исправлений (AIR) применяются к различным типам сужаемой сущности, включая устройства, почтовые ящики и учетные записи пользователей
- Можно запрошена более комплексная схема более подробной охоты на события и данные сущностей с устройств, почтовых ящиков и других сущностей

### <a name="limited-deployment-scenarios"></a>Ограниченные сценарии развертывания
Каждая развернутая поддерживаемая служба предоставляет очень богатый набор необработанных сигналов, а также коррелирующих сведений. Хотя ограниченное развертывание не приведет к отключению функций Защитника Microsoft 365, его возможность обеспечить комплексную видимость в конечных точках, приложениях, данных и удостоверениях будет затронута. В то же время любые возможности устранения проблем применяются только к сущностям, которыми могут управлять развернутые службы.

В таблице ниже перечислены сведения о том, как каждая поддерживаемая служба предоставляет дополнительные данные, возможности получения дополнительной информации путем сопоставления данных, а также улучшения возможностей устранения и реагирования.

| Служба | Данные (сигналы & коррелирующих данных) | Область ответа & исправлений |
| ------ | ------ | ------ |
| Microsoft Defender для конечной точки | - Состояния конечных точек и необработанные события<br />- Обнаружение и оповещения конечных точек, в том числе антивирусная программа, EDR, уменьшение поверхности атаки<br />- Сведения о файлах и других сущностям, наблюдаемых на конечных точках | Конечные точки |
|Microsoft Defender для Office 365 | - Состояния почты и почтовых ящиков и необработанные события<br />- Обнаружение сообщений электронной почты, вложений и ссылок | - Почтовые ящики<br />- Учетные записи Microsoft 365 |
| Microsoft Defender для удостоверений | - Сигналы Active Directory, включая события проверки подлинности<br />- Обнаружение поведения, связанного с удостоверениями | Удостоверения |
| Microsoft Cloud App Security | - Обнаружение несанкциональных облачных приложений и служб (теневые ИТ-службы)<br />- Экспозиция данных в облачных приложениях<br />- Действия с угрозами, связанные с облачными приложениями | Облачные приложения |

## <a name="deploy-the-services"></a>Развертывание служб
Развертывание каждой службы обычно требует предварительной настройки клиента и начальной настройки. Чтобы понять, как развертываются эти службы, см. следующую таблицу.

| Служба | Инструкции по обеспечению | Исходная конфигурация |
| ------ | ------ | ------ |
| Microsoft Defender для конечной точки | [Руководство по развертыванию Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | *См. инструкции по обеспечению* |
|Microsoft Defender для Office 365 | *Нет, в Office 365* | [Настройка политик Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| Microsoft Defender для удостоверений | [Краткое создание: создание экземпляра Microsoft Defender для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | *См. инструкции по обеспечению* |
| Microsoft Cloud App Security | *Нет* | [Краткое начало: начало работы с Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

После развертывания поддерживаемых служб включите [Microsoft 365 Defender.](mtp-enable.md)

## <a name="related-topics"></a>Связанные статьи

- [Обзор Защитника Microsoft 365](microsoft-threat-protection.md)
- [Включить Microsoft 365 Defender](mtp-enable.md)
- [Обзор Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Обзор Microsoft Defender для Office 365](../office-365-security/office-365-atp.md)
- [Обзор Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Обзор Microsoft Defender для удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
