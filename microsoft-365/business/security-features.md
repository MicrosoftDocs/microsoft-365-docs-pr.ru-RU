---
title: Функции обеспечения безопасности и соответствия требованиям Microsoft 365 Business Premium
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
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Узнайте о функциях обеспечения безопасности, которые поставляются с Microsoft 365 Business Premium, чтобы обеспечить защиту данных на компьютерах, телефонах и планшетах.
ms.openlocfilehash: 35eb0ac1dce216ccc557fc629ddb5d2df50e7134
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635151"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Функции обеспечения безопасности и соответствия требованиям Microsoft 365 Business Premium

Microsoft 365 Business Premium предоставляет упрощенные функции безопасности для защиты данных на компьютерах, телефонах и планшетах.
    
## <a name="microsoft-365-admin-center-security-features"></a>Функции безопасности центра администрирования Microsoft 365

[![Надпись, оповещающая об изменении Центра администрирования. Дополнительные сведения см. на сайте aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Вы можете управлять многими функциями безопасности Microsoft 365 Business Premium в центре администрирования, что позволяет включать и отключать эти функции в упрощенном виде. В центре администрирования можно выполнить следующие действия:
  
- [Настройка параметров управления приложениями для устройств с Android или iOS](app-protection-settings-for-android-and-ios.md) . 
    
    Эти параметры включают удаление файлов с неактивного устройства после заданной точки, шифрование рабочих файлов, требование установки ПИН-кода и т. д.
    
- [Настройка параметров защиты приложений для устройств с Windows 10](protection-settings-for-windows-10-devices.md) . 
    
    Эти параметры можно применять к данным компании на устройствах, принадлежащих компании, или на устройствах с личными владельцами.
    
- [Настройка параметров защиты устройств для устройств с Windows 10](protection-settings-for-windows-10-pcs.md) . 
    
    Шифрование [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) можно включить для защиты данных в случае потери или кражи устройства, а также для обеспечения дополнительной защиты от программы-шантажистом с помощью [Windows эксплойтов](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) . 
    
- [Удаление данных организации с устройств](remove-company-data.md)
    
    Вы можете удаленно стереть данные компании, если устройство утрачено, украдено или сотрудник покидает вашу компанию.
    
- [Выполните сброс устройств с Windows 10 в соответствии с их фабричными настройками](reset-devices-to-factory-settings.md) . 
    
    Можно сбросить все устройства с Windows 10, к которым применены параметры защиты устройств.
    
## <a name="additional-security-features"></a>Дополнительные функции безопасности 

Расширенные функции в Microsoft 365 Business Premium помогут вам защитить бизнес от угроз кибератак-угроз и защищать конфиденциальные данные.
  
- **[Office 365 Advanced Threat Protection](https://support.office.com/article/e100fe7c-f2a1-4b7d-9e08-622330b83653)**
    
    Advanced Threat protection (ATP) помогает защитить бизнес от атак с помощью изощренных фишинговых и мошеннических атак, которые предназначены для взлома сведений о сотрудниках и клиентах. Поддерживаются перечисленные ниже возможности. 
    
  - Сложное сканирование вложений и анализ с питанием на основе AI для обнаружения и удаления опасных сообщений.
    
  - Автоматическая проверка ссылок в электронной почте для оценки того, являются ли они частью схемы фишинга. Это позволяет безопасно получать доступ к небезопасным веб-сайтам.

- **[Все возможности Intune на портале Azure](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Доступ к центру администрирования Intune на портале Azure позволяет настраивать дополнительные функции безопасности, такие как управление устройствами MacOS, iPhone и Android, а также расширенное управление устройствами для Windows, которые недоступны в центре администрирования Microsoft 365.
- **Такой же [Условный доступ](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) , как и в плане Azure AD Premium P1**


    Условный доступ помогает защитить организацию от риска входа в систему, попыток доступа к неожиданному сетевому или языковому стандарту, попыток доступа к типам нерискованных устройств и т. д. Политики условного доступа принудительно применяются после завершения первой проверки подлинности и используют сигналы из первого события проверки подлинности, чтобы определить, следует ли утвердить попытки доступа, отклонить или если требуется дополнительная проверка (например, вторая форма идентификации).

    К включенным функциям условного доступа относятся:

    - Доступ на основе имени пользователя, группы и роли
    - Доступ на [основе приложения](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Доступ на основе расположения](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  разрешить доступ только из надежных диапазонов IP-адресов или определенных стран 
    - Требовать MFA для Access
    - Блокировка доступа к приложениям, использующим [устаревшую проверку подлинности](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication)
    - Требовать приложения TP использовать [защиту приложений Intune](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Настраиваемая проверка подлинности, например MFA, с сторонними поставщиками (например, DUO).
   
    Другие возможности:
    - [Самостоятельный сброс паролей](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) для гибридной службы Azure AD
    
## <a name="compliance-features"></a>Функции обеспечения соответствия требованиям

Подписка на Microsoft 365 Business Premium включает функции, помогающие обеспечить соответствие требованиям и нормативным стандартам.

- **[Обзор политик защиты от потери данных](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)** (DLP). 
    
    Вы можете настроить DLP для автоматического обнаружения конфиденциальных данных, таких как номера кредитных карт, номера социального страхования и т. д., чтобы предотвратить случайный общий доступ за прев компании.
    
- **[Архивация на базе Exchange Online](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Лицензия на архивацию на базе Exchange Online позволяет легко архивировать сообщения с помощью непрерывной резервной копии данных. В нем хранятся все сообщения пользователя, в том числе удаленные элементы, если они понадобятся позже для обнаружения или восстановления. Кроме того, вы можете использовать различные политики хранения для сохранения данных электронной почты для судебных удержаний, обнаружения электронных данных или для удовлетворения требований соответствия требованиям.
    
- **[Метки конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium включает все функции [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). С помощью этого плана можно создавать **метки конфиденциальности** , которые позволяют управлять доступом к конфиденциальным сведениям в сообщениях электронной почты и документов, с элементами управления, такими как "не пересылать" и "не копировать". Вы также можете классифицировать конфиденциальную информацию как "конфиденциально" и указать, как секретную информацию можно совместно использовать снаружи и внутри Организации. Шифрование уровня предприятия легко применить к электронной почте и документам, чтобы обеспечить их конфиденциальность. Вы также можете установить клиентскую надстройку Azure Information Protection для приложений Office. Для получения дополнительных сведений обратитесь к [клиенту единой метки Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Для меток конфиденциальности установите **AzInfoProtection_UL. exe**.

Вы можете управлять этими функциями в центре безопасности &amp; и управления Intune. Со временем в центр администрирования Microsoft 365 будут добавлены упрощенные элементы управления.
  
    
## <a name="faq"></a>Вопросы и ответы

 ### <a name="are-these-security-features-available-in-all-markets"></a>Доступны эти функции безопасности на всех рынках?
  
Да, эти функции доступны на всех рынках, где реализовано Microsoft 365 бизнес премиум.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Как найти центр соответствия требованиям безопасности &amp; ?
  
1. [Войдите в Microsoft 365 Business Premium](https://portal.microsoft.com/) , используя учетные данные администратора. 
    
2. В левой панели навигации выберите **центр администрирования** и разверните его. 
    
    ![В левой панели навигации центра администрирования Microsoft 365 выберите пункт центры администрирования.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Выберите **соответствие &amp; требованиям безопасности** , чтобы перейти &amp; в центр соответствия требованиям безопасности.
