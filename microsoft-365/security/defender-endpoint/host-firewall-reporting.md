---
title: Учет брандмауэра в Microsoft Defender для конечной точки
description: Хост и просмотр отчетов брандмауэра в Microsoft 365 центре безопасности.
keywords: защитник windows, брандмауэр
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809344"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Учет брандмауэра в Microsoft Defender для конечной точки

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Если вы администратор, теперь вы можете принимать отчеты брандмауэра в центр Microsoft 365 [безопасности.](https://security.microsoft.com) Эта функция позволяет просматривать отчеты Windows 10 и Windows server 2019 из централизованного расположения. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы 

- Необходимо запускать Windows 10 или Windows Server 2019.
- С бортовых устройств в службу Microsoft Defender для конечных точек см. [здесь.](onboard-configure.md) 
- Чтобы Microsoft 365 центр безопасности начал получать данные, необходимо  включить события аудита для брандмауэр Защитника Windows с помощью advanced Security: 
    - [Падение пакетов платформы фильтрации аудита](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [Подключение платформы фильтрации аудита](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- Включить эти события с помощью редактора объектов групповой политики, локальной политики безопасности или auditpol.exe команд. Дополнительные сведения см. [здесь.](/windows/win32/fwp/auditing-and-logging) 
    - Две команды PowerShell:
        - **auditpol /set/subcategory:"Filtering Platform Packet Drop" /failure:enable** 
        - **auditpol /set/subcategory:"Filtering Platform Connection" /failure:enable** 

## <a name="the-process"></a>Процесс
> [!NOTE]
> Обязательно следуйте инструкциям из раздела выше и правильно настройте устройства для участия в предварительном предварительном просмотре.

- После включения событий центр Microsoft 365 начнет отслеживать данные.
    - Удаленный IP-адрес, удаленный порт, локальный порт, локальный IP, имя компьютера, процесс между входящие и исходящие подключения.
- Администраторы теперь могут видеть Windows брандмауэра [](https://security.microsoft.com/firewall)здесь .
    - Дополнительные отчеты можно упростить, скачав скрипт настраиваемой отчетности для мониторинга брандмауэр Защитника Windows с помощью Power BI. [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) 
    - До отражения данных может занять до 12 часов.

## <a name="supported-scenarios"></a>Поддерживаемые сценарии
Следующие сценарии поддерживаются во время предварительного просмотра Ring0. 

### <a name="firewall-reporting-in-security-center"></a>Отчеты о брандмауэре в центре безопасности

Вот несколько примеров страниц отчета брандмауэра. Здесь вы найдете сводку действий входящие, исходящие и приложения. Вы можете получить доступ к этой странице напрямую, переехав https://security.microsoft.com/firewall на . 

> [!div class="mx-imgBorder"]
> ![Страница отчетов о брандмауэре хост](\images\host-firewall-reporting-page.png)

К этим отчетам также можно получить доступ, переехав в службу **Reports**  >  **Security Report**  >  **Devices** (section),  расположенную в нижней части карты заблокированных подключений к брандмауэру.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>От "Компьютеры с заблокированным подключением" к устройству

Карты поддерживают интерактивные объекты. Вы можете сверлить активность устройства, нажав на имя устройства, которое запустится на новой вкладке, и отвести вас непосредственно на вкладку https://securitycenter.microsoft.com **Timeline** устройства. 

> [!div class="mx-imgBorder"]
> ![Компьютеры с заблокированным подключением](\images\firewall-reporting-blocked-connection.png)

Теперь вы можете выбрать вкладку **Timeline,** которая даст вам список событий, связанных с этим устройством. 

После нажатия кнопки **"Фильтры"** в правом верхнем углу области просмотра выберите нужный тип события. В этом случае выберите **события Брандмауэра,** и области будут фильтроваться для событий Брандмауэра. 

> [!div class="mx-imgBorder"]
> ![Кнопка Фильтры](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Упражнение в продвинутую охоту (предварительное обновление)

Брандмауэр сообщает о поддержке бурения с карты непосредственно в **advanced Hunting,** нажав кнопку **Open Advanced hunting.** Запрос будет предварительно заполнен. 

> [!div class="mx-imgBorder"]
> ![Кнопка Open Advanced hunting](\images\firewall-reporting-advanced-hunting.png)

Теперь запрос можно выполнять, а все связанные события брандмауэра за последние 30 дней можно изучить. 

Для дополнительных отчетов или пользовательских изменений запрос можно экспортировать в Power BI для дальнейшего анализа. Настраиваемые отчеты можно упростить, скачав сценарий настраиваемой отчетности для мониторинга брандмауэр Защитника Windows с помощью Power BI. [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) 

 