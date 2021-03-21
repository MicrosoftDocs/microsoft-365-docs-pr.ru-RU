---
title: Включи microsoft 365 Defender в центре безопасности Microsoft 365
description: Узнайте, как включить Microsoft 365 Defender и приступить к интеграции инцидентов и ответных действий в области безопасности.
keywords: начать работу, включить MTP, Microsoft Threat Protection, M365, безопасность, расположение данных, необходимые разрешения, право на лицензию, страницу параметров
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e7910866c494cf599022c17c29e3577e55cdba51
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928656"
---
# <a name="turn-on-microsoft-365-defender"></a>Включив защитник Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) объединяет процесс реагирования на инциденты, интегрируя ключевые возможности в Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity. В этом едином интерфейсе добавлены мощные функции, к которым можно получить доступ в Центре безопасности Майкрософт 365.

Microsoft 365 Defender автоматически включается при посещении центра безопасности Microsoft 365 подходящими клиентами с нужными разрешениями. Ознакомьтесь с этой статьей, чтобы разобраться в различных необходимых предпосылках и о том, как подготовка Защитника Microsoft 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Проверка прав на лицензию и необходимых разрешений

Лицензия на продукт безопасности Microsoft 365 обычно дает вам право использовать Microsoft 365 Defender в центре безопасности Microsoft 365 без дополнительных затрат на лицензирование. Мы рекомендуем получить лицензию Microsoft 365 E5, E5 Security, A5 или A5 Security или допустимое сочетание лицензий, которые предоставляют доступ ко всем поддерживаемым службам.

Подробные сведения о лицензировании [читайте в публикации "Ъ" "Требования к лицензированию".](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Проверка роли

Вы должны быть глобальным **администратором** или **администратором** безопасности в Azure Active Directory, чтобы включить Microsoft 365 Defender. [Просмотр ролей в Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Поддерживаемые службы

Microsoft 365 Defender собирает данные из различных поддерживаемых служб, которые вы уже развернули. Централизованная обработка и хранение данных будут определять новые сведения и делать возможными процессы централизованного реагирования. Это делается без влияния на существующие развертывания, параметры или данные, связанные с интегрированными службами.

Чтобы получить лучшую защиту и оптимизировать Microsoft 365 Defender, рекомендуется развернуть все применимые поддерживаемые службы в сети. Дополнительные сведения читайте [в публикации "Ъ" "Развертывание поддерживаемых служб".](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>На борту службы
Простота в Microsoft 365 Defender. В меню навигации выберите любой элемент в разделе Конечные точки, например Инциденты, Охота, Центр действий или аналитика угроз, чтобы инициировать процесс взбора. 

### <a name="data-center-location"></a>Расположение центра обработки данных

Microsoft 365 Defender будет хранить и обрабатывать данные в том же расположении, что и [Microsoft Defender для конечной точки.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Если у вас нет Microsoft Defender для конечной точки, новое расположение центра обработки данных автоматически выбирается в зависимости от расположения активных служб безопасности Microsoft 365. Выбранное расположение центра обработки данных отображается на экране.

Выберите **Необходимую помощь?** в центре безопасности Microsoft 365 связаться с службой поддержки Майкрософт по поводу обеспечения Microsoft 365 Defender в другом расположении центра обработки данных.

> [!NOTE]
> Microsoft Defender для конечной точки автоматически содержит положения в центрах обработки данных Европейского союза (ЕС) при включении через Azure Defender. Microsoft 365 Defender автоматически будет в том же центре обработки данных ЕС для клиентов, которые таким образом закапировали Defender для конечной точки.

### <a name="confirm-that-the-service-is-on"></a>Подтверждение включения службы

После подготовки службы в нее добавляются:

- [Управление инцидентами](incidents-overview.md)
- [Очередь оповещений](investigate-alerts.md)
- Центр уведомлений для управления службой [Автоматического анализа угроз и защиты от атак](mtp-autoir.md)
- [Расширенные возможности](advanced-hunting-overview.md) охоты
- Аналитика угроз

![Изображение области навигации центра безопасности Microsoft 365 с Microsoft 365 Defender имеет центр безопасности Microsoft 365 с управлением инцидентами и другими возможностями ](../../media/mtp-enable/mtp-on.png)
 *Защитника Microsoft 365*

### <a name="getting-microsoft-defender-for-identity-data"></a>Получение данных Microsoft Defender для удостоверений 
Чтобы включить интеграцию с microsoft Cloud App Security, необходимо хотя бы один раз войти в службу безопасности облачных приложений Майкрософт.

## <a name="get-assistance"></a>Получение помощи

Чтобы получить ответы на наиболее часто задаваемые вопросы о включив Microsoft 365 Defender, ознакомьтесь с часто задаваемой [проблемой.](mtp-enable-faq.md)

Сотрудники службы поддержки Майкрософт могут помочь в предоставлении или откормке службы и связанных с ней ресурсов на клиенте. Для оказания помощи выберите **Need Help?** в центре безопасности Microsoft 365. При контакте с поддержкой упоминают Microsoft 365 Defender.

## <a name="related-topics"></a>Родственные темы

- [Вопросы и ответы](mtp-enable-faq.md)
- [Требования к лицензированию и другие предварительные требования](prerequisites.md)
- [Развертывание поддерживаемых служб](deploy-supported-services.md)
- [Обзор Защитника Microsoft 365](microsoft-threat-protection.md)
- [Обзор Microsoft Defender для конечной точки](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Обзор Defender для Office 365](../office-365-security/office-365-atp.md)
- [Обзор Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Обзор Microsoft Defender для удостоверений](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender для хранения данных конечной точки](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)