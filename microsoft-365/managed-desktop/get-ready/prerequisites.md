---
title: Предварительные условия для компьютеров, управляемых Майкрософт
description: Лицензии, учетные записи Azure, параметры проверки подлинности и параметры Microsoft 365, которые необходимо настроить перед регистрацией в Microsoft Managed Desktop
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c298c0d07b73966fe3946f0e3f2706da5d2d30fc
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453901"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Предварительные условия для компьютеров, управляемых Майкрософт

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

В этом разделе описаны требования к инфраструктуре, которые необходимо выполнить для обеспечения успеха в Microsoft Managed Desktop. 


Область | Необходимые сведения
--- | ---
Лицензирование |Microsoft Managed Desktop требует лицензию Microsoft 365 E3 с Microsoft Defender для конечной точки (или эквивалентов), назначенную пользователям. В клиенте должны быть доступны две лицензии для Azure Active Directory Premium 2, но эта лицензия не нужна пользователям. <br>Дополнительные сведения о конкретных планах служб см. в разделе [Дополнительные сведения о лицензиях](#more-about-licenses) в этом разделе.<br>Дополнительные сведения о доступных лицензиях см. в [сайте Microsoft 365 licensing.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
Подключение |  Все управляемые настольные устройства Майкрософт требуют подключения к многочисленным конечным точкам службы Майкрософт из корпоративной сети.<br><br>Полный список требуемого IPs и URL-адресов см. в [сетевой конфигурации.](../get-ready/network.md) 
Azure Active Directory |    Azure Active Directory (Azure AD) должен быть либо источником полномочий для всех учетных записей пользователей, либо учетные записи пользователей должны синхронизироваться из локального Active Directory с помощью последней поддерживаемой версии Azure AD Connect.<br><br>[Для пользователей управляемых](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) настольных компьютеров Microsoft должен быть включен корпоративный роуминг.<br><br>Дополнительные сведения см. в [видеоролике Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Дополнительные сведения о поддерживаемых версиях Azure AD Connect см. в истории выпуска [Azure AD Connect:Version.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)
Проверка подлинности |    Если Azure AD не является источником первичной проверки подлинности для учетных записей пользователей, необходимо настроить одну из них в Azure AD Connect:<br>- Синхронизация хаширования паролей<br>- Сквозная проверка подлинности<br>- внешний поставщик удостоверений (в том числе Windows Server ADFS и идентификаторы, не включаемые в Microsoft), настроенный для удовлетворения требований к интеграции Azure AD. Дополнительные [сведения см. в](https://www.microsoft.com/download/details.aspx?id=56843) руководстве. <br><br>При настройке параметров проверки подлинности с помощью Azure AD Connect рекомендуется также написать пароль. Дополнительные сведения см. в [статью Возвращение пароля.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Если реализован внешний поставщик удостоверений, необходимо проверить решение:<br>- соответствует требованиям интеграции Azure AD<br>- Поддерживает условный доступ Azure AD, что позволяет настраивать политику соответствия требованиям к управляемым настольным устройствам Майкрософт<br>- Включает регистрацию устройств и использование служб и функций Microsoft 365, необходимых в рамках Microsoft Managed Desktop <br><br>Дополнительные сведения о параметрах проверки подлинности в Azure AD см. в меню Параметры входов пользователя [Azure AD Connect.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive для бизнеса должен быть включен для пользователей управляемых настольных компьютеров Майкрософт.<br><br>Несмотря на то, что для регистрации в Microsoft Managed Desktop не требуется регистрация, мы настоятельно рекомендуем перенести в облако следующие службы:<br>- Электронная почта: перенос в облачные почтовые ящики, Exchange online или настройка с Помощью гибридной системы Exchange Online с exchange 2013 или более высокой локальной платформы.<br>- Файлы и папки: миграция в OneDrive для бизнеса или SharePoint Online.<br>- Средства совместной работы в Интернете: миграция в Teams.
Управление устройствами | Устройства microsoft Managed Desktop требуют управления с помощью Microsoft Intune. Intune должен быть назначен в качестве органа управления мобильными устройствами.<br><br>Дополнительные сведения см. [в сайте Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
Резервное копирование и восстановление данных |  Microsoft Managed Desktop требует синхронизации файлов с OneDrive для бизнеса для защиты. Все файлы, не синхронизированные с OneDrive для бизнеса, не гарантируются Microsoft Managed Desktop и могут быть потеряны во время обмена устройствами или вызовов поддержки, требующих сброса устройства.<br><br>Несмотря на то, что это не требуется, Microsoft Managed Desktop настоятельно рекомендует перенос с сетевых дисков на соответствующие облачные решения. Дополнительные сведения см. в [сайте Prepare mapped drives for Microsoft Managed Desktop.](mapped-drives.md)

Когда вы будете готовы начать работу с microsoft Managed Desktop, обратитесь к вашему менеджеру учетных записей Майкрософт. 

## <a name="more-about-licenses"></a>Подробнее о лицензиях

Для работы в Microsoft Managed Desktop необходимы определенные параметры лицензии. Сведения о том, как используются эти лицензии, см. в веб-сайте [Microsoft Managed Desktop](../intro/technologies.md) technologies.

> [!TIP]
> Чтобы назначить эти параметры лицензии определенным пользователям, [](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) рекомендуется воспользоваться функцией лицензирования Azure Active Directory на основе группы.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Корпоративная  
- Microsoft Defender для конечной точки
- Приложения Microsoft 365 для предприятий
- Microsoft Teams
- [SharePoint Online (план 2)](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online (план 2)](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Менеджер учетной записи Майкрософт поможет вам просмотреть текущие лицензии и планы обслуживания и найти наиболее эффективный способ получения дополнительных лицензий или планов служб, которые могут потребоваться, избегая дублирования.
