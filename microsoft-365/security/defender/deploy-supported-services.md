---
title: Развертывание служб, поддерживаемых Microsoft 365 Defender
description: Узнайте о службах безопасности Майкрософт, которые могут быть интегрированы Microsoft 365 Defender, их лицензионных требованиях и процедурах развертывания
keywords: развертывание, лицензии, поддерживаемые службы, подготовка, настройка Microsoft 365 Defender, M365, право на лицензию, Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security, MCAS, E5, A5, EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
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
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935681"
---
# <a name="deploy-supported-services"></a>Развертывание поддерживаемых служб

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Microsoft 365 Defender](microsoft-365-defender.md) интегрирует различные службы безопасности Майкрософт, чтобы обеспечить централизованные возможности обнаружения, предотвращения и расследования от сложных атак. В этой статье описываются поддерживаемые службы, их требования к лицензированию, преимущества и ограничения, связанные с развертыванием одной или более служб, а также ссылки на возможность их полного развертывания по отдельности.

## <a name="supported-services"></a>Поддерживаемые службы
Лицензия Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимая комбинация лицензий предоставляет доступ к следующим поддерживаемым службам и дает вам право использовать Microsoft 365 Defender в центре Microsoft 365 безопасности. [См. требования к лицензированию](prerequisites.md#licensing-requirements)

| Поддерживаемая служба | Описание |
| ------ | ------ |
| Microsoft Defender для конечной точки | Набор защиты конечных точек, построенный вокруг мощных поведенческих датчиков, облачной аналитики и аналитики угроз |
|Microsoft Defender для Office 365 | Расширенные средства защиты приложений и данных в Office 365, включая электронную почту и другие средства совместной работы |
| Microsoft Defender для удостоверений | Защита от расширенных угроз, скомпрометанных удостоверений и вредоносных инсайдеров с помощью коррелирующих сигналов Active Directory |
| Microsoft Cloud App Security | Определение и борьба с киберугрозами в облачных службах Майкрософт и сторонних поставщиков |

## <a name="deployed-services-and-functionality"></a>Развернутые службы и функциональные возможности
Microsoft 365 Defender обеспечивает лучшую видимость, корреляцию и исправление при развертывании дополнительных поддерживаемых служб.

### <a name="benefits-of-full-deployment"></a>Преимущества полного развертывания
Чтобы получить все преимущества Microsoft 365 Defender, рекомендуется развернуть все поддерживаемые службы. Вот некоторые основные преимущества полного развертывания:
- Инциденты выявляются и коррелируются на основе оповещений и сигналов событий от всех доступных датчиков и возможностей анализа, определенных для службы.
- Автоматические учебники по расследованию и исправлению (AIR) применяются к различным типам сущности, включая устройства, почтовые ящики и учетные записи пользователей
- Можно запрашивать более полную схему охоты для данных событий и сущности с устройств, почтовых ящиков и других сущностей.

### <a name="limited-deployment-scenarios"></a>Ограниченные сценарии развертывания
Каждая поддерживаемая служба, развертываемая, предоставляет чрезвычайно богатый набор необработанных сигналов, а также сопоставляет информацию. Хотя ограниченное развертывание не вызывает отключения Microsoft 365 Defender, это влияет на его способность обеспечить всестороннюю видимость в конечных точках, приложениях, данных и удостоверениях. В то же время любые возможности восстановления применяются только к сущностям, которыми могут управлять развернутые службы.

В приведенной ниже таблице перечислены, как каждая поддерживаемая служба предоставляет дополнительные данные, возможности получения дополнительных данных путем сопоставления данных и улучшения возможностей по исправлению ситуации и реагированию.

| Служба | Данные (сигналы & данные) | Область & реагирования |
| ------ | ------ | ------ |
| Microsoft Defender для конечной точки | - Состояния конечной точки и необработанные события<br />- Обнаружение и оповещение конечной точки, включая антивирусные, EDR, уменьшение поверхности атаки<br />- Сведения о файлах и других сущностями, наблюдаемых на конечных точках | Конечные точки |
|Microsoft Defender для Office 365 | - Состояния почты и почтовых ящиков и необработанные события<br />- Обнаружение электронной почты, вложений и ссылок | - Почтовые ящики<br />- Microsoft 365 учетные записи |
| Microsoft Defender для удостоверений | - Сигналы Active Directory, включая события проверки подлинности<br />- Обнаружение поведенческих данных, связанных с удостоверениями | Удостоверения |
| Microsoft Cloud App Security | - Обнаружение несанкционных облачных приложений и служб (теневых ИТ)<br />- Подвержение данных облачным приложениям<br />- Действие угрозы, связанное с облачными приложениями | Облачные приложения |

## <a name="deploy-the-services"></a>Развертывание служб
Развертывание каждой службы обычно требует предварительной настройки для клиента и начальной конфигурации. Чтобы понять, как развертываются эти службы, см. в следующей таблице.

| Служба | Инструкции по подготовкам | Исходная конфигурация |
| ------ | ------ | ------ |
| Microsoft Defender для конечной точки | [Руководство по развертыванию Microsoft Defender для конечной точки](../defender-endpoint/deployment-phases.md) | *См. инструкции по обеспечению* |
|Microsoft Defender для Office 365 | *Нет, с Office 365* | [Настройка политик Microsoft Defender для Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| Microsoft Defender для удостоверений | [Quickstart: создание экземпляра Microsoft Defender для удостоверений](/azure-advanced-threat-protection/install-atp-step1) | *См. инструкции по обеспечению* |
| Microsoft Cloud App Security | *Нет* | [Quickstart: начало работы с Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security) |

После развертывания поддерживаемых служб включаем [Microsoft 365 Defender.](m365d-enable.md)

## <a name="related-topics"></a>Статьи по теме

- [Microsoft 365 Обзор defender](microsoft-365-defender.md)
- [Включение Microsoft 365 Defender](m365d-enable.md)
- [Обзор Microsoft Defender для конечной точки](../defender-endpoint/microsoft-defender-endpoint.md)
- [Обзор Microsoft Defender для Office 365](../office-365-security/defender-for-office-365.md)
- [Обзор Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Обзор Microsoft Defender для удостоверений](/azure-advanced-threat-protection/what-is-atp)
