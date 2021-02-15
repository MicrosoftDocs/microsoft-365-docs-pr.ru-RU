---
title: Предварительные условия для компьютеров, управляемых Майкрософт
description: Лицензии, учетные записи Azure, параметры проверки подлинности и параметры Microsoft 365, которые необходимо настроить перед регистрацией в microsoft Managed Desktop
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659144"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Предварительные условия для компьютеров, управляемых Майкрософт

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

В этом разделе описаны требования к инфраструктуре, которые необходимо выполнить, чтобы обеспечить успешное управление компьютерами, управляемыми Майкрософт. 


Область | Сведения о предварительных условиях
--- | ---
Лицензирование |Для компьютеров, управляемых Майкрософт, требуется лицензия Microsoft 365 E3 с Microsoft Defender для конечной точки и Azure Active Directory Premium 2 (или эквиваленты).<br>Дополнительные сведения о конкретных планах обслуживания см. в разделе ["Дополнительные сведения о лицензиях"](#more-about-licenses) в этом разделе.<br>Дополнительные сведения о доступных лицензиях см. в сведениях о [лицензировании Microsoft 365.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
Подключение |  Все настольные компьютеры, управляемые Майкрософт, требуют подключения к многочисленным конечным точкам служб Майкрософт из корпоративной сети.<br><br>Полный список необходимых IPS и URL-адресов см. в [конфигурации сети.](../get-ready/network.md) 
Azure Active Directory |    Azure Active Directory (Azure AD) должен быть либо источником полномочий для всех учетных записей пользователей, либо учетные записи пользователей должны синхронизироваться из локальной службы Active Directory с помощью последней поддерживаемой версии Azure AD Connect.<br><br>[Для пользователей компьютеров,](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) управляемых Майкрософт, должен быть включен роуминг состояния предприятия.<br><br>Дополнительные сведения см. в [azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Дополнительные сведения о поддерживаемых версиях Azure AD Connect см. в истории выпусков [Azure AD Connect:Version.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)
Проверка подлинности |    Если Azure AD не является источником основной проверки подлинности для учетных записей пользователей, необходимо настроить один из них в Azure AD Connect:<br>- Синхронизация паролей с помощью hash<br>- Сквозная проверка подлинности<br>- Внешний поставщик удостоверений (в том числе ADFS Windows Server и сторонние IDP), настроенный для удовлетворения требований к интеграции Azure AD. Дополнительные [сведения см.](https://www.microsoft.com/download/details.aspx?id=56843) в рекомендациях. <br><br>При настройке параметров проверки подлинности с помощью Azure AD Connect также рекомендуется использовать функцию записи паролей. Дополнительные сведения см. в [записи пароля.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Если внедрен внешний поставщик удостоверений, необходимо проверить решение:<br>- Соответствует требованиям интеграции Azure AD<br>- Поддерживает условный доступ Azure AD, который позволяет настроить политику соответствия требованиям для управляемых настольных компьютеров Майкрософт<br>- Включает регистрацию устройств и использование служб или функций Microsoft 365, необходимых в составе компьютеров, управляемых Майкрософт <br><br>Дополнительные сведения о параметрах проверки подлинности с помощью Azure AD см. в параметрах входов пользователей [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive для бизнеса должен быть включен для пользователей компьютеров, управляемых Майкрософт.<br><br>Хотя регистрация на компьютере, управляемом Майкрософт, не требуется, мы настоятельно рекомендуем перенести в облако следующие службы:<br>- Электронная почта: миграция в облачные почтовые ящики, Exchange Online или настройка гибридной конфигурации Exchange Online с Exchange 2013 или более высокой локальной системы.<br>- Файлы и папки: миграция в OneDrive для бизнеса или SharePoint Online.<br>- Средства совместной работы через Интернет: переход на Teams.
Управление устройствами | Настольные устройства, управляемые Майкрософт, требуют управления с помощью Microsoft Intune. Intune необходимо установить в качестве органа управления мобильными устройствами.<br><br>Дополнительные сведения см. [в microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Резервное копирование и восстановление данных |  Для защиты компьютеров, управляемых Майкрософт, требуется синхронизировать файлы с OneDrive для бизнеса. Любые файлы, не синхронизированные с OneDrive для бизнеса, не гарантируются компьютером, управляемым Майкрософт, и могут быть потеряны во время обмена устройствами или звонков в службу поддержки, требующих сброса устройства.<br><br>Хотя это и не обязательно, на компьютере, управляемом Майкрософт, настоятельно рекомендуется мить с сетевых дисков с соответствующим облачным решением. Дополнительные сведения см. в [подготовьте mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Когда вы будете готовы начать работу с компьютером, управляемым Майкрософт, обратитесь к менеджеру по работе с учетными данными Майкрософт. 

## <a name="more-about-licenses"></a>Дополнительные информация о лицензиях

Для работы компьютеров, управляемых Майкрософт, требуются определенные параметры лицензии. Сведения [об используемых лицензиях](../intro/technologies.md) см. в технологиях microsoft Managed Desktop.

> [!TIP]
> Чтобы назначить эти параметры лицензии определенным пользователям, [](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) рекомендуется воспользоваться функцией лицензирования Azure Active Directory на основе групп.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Корпоративная  
- Microsoft Defender для конечной точки
- Приложения Microsoft 365 для предприятий
- Microsoft Teams
- [SharePoint Online (план 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (план 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Ваш диспетчер учетных записей Майкрософт поможет вам просмотреть текущие лицензии и планы обслуживания и найти наиболее эффективный способ получения дополнительных лицензий или планов обслуживания, которые вам могут потребоваться, избегая дублирования.
