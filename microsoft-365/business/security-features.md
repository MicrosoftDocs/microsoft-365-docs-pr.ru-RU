---
title: Функции безопасности и соответствия требованиям Microsoft 365 бизнес премиум
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Узнайте о функции безопасности в Microsoft 365 бизнес премиум для защиты данных на ПК, телефонах и планшетах.
ms.openlocfilehash: b7fdd3d7fa25c23ee49ae82aa037588d8fba61a1
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840396"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Функции безопасности и соответствия требованиям Microsoft 365 бизнес премиум

Microsoft 365 бизнес премиум предлагает упрощенные функции безопасности для защиты данных на ПК, телефонах и планшетах.
    
## <a name="microsoft-365-admin-center-security-features"></a>Функции безопасности Центра администрирования Microsoft 365

Вы можете управлять многими функциями безопасности Microsoft 365 бизнес премиум в Центре администрирования, что упрощает их включив или отключив. В Центре администрирования можно сделать следующее:
  
- [Настройка параметров управления приложениями для устройств с Android или iOS.](app-protection-settings-for-android-and-ios.md) 
    
    Эти параметры включают удаление файлов с неактивного устройства после определенного периода, шифрование work-файлов, требование, чтобы пользователи установили ПИН-код и так далее.
    
- [Настройка параметров защиты приложений для устройств с Windows 10.](protection-settings-for-windows-10-devices.md) 
    
    Эти параметры можно применять к данным компании как на собственных, так и на личных устройствах.
    
- [Настройка параметров защиты устройств с Windows 10.](protection-settings-for-windows-10-pcs.md) 
    
    Вы можете включить шифрование [BitLocker,](https://go.microsoft.com/fwlink/p/?linkid=871405) чтобы защитить данные в случае потери или кражи устройства, а также включить [Exploit Guard в Windows](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) для обеспечения более активной защиты от программ-вымогателей. 
    
- [Удаление данных организации с устройств](remove-company-data.md)
    
    Вы можете удаленно стереть данные компании, если устройство потеряно, украдено или сотрудник уедет из компании.
    
- [Сброс устройства с Windows 10 до заводских настроек.](reset-devices-to-factory-settings.md) 
    
    Вы можете сбросить все устройства с Windows 10, к ним применены параметры защиты устройств.
    
## <a name="additional-security-features"></a>Дополнительные функции безопасности 

Дополнительные функции в составе Microsoft 365 бизнес премиум помогут защитить ваш бизнес от киберугроз и поддержать безопасность конфиденциальной информации.
  
- **[Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Microsoft Defender для Office 365 помогает защитить ваш бизнес от сложных фишинговых атак и атак вымогателей, предназначенных для компрометации информации о сотрудниках или клиентах. Поддерживаются перечисленные ниже возможности. 
    
  - Сложный анализ вложений и анализ на основе ИИ для обнаружения и отклонения опасных сообщений.
    
  - Автоматическая проверка ссылок в электронной почте для оценки того, являются ли они частью схемы фишинга. Это обеспечивает безопасность доступа к небезопасным веб-сайтам.

- **[Все возможности Intune на портале Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Доступ к Центру администрирования Intune на портале Azure позволяет настроить дополнительные функции безопасности, такие как управление устройствами MacOS, iPhone и Android, а также расширенные возможности управления устройствами для Windows, которые недоступны в Центре администрирования Microsoft 365.
- **Тот [же условный доступ, что](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) и для плана Azure AD Premium P1**


    Условный доступ помогает защитить организацию от риска для входов, попыток доступа из неожиданной сети или локали, попыток доступа от рискованных типов устройств и так далее. Политики условного доступа применяются после завершения первой проверки подлинности и используют сигналы первого события проверки подлинности, чтобы определить, следует ли утвердить, отказано в доступе или требуется ли дополнительное подтверждение (например, вторая форма идентификации).

    Включены следующие функции условного доступа:

    - Доступ на основе имени пользователя, группы и роли
    - Доступ [на основе приложения](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Доступ в зависимости от расположения;](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration)  разрешить доступ только из надежных диапазонов IP-адресов или определенных стран. 
    - Требовать MFA для доступа
    - Блокировка доступа к приложениям, которые используют [устаревшую проверку подлинности](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Требовать от приложений использования [защиты приложений Intune](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Настраиваемая проверка подлинности, например MFA со сторонними поставщиками, например, с помощью ОПЕРАТОРА.
   
    Другие возможности:
    - [Самостоятельный сброс паролей](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) для гибридной службы Azure AD
    
## <a name="compliance-features"></a>Функции обеспечения соответствия требованиям

Ваша подписка на Microsoft 365 бизнес премиум включает функции, которые помогают поддерживать соответствие требованиям и нормативные стандарты.

- **[Обзор политик защиты от потери данных](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** (DLP). 
    
    Вы можете настроить DLP, чтобы автоматически обнаруживать конфиденциальную информацию, например номера кредитных карт, номера социального страхования и так далее, чтобы предотвратить их непреднамеренное совместное использование за пределами вашей компании.
    
- **[Архивация на базе Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    архивация на базе Exchange Online позволяет легко архивировать сообщения с помощью непрерывного резервного копирования данных. В нем хранится все сообщения электронной почты пользователя, включая удаленные элементы, на случай, если они потребуется позже для обнаружения или восстановления. Кроме того, вы можете использовать различные политики хранения для сохранения данных электронной почты для хранения для судебного разбирательства, eDiscovery или для соответствия требованиям.
    
- **[Метки конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 бизнес премиум включает все функции [Azure Information Protection (план 1).](https://go.microsoft.com/fwlink/p/?linkid=871407) С помощью этого плана  вы можете создавать метки конфиденциальности, которые позволяют контролировать доступ к конфиденциальной информации в электронной почте и документах, с помощью таких элементов управления, как "Не переад вперед" и "Не копировать". Вы также можете классифицировать конфиденциальную информацию как "конфиденциальную" и указать, как можно делиться конфиденциальной информацией за пределами и внутри компании. Шифрование корпоративного уровня легко применять к электронной почте и документам, чтобы ваши сведения были закрытыми. Вы также можете установить клиентскую надстройку Azure Information Protection для приложений Office. Дополнительные сведения см. в клиенте [унифицированных меток Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history) Для меток конфиденциальности установите **AzInfoProtection_UL.exe.**

Вы можете управлять этими функциями в Центре соответствия требованиям безопасности и Центре администрирования &amp; Intune. Со временем упрощенные элементы управления будут добавлены в Центр администрирования Microsoft 365.
  
    
## <a name="faq"></a>Вопросы и ответы

 ### <a name="are-these-security-features-available-in-all-markets"></a>Доступны ли эти функции безопасности на всех рынках?
  
Да, эти функции доступны на всех рынках, где продается Microsoft 365 бизнес премиум.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Как найти Центр соответствия &amp; требованиям безопасности?
  
1. [Во sign in to Microsoft 365 Business Premium](https://portal.microsoft.com/) by using your admin credentials. 
    
2. В левой области nav найдите **центры администрирования** и разойдите их. 
    
    ![In the left nav in the Microsoft 365 admin center, choose Admin centers.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Выберите **&amp; "Соответствие требованиям безопасности",** чтобы перейти в Центр &amp; соответствия требованиям безопасности.
