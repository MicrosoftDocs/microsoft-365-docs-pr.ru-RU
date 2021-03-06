---
title: Добавление хранителей в Advanced eDiscovery случае
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как использовать встроенный инструмент управления хранителями в Advanced eDiscovery для координации рабочего процесса и определения соответствующих источников данных в случае.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740346"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Добавление хранителей в Advanced eDiscovery случае

Используйте встроенный инструмент управления хранителями в Advanced eDiscovery для координации рабочего процесса по управлению хранителями и выявлению соответствующих источников данных, связанных с делом. При добавлении хранителя система может автоматически идентифицировать и разместить удержание на Exchange и OneDrive для бизнеса учетной записи. В процессе обнаружения при расследовании можно также идентифицировать другие источники данных (например, почтовые ящики, сайты или Teams), к которые был предоставлен доступ к хранителям или к ним. В этой ситуации можно использовать средство управления хранителями, чтобы связать эти источники данных с конкретным хранителями. После добавления хранителей в дело и связи другого источника данных с ними можно быстро сохранить данные и поиска данных хранения.

Вы можете добавлять и управлять хранителями в Advanced eDiscovery в четырех шагах:

1. Определите хранителей.

2. Выберите расположения данных хранителя.

3. Настройка параметров удержания.

4. Просмотрите хранителей и завершите процесс.

   [![Вкладка Источники в Advanced eDiscovery случае ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Убедитесь, что у вас есть необходимые разрешения

Чтобы добавить хранителей в дело, необходимо быть членом группы ролей диспетчера электронных открытий. Это предоставляет вам необходимые разрешения для добавления хранителей в дело и хранения источников данных. Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Шаг 1. Определение хранителей

1. Войдите и войдите в учетную запись пользователя, которая получила соответствующие разрешения на [https://compliance.microsoft.com](https://compliance.microsoft.com) открытие электронных данных.

2. В левой области навигации Центра соответствия требованиям Microsoft 365 нажмите **Показать все** и выберите **Обнаружение электронных данных > Дополнительно**.

3. На **Advanced eDiscovery** нажмите вкладку **Cases** и выберите случай, в который необходимо добавить хранителей.

4. Щелкните **вкладку Источники** данных и нажмите **кнопку Добавить источник данных** Добавить новые  >  **хранители**.

5. Добавьте в дело одного или несколько пользователей в качестве хранителей, введя первую часть имени или псевдонима пользователя. После того как вы найдете правильного человека, выберите его имя, чтобы добавить их в список.

## <a name="step-2-choose-custodian-data-locations"></a>Шаг 2. Выбор расположения данных хранителя

После выбора хранителей система автоматически пытается определить и проверить этих пользователей и их источники данных. После добавления хранителей в список средство автоматически включает основной почтовый ящик и OneDrive учетную запись для каждого хранителя. Вы можете не включать эти источники данных при добавлении хранителей в дело.

Помимо почтового ящика и учетной записи OneDrive хранителя вы также можете связать другие расположения данных с хранителями, такими как сайт SharePoint или Microsoft Team, в который входит хранитель. Это позволяет сохранять, собирать, анализировать и анализировать контент в других источниках данных, связанных с хранителями дела.

Для отселки основного почтового ящика и OneDrive учетной записи хранителя:

1. Раздвойте хранителя, чтобы просмотреть основные расположения данных, автоматически связанные с каждым хранителями.

2. Выберите **Clear**  рядом с почтовым **ящиком или OneDrive,** чтобы удалить почтовый ящик или OneDrive или учетную запись хранителя в качестве расположения данных для этого хранителя.

   ![Настройка расположения для связывать с хранителями](../media/ConfigureCustodianLocations.png)

Чтобы связать другие почтовые ящики, сайты, Teams или Yammer группы с определенным хранителями:

1. Развяви хранителя, чтобы отобразить следующие службы, чтобы связать расположения данных с хранителями. Нажмите **кнопку Изменить** рядом со службой, чтобы добавить расположение данных.

   - **Exchange:** Используйте для связывать другие почтовые ящики с хранителями. Введите в поле поиска имя или псевдоним (не менее трех символов) почтовых ящиков пользователей или групп рассылки. Выберите почтовые ящики для назначения хранителю и нажмите кнопку **Добавить**.

   - **SharePoint:** Используйте для SharePoint сайтов с хранителями. Выберите сайт в списке или наведите URL-адрес в поле поиска. Выберите сайты для назначения хранителю и нажмите кнопку **Добавить**.

   - **Teams.** Используйте для назначения Microsoft Teams, в который в настоящее время входит хранитель. Выберите группы, назначив хранителю, а затем нажмите **кнопку Добавить**. После добавления группы система автоматически определяет и находит SharePoint и почтовый ящик группы, связанных с этой группой, и назначает их хранителю.

   - **Yammer:** Используйте для назначения Yammer групп, в которые в настоящее время входит хранитель. Выберите группы для назначения хранителю и нажмите кнопку **Добавить**. После добавления группы система автоматически определяет и находит SharePoint и почтовый ящик группы, связанных с этой группой, и назначает их хранителю.

   > [!NOTE]
   > Вы можете  использовать Exchange и **SharePoint** для связывать другие группы или группы Yammer (в которые хранитель не входит) с хранителями. Для этого необходимо добавить почтовый ящик и сайт, связанный с каждой группой или Yammer группой.

2. Вы можете просмотреть общее число почтовых ящиков, сайтов, Teams и Yammer групп, назначенных каждому хранителя, расширяя каждый хранитель в таблице. Когда вы завершите назначенное расположение данных для каждого хранителя, эти ассоциации будут поддерживаться и использоваться во время этапов сбора, обработки и проверки в процессе Advanced eDiscovery процесса.

3. После добавления хранителей и настройки расположения данных щелкните **Далее,** чтобы перейти на страницу **Параметры удержания.**  

## <a name="step-3-configure-hold-settings"></a>Шаг 3. Настройка параметров удержания

 После завершения работы с хранителями и расположениями данных можно придержать некоторых или всех хранителей. При удержании хранителя все содержимое во всех расположениях контента, связанных с хранителями, сохраняется до удаления удержания или освобождения хранителя из удержания. В некоторых случаях может потребоваться добавить хранителей в дело, не помещая их на удержание.

Для удержания хранителей и источников данных:

1. На странице **Параметры удержания** можно применить удержание к отдельным хранителям, выбрав почтовый ящик в столбце **Удержание.**

   Кроме того, вы можете разместить всех хранителей на удержание, выбрав контрольный ящик **Hold** в верхней части столбца.

2. Проверьте выборы удержания хранителя и нажмите кнопку **Далее**.

   > [!NOTE]
   > Если не разместить удержание на хранителях, хранитель и связанные с ним источники данных будут добавлены в дело, но содержимое в этих источниках данных не будет сохранено удержанием, связанным с делом.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Шаг 4. Просмотр хранителей и завершение процесса

Перед добавлением хранителей в дело можно просмотреть список хранителей, назначенное им расположение данных и параметры хранения.

1. Проверка и проверка всех источников данных и параметр удержания, связанных с каждым хранителями в таблице. При необходимости перейдите на страницу **Определить хранителя** или **параметры удержания,** чтобы внести какие-либо изменения.

2. Щелкните **Отправить,** чтобы добавить хранителей и их расположения данных в дело и применить все параметры хранения.

   Новые хранители добавляются в дело и отображаются на вкладке **Источники** данных.

   [![Хранители, перечисленные на вкладке Источники данных ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
