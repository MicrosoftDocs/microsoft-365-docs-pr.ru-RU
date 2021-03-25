---
title: Интеграция Microsoft Defender для конечной точки с другими решениями Майкрософт
description: Узнайте, как Microsoft Defender для конечной точки интегрируется с другими решениями Майкрософт, включая Центр безопасности Microsoft Defender для удостоверений и Azure.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: защитник Microsoft 365, условный доступ, office, расширенные средства защиты от угроз, защитник Microsoft для удостоверений, защитник Microsoft для office, центр безопасности azure, безопасность облачных приложений Майкрософт, лазурный sentinel
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
ms.openlocfilehash: 287ad9adeccd527b756bdd5304d3c89fc1b2d789
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076493"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Защитник Microsoft для конечной точки и другие решения Майкрософт

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Интеграция с другими решениями Майкрософт

Microsoft Defender для конечной точки напрямую интегрируется с различными решениями Майкрософт.

### <a name="azure-security-center"></a>Центр безопасности Azure
Microsoft Defender for Endpoint предоставляет комплексное решение для защиты серверов, включая возможности обнаружения конечных точек и реагирования (EDR) на Windows Servers.

### <a name="azure-sentinel"></a>Azure Sentinel
Соединитель Microsoft Defender для конечной точки позволяет передавать оповещения из Microsoft Defender для конечной точки в Azure Sentinel. Это позволит более комплексно анализировать события безопасности в организации и создавать книги для эффективного и немедленного реагирования.

### <a name="azure-information-protection"></a>Azure Information Protection
Обеспечение безопасности конфиденциальных данных при одновременном повышении производительности на рабочем месте с помощью обнаружения данных и защиты данных.

### <a name="conditional-access"></a>Условный доступ
Динамический показатель риска устройств Microsoft Defender для конечной точки интегрирован в оценку условного доступа, обеспечивая доступ к ресурсам только защищенным устройствам. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security использует сигналы Microsoft Defender для конечных точек, чтобы обеспечить прямую видимость использования облачных приложений, включая использование неподтвердимых облачных служб (теневых ИТ) со всех устройств, отслеживаемых Microsoft Defender для конечных точек.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender для удостоверений
Подозрительные действия — это процессы, запущенные в контексте пользователя. Интеграция между Microsoft Defender для конечной точки и Azure ATP обеспечивает гибкость проведения расследования кибербезопасности в различных действиях и удостоверениях.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender для Office
[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) помогает защитить организацию от вредоносных программ в сообщениях электронной почты или файлах с помощью безопасных ссылок ATP, безопасных вложений ATP, расширенных возможностей для защиты от фишинга и подмены данных. Интеграция между ATP Office 365 и Microsoft Defender для endpoint позволяет аналитикам безопасности перейти вверх по течению для изучения точки входа атаки. С помощью обмена сведениями об угрозах атаки могут быть задержаны и заблокированы. 

>[!NOTE]
> Данные Defender for Office 365 отображаются для событий в течение последних 30 дней. Для оповещений данные Defender for Office 365 отображаются в зависимости от времени первого действия. После этого данные больше не доступны в Defender для Office 365.

### <a name="skype-for-business"></a>Skype для бизнеса
Интеграция Skype для бизнеса позволяет аналитикам общаться с потенциально скомпрометированным пользователем или владельцем устройств с помощью простой кнопки с портала.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
С помощью Microsoft 365 Defender, Microsoft Defender для конечной точки и различных решений безопасности Майкрософт образуют единый пакет корпоративной защиты до и после нарушения, который интегрируется в конечные точки, удостоверения, электронную почту и приложения для обнаружения, предотвращения, расследования и автоматического реагирования на сложные атаки. 
 
[Дополнительные информацию о Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>Статьи по теме
- [Настройка интеграции и других расширенных функций](advanced-features.md)
- [Обзор Защитника Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [Включив защитник Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [Защита пользователей, данных и устройств с помощью условного доступа](conditional-access.md)
