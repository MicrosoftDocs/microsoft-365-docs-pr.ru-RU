---
title: Угрозы, обнаруженные антивирусной программой в Microsoft Defender
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Узнайте, антивирусная программа в Microsoft Defender защищает ваши Windows устройства от угроз программного обеспечения, таких как вирусы, вредоносные программы и программы-шпионы.
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198367"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Угрозы, обнаруженные антивирусной программой в Microsoft Defender

антивирусная программа в Microsoft Defender защищает ваши Windows устройства от угроз программного обеспечения, таких как вирусы, вредоносные программы и программы-шпионы.

- Вирусы обычно распространяются, прикрепляя код к другим файлам на вашем устройстве или сети, что может привести к неправильной работе зараженных программ.
- Вредоносные программы включают вредоносные файлы, приложения и код, которые могут привести к повреждению и нарушению нормального использования устройств. Кроме того, вредоносные программы могут разрешить несанкционированный доступ, использовать системные ресурсы, украсть пароли и сведения об учетной записи, заблокировать вас на компьютере и попросить выкуп и другие.
- Программы-шпионы собирают данные, такие как действия для просмотра веб-страниц, и отправляют данные на удаленные серверы.
 
Чтобы обеспечить защиту от угроз, антивирусная программа в Microsoft Defender использует несколько методов. Эти методы включают облачную защиту, защиту в режиме реального времени и специальные обновления защиты.

- Защита от облачных сообщений обеспечивает практически мгновенное обнаружение и блокировку новых и возникающих угроз.
- При постоянном сканировании используются мониторинг файлов и процессов и другие методы (также известные как защита в режиме *реального времени).*
- Специализированные обновления защиты основаны на машинном обучении, человеческом и автоматизированном анализе больших данных и углубленном исследовании устойчивости к угрозам. 

Дополнительные новости о вредоносных программах и антивирусная программа в Microsoft Defender см. в следующих статьях: 

- [Понимание вредоносных программ & других угроз](/windows/security/threat-protection/intelligence/understanding-malware)
- [Как Корпорация Майкрософт определяет вредоносные программы и потенциально нежелательные приложения](/windows/security/threat-protection/intelligence/criteria)
- [Защита нового поколения в Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Что происходит, когда используется антивирусное решение, не в microsoft? 

антивирусная программа в Microsoft Defender является частью операционной системы и включена на устройствах, работающих Windows 10. Однако, если вы используете антивирусное решение, не в microsoft, и не используете [Microsoft Defender для конечной](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)точки, антивирусная программа в Microsoft Defender автоматически переходит в отключенный режим.  

В отключенном режиме пользователи и клиенты по-прежнему могут использовать антивирусная программа в Microsoft Defender для планового или по требованию сканирования для выявления угроз; однако антивирусная программа в Microsoft Defender больше не будет:

- используется в качестве антивирусного приложения по умолчанию.
- активно сканировать файлы на угрозы.
- устранение или устранение угроз.

Если удалить антивирусное решение, не включаемую в Microsoft, антивирусная программа в Microsoft Defender автоматически перейдите в активный режим, чтобы защитить Windows устройств от угроз.

> [!TIP]
> - Если вы используете Microsoft 365, антивирусная программа в Microsoft Defender в качестве основного антивирусного решения. Интеграция может обеспечить лучшую защиту. См. [совместно: антивирусная программа в Microsoft Defender и Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Не забудьте антивирусная программа в Microsoft Defender, даже если вы используете антивирусное решение, не в microsoft.

## <a name="what-to-expect-when-threats-are-detected"></a>Чего ожидать при обнаружении угроз

Когда угрозы обнаруживаются антивирусная программа в Microsoft Defender, происходят следующие вещи:

- Пользователи получают [уведомления в Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Обнаружения перечислены в приложении [Безопасность Windows на](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) странице **История** защиты.  
- Если вы [](secure-win-10-pcs.md) обеспечили безопасность Windows 10 устройств и зарегистрировали их в [Intune,](/mem/intune/enrollment/windows-enrollment-methods)а в вашей организации зарегистрировано 800 или меньше устройств, в центре  администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> на странице Угрозы и антивирусы, к  которым можно получить доступ с карты  **антивирусная программа в Microsoft Defender** на домашней странице (или с области навигации, выбрав антивирусные угрозы  >  **&** health).

    Если в вашей организации зарегистрировано более 800 устройств в Intune, вам будет предложено [](/mem/endpoint-manager-overview) просмотреть обнаружения угроз и сведения из Microsoft Endpoint Manager, а не со страницы **Threats и antivirus.**
 
    > [!NOTE]
    > Страница **антивирусная программа в Microsoft Defender** и **угрозы** и антивирусные программы выкатываются поэтапно, поэтому у вас может не быть немедленного доступа к ним.

В большинстве случаев пользователям не требуется принимать дополнительные меры. Как только вредоносный файл или программа обнаруживается на устройстве, антивирусная программа в Microsoft Defender блокирует его и не позволяет ему работать. Кроме того, новые обнаруженные угрозы добавляются в антивирусный и антивирусный движок, чтобы защитить другие устройства и пользователей.  

Если пользователь должен принять действие, например, одобрить удаление вредоносного файла, он увидит это в получаемом уведомлении. Дополнительные данные о действиях, антивирусная программа в Microsoft Defender от имени пользователя или действиях, которые могут потребоваться пользователям, см. в [статью История защиты.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Чтобы узнать, как управлять обнаружением угроз в качестве ИТ-специалиста/администратора, см. в статью Обзор обнаруженных угроз [и принять меры.](review-threats-take-action.md)

Чтобы узнать больше о различных угрозах, <a href="https://www.microsoft.com/wdsi/threats" target="_blank">посетите сайт портал для обнаружения угроз (Microsoft) Threats, на</a>котором можно выполнить следующие действия: 

- Просмотр текущих сведений о главных угрозах.
- Просмотр последних угроз для определенного региона.
- Поиск в энциклопедии угроз для сведений о конкретной угрозе.

## <a name="related-content"></a>См. также:

[Безопасные Windows 10](secure-windows-10-devices.md) устройства (статья)\
[Оценка антивирусная программа в Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (статья)\
[Как включить антивирусную](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) защиту в режиме реального времени и облачной доставки (статья)\
[Как включить и использовать антивирусная программа в Microsoft Defender из приложения Безопасность Windows](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (статья)\
[Как включить антивирусная программа в Microsoft Defender с помощью групповой политики](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (статья)\
[Обновление определений антивирусов](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (статья)\
[Отправка вредоносных программ и не вредоносных программ в Корпорацию Майкрософт для анализа](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (статья)
