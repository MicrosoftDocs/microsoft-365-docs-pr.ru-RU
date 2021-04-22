---
title: Интеграция Microsoft Defender для конечной точки с другими решениями Майкрософт
description: Узнайте, как Microsoft Defender для конечной точки интегрируется с другими решениями Майкрософт, включая Microsoft Defender для удостоверений и Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: защитник Microsoft 365, условный доступ, office, Microsoft Defender для Endpoint, защитник Microsoft для удостоверений, защитник Microsoft для office, Защитник Azure, безопасность облачных приложений Майкрософт, лазурный досье
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935537"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Защитник Microsoft для конечной точки и другие решения Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Интеграция с другими решениями Майкрософт

Microsoft Defender для конечной точки напрямую интегрируется с различными решениями Майкрософт.

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender for Endpoint предоставляет комплексное решение для защиты серверов, включая возможности обнаружения конечных точек и реагирования (EDR) на Windows Servers.

### <a name="azure-sentinel"></a>Azure Sentinel
Соединитель Microsoft Defender для конечной точки позволяет передавать оповещения из Microsoft Defender для конечной точки в Azure Sentinel. Это позволит более комплексно анализировать события безопасности в организации и создавать книги для эффективного и немедленного реагирования.

### <a name="azure-information-protection"></a>Azure Information Protection
Недавно мы отключили интеграцию Azure Information Protection, так как наши возможности DLP конечных точек включают улучшенное решение обнаружения и защиты конфиденциальных данных, хранимых на конечных устройствах, что облегчает большую видимость и интеграцию решений. Об этом было объявлено в следующем [блоге](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555). Мы рекомендуем клиентам перейти к использованию DLP конечной точки.

### <a name="conditional-access"></a>Условный доступ
Динамический показатель риска устройств Microsoft Defender для конечной точки интегрирован в оценку условного доступа, обеспечивая доступ к ресурсам только защищенным устройствам. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security использует сигналы Microsoft Defender для конечных точек, чтобы обеспечить прямую видимость использования облачных приложений, включая использование неподтвердимых облачных служб (теневых ИТ) со всех устройств, отслеживаемых Microsoft Defender для конечных точек.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender для удостоверений
Подозрительные действия — это процессы, запущенные в контексте пользователя. Интеграция между Microsoft Defender для конечной точки и Microsoft Defender for Identity обеспечивает гибкость в проведении расследований кибербезопасности в различных действиях и удостоверениях.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender для Office
[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) помогает защитить организацию от вредоносных программ в сообщениях электронной почты или файлах с помощью безопасных ссылок, безопасных вложений, расширенных возможностей для защиты от фишинга и подмены сведений. Интеграция между Microsoft Defender для Office 365 и Microsoft Defender для конечной точки позволяет аналитикам безопасности идти вверх по течению для изучения точки входа атаки. С помощью обмена сведениями об угрозах атаки могут быть задержаны и заблокированы. 

>[!NOTE]
> Данные Defender for Office 365 отображаются для событий в течение последних 30 дней. Для оповещений данные Defender for Office 365 отображаются в зависимости от времени первого действия. После этого данные больше не доступны в Defender для Office 365.

### <a name="skype-for-business"></a>Skype для бизнеса
Интеграция Skype для бизнеса позволяет аналитикам общаться с потенциально скомпрометированным пользователем или владельцем устройств с помощью простой кнопки с портала.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
С помощью Microsoft 365 Defender, Microsoft Defender для конечной точки и различных решений безопасности Майкрософт образуют единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечные точки, удостоверения, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки. 
 
[Дополнительные информацию о Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>Похожие темы
- [Настройка интеграции и других расширенных функций](advanced-features.md)
- [Обзор Защитника Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [Включение Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [Защита пользователей, данных и устройств с помощью условного доступа](conditional-access.md)
