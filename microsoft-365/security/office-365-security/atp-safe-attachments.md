---
title: Безопасные вложения ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
- seo-marvel-apr2020
description: В этой статье рассказывается о функции безопасных вложений ATP для Office 365 и о том, как получить эту функцию для вашей подписки.
ms.openlocfilehash: 1ff7021f1c9fa64d3f04cbcac7231733399ad2b8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198779"
---
# <a name="atp-safe-attachments"></a>Безопасные вложения ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="overview-of-office-365-atp-safe-attachments"></a>Обзор безопасных вложений Office 365 ATP

Безопасные вложения ATP (наряду с [безопасными ссылками ATP](atp-safe-links.md)) входят в состав [Office 365 Advanced Threat protection](office-365-atp.md) (ATP). Функция безопасных вложений ATP проверяет, являются ли вложения электронной почты вредоносными, а затем принимает меры для защиты Организации. Функция безопасных вложений ATP защищает организацию в соответствии с [политиками безопасных вложений ATP](set-up-atp-safe-attachments-policies.md) , заданными глобальными администраторами или администраторами безопасности.

Защита ATP также может быть расширена до файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams. Чтобы узнать больше, ознакомьтесь с [разделом Office 365 Advanced Threat Protection for SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md).

## <a name="how-to-get-atp-safe-attachments"></a>Получение безопасных вложений ATP

Для начала убедитесь, что в подписке включена [Расширенная защита от угроз](office-365-atp.md). ATP включена в подписку, например, [microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 бизнес премиум](https://www.microsoft.com/microsoft-365/business), office 365, Office 365 A5 и т. д. Если у вашей организации есть подписка на Microsoft 365, не включающая в себя Office 365 ATP, вы можете приобрести ATP как надстройку. Дополнительные сведения см. в статье [office 365 Advanced Threat protection Plans and ценах](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Далее Убедитесь, что политики безопасных вложений ATP определены. (См. раздел [Настройка политик безопасных вложений Office 365 ATP](set-up-atp-safe-attachments-policies.md)) Функции безопасных вложений ATP активны в следующих случаях:

- Настроены политики безопасных вложений ATP. (См. раздел [Настройка политик безопасных вложений ATP в Office 365](set-up-atp-safe-attachments-policies.md)).

- Пользователи выполнили вход с помощью рабочей или учебной учетной записи. (См. раздел [Вход в Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)).

Для определения (или изменения) политик ATP необходимо назначить соответствующую роль. Некоторые примеры описаны в таблице ниже.

|Роль|Где/как назначено|
|---|---|
|Глобальный администратор|Сотрудник, который подписывается на приобретение Microsoft 365, по умолчанию является глобальным администратором. (Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора майкрософт 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
|Администратор безопасности|Центр администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Управление организациями в Exchange Online|Центр администрирования Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>или <br>  Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
|

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>Сведения о том, где находится защита от использования надежных вложений ATP

Определив [политики безопасных вложений ATP](set-up-atp-safe-attachments-policies.md), вы можете узнать, как работает служба, [просматривая отчеты для Advanced Threat protection](view-reports-for-atp.md).

В следующей таблице приведено несколько примеров сценариев. Во всех этих случаях предполагается, что у Организации есть подписка на Microsoft 365, включающая в себя улучшенную защиту от угроз.

****

|Пример сценария|Применяется ли защита надежных вложений ATP в этом случае?|
|---|---|
|Организация Pat имеет Office 365, но никто не определил ни одной политики для безопасных вложений в ATP.|Нет. Несмотря на то, что функция доступна, необходимо определить по крайней мере одну политику безопасных вложений ATP, чтобы обеспечить защиту от надежных вложений ATP.|
|Иванов — сотрудник отдела продаж в компании Contoso. В Организации Иванов есть политика безопасных вложений ATP на месте, которая применяется только к сотрудникам из финансового отдела.|Нет. В этом случае сотрудники Организации будут иметь защиту от использования надежных вложений ATP, но другие сотрудники, включая Отдел продаж, не будут определять политики, включающие эти группы.|
|Вчера Администратор в Организации Жан настроил политику безопасных вложений ATP, которая применяется ко всем сотрудникам. Ранее на сегодняшний день Жан получил сообщение электронной почты, содержащее вложение.|Да. В этом примере у Жан есть лицензия на Advanced Threat Protection, и политика безопасных вложений ATP, включающая Жан, определена. Для вступления в силу новой политики в центрах обработки данных обычно требуется около 30 минут. так как в этом случае был пройден день, политика должна быть применена.|
|Для всех пользователей организации в Организации Крис установлен Office 365, а также политики безопасных вложений ATP. Крис получает сообщение электронной почты, которое содержит вложение, и пересылает его другим пользователям, находящимся за пререшениями Организации.|Для сообщений, получаемых Крис, используется защита от надежных вложений ATP. Если в организациях получателей также есть политики безопасных вложений ATP, то при получении переадресованного сообщения будут направляться такие политики в соответствии с назначением.|
|В Организации ресурса имеются политики безопасных вложений ATP на месте, а [ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md) включено. В ресурсе предполагается, что все файлы в SharePoint Online были проверены и безопасно открыты и скачаны.|Защита надежных вложений ATP выполняется в соответствии с определенными политиками; Однако это не означает, что проверяются все отдельные файлы в SharePoint Online, OneDrive для бизнеса или Microsoft Teams. (Дополнительные сведения см. в разделе [ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md).)|
|

## <a name="submitting-files-for-malware-analysis"></a>Отправка файлов для анализа вредоносных программ

- Если вы получили файл, который необходимо проанализировать корпорацией Майкрософт, посетите страницу [отправить файл для анализа вредоносных программ](https://aka.ms/wdsi/submit).

- Если вы получили сообщение электронной почты (с вложением или без него), которое вы хотите отправить в корпорацию Майкрософт для анализа, просмотрите [сообщения отчетов и файлы в корпорацию Майкрософт](report-junk-email-messages-to-microsoft.md).
