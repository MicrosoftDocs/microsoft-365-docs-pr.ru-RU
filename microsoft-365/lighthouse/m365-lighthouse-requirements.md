---
title: Требования к Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Для поставщиков управляемых служб (MSP) получите список требований к использованию Microsoft 365 Lighthouse.
ms.openlocfilehash: 9c87744053ffe3bace90534287cd2b81697f3554
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395353"
---
# <a name="requirements-for-microsoft-365-lighthouse"></a>Требования к Microsoft 365 Lighthouse

> [!NOTE]
> Функции, описанные в этой статье, подлежат изменениям и доступны только партнерам, которые соответствуют требованиям, указанным в этой статье. Если в организации нет Microsoft 365 Lighthouse, [см.](m365-lighthouse-sign-up.md)в Microsoft 365 Lighthouse.

Microsoft 365 Lighthouse является порталом администрирования, который помогает управляемым поставщикам услуг (MSP) обеспечивать безопасность устройств, данных и пользователей в масштабе для клиентов малого и среднего бизнеса (SMB).  

MsPs должны быть зарегистрированы в программе поставщик облачных решений (CSP) в качестве непрямого посредника или партнера Direct Bill для использования Microsoft 365 Lighthouse.  

Кроме того, каждый клиент MSP должен иметь право на Microsoft 365 Lighthouse, выполнев следующие требования: 
 
- Делегированная привилегия администратора (DAP) для MSP 
- По крайней мере одна Microsoft 365 бизнес премиум лицензия 
- Менее 500 лицензированных пользователей  

## <a name="requirements-for-enablingdevice-management"></a>Требования для включения управления устройствами   

Чтобы просмотреть устройства клиента-клиента на страницах управления устройствами, MSP должен:    

- Регистрация всех устройств клиентов в Microsoft Endpoint Manager (MEM).Дополнительные сведения см. в [Microsoft Intune.](/mem/intune/enrollment/)
- Назначение политик соответствия требованиям для всех устройств клиента.Дополнительные сведения см. в [дополнительных сведениях о создании](/mem/intune/protect/create-compliance-policy)политики соответствия требованиям в Microsoft Intune. 

## <a name="requirements-for-enabling-usermanagement"></a>Требования для включения управления пользователями 

Чтобы данные клиентов были в отчетах на страницах управления пользователями, включая рискованных пользователей, многофакторную проверку подлинности и сброс пароля, клиенты должны иметь лицензии на Azure Active Directory Premium P1 или более поздней основе. Azure AD Premium P1 включен в Microsoft 365 бизнес премиум.   

## <a name="requirements-for-enablingthreat-management"></a>Требования для включения управления угрозами 

Чтобы просмотреть устройства клиента и угрозы на страницах управления угрозами, необходимо записать все устройства клиента в Microsoft Endpoint Manager (MEM) и защитить их, запуская антивирусная программа в Microsoft Defender.  

Дополнительные сведения см. в [Microsoft Intune.](/mem/intune/enrollment/)  

антивирусная программа в Microsoft Defender является частью Windows операционной системы и включена по умолчанию на устройствах с Windows 10.  

> [!NOTE] 
> Если вы используете антивирусное решение, не в microsoft, а не антивирусная программа в Microsoft Defender, антивирусная программа в Microsoft Defender автоматически отключается. При отсечении антивирусного решения, антивирусная программа в Microsoft Defender автоматически активируется для защиты Windows устройств от угроз.    

## <a name="related-content"></a>См. также:   

[Настройка Microsoft 365 Lighthouse безопасности портала](m365-lighthouse-configure-portal-security.md) (статья)\
[Microsoft 365 Lighthouse страницы соответствия требованиям устройства](m365-lighthouse-device-compliance-page-overview.md) (статья)\
[Microsoft 365 Lighthouse страницы пользователей](m365-lighthouse-users-page-overview.md) (статья)\
[Microsoft 365 Lighthouse страницы управления угрозами](m365-lighthouse-threat-management-page-overview.md) (статья)\
[Microsoft 365 Lighthouse faQ](m365-lighthouse-faq.yml)   (статья)

