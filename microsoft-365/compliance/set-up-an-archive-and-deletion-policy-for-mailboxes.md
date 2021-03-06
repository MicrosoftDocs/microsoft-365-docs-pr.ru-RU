---
title: Настройка политики архивации и удаления для почтовых ящиков в организации
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: Узнайте, как создать политику архивации и удаления в Microsoft 365, которая автоматически перемещает элементы в архивный почтовый ящик пользователя.
ms.openlocfilehash: 45d6428f5b0a856538d500b1d1f0447447b9dfe9
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341644"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Настройка политики архивации и удаления для почтовых ящиков в организации

В Microsoft 365 администраторы могут создать политику архивации и удаления, которая автоматически перемещает элементы в архивный почтовый ящик пользователя и автоматически удаляет элементы из почтового ящика. Администратор делает это, создавая политику хранения, назначенную почтовым ящикам, и перемещает элементы в архивный почтовый ящик пользователя через определенный период времени, а также удаляет элементы из почтового ящика после достижения определенного возраста. Фактические правила, определяя, какие элементы перемещаются или удаляются и когда это происходит, называются тегами хранения. Теги хранения связаны с политикой хранения, которая, в свою очередь, назначена почтовому ящику пользователя. Тег хранения применяет параметры хранения для отдельных сообщений и папок в почтовом ящике пользователя. Он определяет, как долго сообщение остается в почтовом ящике и какие действия принимаются, когда сообщение достигает указанного возраста хранения. Когда сообщение достигает возраста хранения, оно либо перемещается в архивный почтовый ящик пользователя, либо удаляется.
  
В этой статье будет создана политика архивизации и хранения для фиктивной организации с именем Alpine House. Настройка этой политики включает следующие задачи:
  
- Включение архивного почтового ящика для каждого пользователя организации. Это предоставляет пользователям дополнительное хранилище почтовых ящиков и необходимо, чтобы политика хранения может переместить элементы в архивный почтовый ящик. Он также позволяет хранить архивные данные пользователя, перемещая элементы в их архивный почтовый ящик.

- Создание трех пользовательских тегов хранения, которые делают следующее:

  - Автоматически перемещает элементы 3-летнего возраста в архивный почтовый ящик пользователя. Перемещение элементов в архивный почтовый ящик освободит место в основном почтовом ящике пользователя.

  - Автоматически удаляет элементы 5-летней давности из папки "Удаленные элементы". Это также освободит место в основном почтовом ящике пользователя. Пользователь будет иметь возможность восстановить эти элементы, если это необходимо. Дополнительные сведения см. в сноске в разделе [Дополнительные](#more-information) сведения. 

  - Автоматически (и постоянно) удаляет элементы, которые 7 лет, как из основного, так и из архивного почтового ящика. Из-за правил соответствия требованиям некоторые организации обязаны хранить электронную почту в течение определенного периода времени. По истечении этого периода организации может потребоваться навсегда удалить эти элементы почтовых ящиков пользователей.

- Создание новой политики хранения и добавление к ней новых пользовательских тегов хранения. Кроме того, в новую политику хранения будут добавлены встроенные теги хранения. Это включает личные теги, которые пользователи могут назначать элементу в почтовом ящике. Вы также добавим тег хранения, который перемещает элементы из папки "Извлекаемые элементы" в основном почтовом ящике пользователя в папку "Извлекаемые элементы" в архивном почтовом ящике. Это помогает освободить место в папке "Извлекаемые элементы" пользователя при удержании почтового ящика.

Вы можете следовать некоторым или всем шагам в этой статье, чтобы настроить политику архивации и удаления почтовых ящиков в вашей организации. Рекомендуется протестировать этот процесс на нескольких почтовых ящиках перед его реализацией на всех почтовых ящиках в организации.
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Перед настройками политики архивации и удаления

- Для выполнения действий в этом разделе необходимо быть глобальным администратором в организации. 

- При создании новой учетной записи пользователя и назначении Exchange Online лицензии для пользователя автоматически создается почтовый ящик. После создания почтового ящика ему автоматически назначена политика хранения по умолчанию с именем MrM Policy по умолчанию. В этой статье вы создайте новую политику хранения, а затем назначите ее почтовым ящикам пользователей, заменив политику MRM по умолчанию. В почтовом ящике может быть назначена только одна политика хранения.

- Дополнительные новости о тегах хранения и политиках хранения в Exchange Online см. в Exchange Online теги хранения и [политики хранения.](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies)

## <a name="step-1-enable-archive-mailboxes-for-users"></a>Шаг 1. Включить архивные почтовые ящики для пользователей

Первый шаг — включить архивный почтовый ящик для каждого пользователя в организации. Необходимо включить архивный почтовый ящик пользователя, чтобы тег хранения с действием хранения "Перемещение в архив" перемещал элемент по истечении срока хранения.
  
> [!NOTE]
> Вы можете включить архивные почтовые ящики в любое время во время этого процесса, до тех пор, пока они включены в определенный момент до завершения процесса. Если архивный почтовый ящик не включен, никакие действия не принимаются к пунктам, для них назначена политика архивации или удаления.
  
1. Перейдите на сайт <https://compliance.microsoft.com>.

2. Во входе с помощью глобальной учетной записи администратора.
    
3. В Центр соответствия требованиям Microsoft 365 нажмите **кнопку Управление информацией,** а затем нажмите вкладку **Архив.**

    Отображается список почтовых ящиков в организации и включен ли соответствующий архивный почтовый ящик.

4. Выберите все почтовые ящики, щелкнув первый в списке, удерживая клавишу **Shift,** а затем щелкнув последний в списке.

    > [!TIP]
    > На этом шаге предполагается, что архивные почтовые ящики не включены. Если у вас есть почтовые ящики с включенным архивом, удерживайте клавишу **Ctrl** и щелкните каждый почтовый ящик с отключенным архивным почтовым ящиком. Или вы можете щелкнуть заглавную колонку **архивных** почтовых ящиков, чтобы сортировать строки в зависимости от того, включен или отключен архивный почтовый ящик, чтобы упростить выбор почтовых ящиков.
  
5. В области сведений в статье **Bulk Edit** нажмите кнопку **Включить**.

    Отображается предупреждение о том, что элементы старше двух лет будут перемещены в новый почтовый ящик архива. Это происходит из-за того, что политика хранения по умолчанию, назначенная новому почтовому ящику пользователя при его создания, имеет тег политики по умолчанию архива с возрастом хранения 2 года. Пользовательский тег политики по умолчанию архива, созданный в шаге 2, имеет возраст хранения 3 года. Это означает, что элементы старше 3 лет будут перемещены в почтовый ящик архива.

6. Щелкните **Да,** чтобы закрыть предупреждение и запустить процесс, чтобы включить архивный почтовый ящик для каждого выбранного почтового ящика.

7. После завершения процесса щелкните **Обновление** ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) обновления, чтобы обновить список на странице **Архив.**

    Почтовый ящик архива включен для всех пользователей в вашей организации.

    ![Список почтовых ящиков с включенным архивным почтовым ящиком](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>Шаг 2. Создание новых тегов хранения для политик архива и удаления

На этом этапе создадут три пользовательских тега хранения, которые были описаны ранее.
  
- Alpine House 3 Year Move to Archive (custom archive policy)

- Alpine House 7 Year Permanently Delete (custom deletion policy)

- Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)

Чтобы создать новые теги хранения, вы будете использовать центр администрирования Exchange (EAC) в Exchange Online организации. Обязательно используйте классическую версию EAC.
  
1. Перейдите [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) к и войдите с помощью учетных данных.
  
2. В EAC перейдите к тегам **хранения управления**  >  **соответствием** требованиям

    Отображается список тегов хранения для организации.

### <a name="create-a-custom-archive-default-policy-tag"></a>Создание настраиваемого тега политики по умолчанию архива
  
Сначала создадим настраиваемый тег политики политики по умолчанию архива (DPT), который будет перемещать элементы в почтовый ящик архива через 3 года.
  
1. На странице **Теги хранения** нажмите **кнопку Новый** значок тега Новый, а затем выберите применяется автоматически для всего почтового ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **ящика (по умолчанию).**

2. На странице Новый тег, автоматически применяемый на всю страницу почтового ящика **(по умолчанию),** выполните следующие поля: 

    ![Параметры создать новый тег политики по умолчанию архива](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **Имя** Введите имя для нового тега хранения. 

   2. **Действие хранения** Выберите **Перемещение в архив** для перемещения элементов в почтовый ящик архива по истечении срока хранения.

   3. **Период хранения** Выберите, **когда элемент достигнет следующего возраста (в днях)** и введите продолжительность периода хранения. В этом случае элементы будут перемещены в почтовый ящик архива через 1095 дней (3 года).

   4. **Комментарий** (необязательный) Введите комментарий, который объясняет назначение настраиваемого тега хранения.

3. Щелкните **Сохранить** для создания настраиваемой DPT архива.

    Новый DPT архива отображается в списке тегов хранения.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Создание настраиваемого тега политики удаления по умолчанию
  
Далее вы создадим еще один пользовательский DPT, но это будет политика удаления, которая окончательно удаляет элементы после 7 лет.
  
1. На странице **Теги хранения** нажмите **кнопку Новый** значок тега Новый, а затем выберите применяется автоматически для всего почтового ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **ящика (по умолчанию).**

2. На странице Новый тег, автоматически применяемый на всю страницу почтового ящика **(по умолчанию),** выполните следующие поля: 

    ![Параметры создать новый тег политики политики удаления по умолчанию](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **Имя** Введите имя для нового тега хранения. 

   2. **Действие хранения** Выберите **Permanently Delete** для очистки элементов из почтового ящика по истечении срока хранения.

   3. **Период хранения** Выберите, **когда элемент достигнет следующего возраста (в днях)** и введите продолжительность периода хранения. Для этого сценария элементы будут сгвеяться через 2555 дней (7 лет).

   4. **Комментарий** (необязательный) Введите комментарий, который объясняет назначение настраиваемого тега хранения. 

3. Щелкните **Сохранить,** чтобы создать настраиваемый DPT удаления. 

    Новый DPT удаления отображается в списке тегов хранения.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Создание настраиваемого тега политики хранения для папки "Удаленные элементы"
  
Последний тег хранения, который вы создадим, — это настраиваемый тег политики хранения (RPT) для папки "Удаленные элементы". Этот тег удаляет элементы в папке "Удаленные элементы" через 5 лет и предоставляет период восстановления, когда пользователи могут использовать средство Восстановления удаленных элементов для восстановления элемента.
  
1. На странице **Теги хранения** щелкните **Новый** значок тега New, а затем выберите автоматически примененную ![ к ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **папке по умолчанию.**

2. На **теге New, который автоматически применяется к странице** папки по умолчанию, выполните следующие поля:

    ![Параметры создать новый тег политики хранения для папки "Удаленные элементы"](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **Имя** Введите имя для нового тега хранения. 

   2. **Примени этот тег к следующей папке по умолчанию** В выпадаемом списке выберите **удаленные элементы.**

   3. **Действие хранения** Выберите **Удаление** и разрешение восстановления для удаления элементов по истечении срока хранения, но разрешить пользователям восстанавливать удаленный элемент в течение периода хранения удаленных элементов (который по умолчанию составляет 14 дней).

   4. **Период хранения** Выберите, **когда элемент достигнет следующего возраста (в днях)** и введите продолжительность периода хранения. Для этого сценария элементы будут удалены через 1825 дней (5 лет).

   5. **Комментарий** (необязательный) Введите комментарий, который объясняет назначение настраиваемого тега хранения. 

3. Нажмите **кнопку Сохранить,** чтобы создать настраиваемый RPT для папки "Удаленные элементы".

    Новый RPT отображается в списке тегов хранения.

## <a name="step-3-create-a-new-retention-policy"></a>Шаг 3. Создание новой политики хранения

После создания пользовательских тегов хранения следующий шаг — создание новой политики хранения и добавление тегов хранения. Вы добавим три настраиваемые теги хранения, созданные в шаге 2, и встроенные теги, упомянутые в первом разделе. На шаге 4 вы назначите эту новую политику хранения почтовым ящикам пользователей.
  
1. В EAC перейдите **к** политикам хранения соответствия  >  требованиям.

2. На странице **Политики хранения** нажмите кнопку **Новый значок** ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

3. В поле **Имя** введите имя новой политики хранения; например, **политика архивации и удаления дома Alpine House.**

4. В **тегах Хранения** щелкните **Добавить значок Добавить** новый ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) .

    Отображается список тегов хранения в организации. Обратите внимание на пользовательские теги, созданные в шаге 2.

5. Добавьте 9 тегов хранения, которые выделены на следующем скриншоте (эти теги описаны более подробно в разделе [Дополнительные сведения).](#more-information) Чтобы добавить тег хранения, выберите его и нажмите **кнопку Добавить**.

    ![Добавление тегов хранения в новую политику хранения](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > Вы можете выбрать несколько тегов хранения, удерживая клавишу **Ctrl** и щелкнув каждый тег. 
  
6. После добавленных тегов хранения нажмите **кнопку ОК**.

7. На странице **Новая политика хранения** щелкните **Сохранить,** чтобы создать новую политику.

    Новая политика хранения отображается в списке. Выберите его для отображения связанных с ней тегов хранения в области сведений.

    ![Новая политика хранения и список связанных тегов хранения](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>Шаг 4. Назначение новой политики хранения почтовым ящикам пользователей

Когда создается новый почтовый ящик, ему по умолчанию назначена политика хранения с именем MRM по умолчанию. На этом этапе вы замените эту политику хранения (так как в почтовом ящике может быть назначена только одна политика хранения), назначив новую политику хранения, созданную в шаге 3, почтовым ящикам пользователей в организации. На этом шаге предполагается назначить новую политику всем почтовым ящикам в организации.
  
1. В EAC перейдите к **почтовым ящикам**  >  **получателей**.

    Отображается список всех почтовых ящиков пользователей в организации.

2. Выберите все почтовые ящики, щелкнув первый в списке, удерживая клавишу **Shift,** а затем щелкнув последний в списке. 

3. В подробностях области справа от EAC в статье **Bulk Edit** щелкните **Дополнительные параметры**.

4. В разделе **Политика хранения** щелкните **Обновить**.

5. На странице **Политика удержания** в списке **Выбор** политики хранения выберите политику хранения, созданную в шаге 3; например, **политика архива и** хранения дома Alpine House.

6. Щелкните **Сохранить,** чтобы сохранить новое назначение политики хранения.

7. Чтобы убедиться, что новая политика хранения назначена почтовым ящикам, можно сделать следующее:

   1. Выберите почтовый ящик на странице **Почтовые ящики** и нажмите кнопку **Изменить изменить** ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) .

   2. На странице свойств почтовых ящиков для выбранного пользователя щелкните **функции почтовых ящиков.**

   Имя новой политики, назначенной почтовому ящику,  отображается в перечне политики хранения.

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(Необязательный) Шаг 5. Запуск помощника управляемых папок для применения новых параметров

После применения новой политики хранения к почтовым ящикам в шаге 4 может занять до 7 дней Exchange Online для новых параметров хранения, которые будут применены к почтовым ящикам. Это вызвано тем, что процесс, называемый *помощником управляемых* папок, обрабатывает почтовые ящики по крайней мере один раз в 7 дней. Вместо ожидания запуска помощника управляемых папок вы можете заставить это сделать, заняв в powerShell управляемый Exchange Online кодлет **Start-ManagedFolderAssistant.**

 **Что происходит при запуске помощника управляемых папок?** Он применяет параметры политики хранения, проверяя элементы в почтовом ящике и определяя, подлежат ли они хранению. Затем он штамповки элементов, подлежат сохранению с соответствующим тегом хранения, а затем принимает указанное действие хранения на элементы, прошедшие их возраст хранения.
  
Ниже положены действия по подключению к Exchange Online PowerShell и запуску помощника управляемых папок на каждом почтовом ящике в организации.

1. [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Запустите следующие две команды, чтобы запустить помощник управляемых папок для всех почтовых ящиков пользователей в организации.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

Вот и все! Вы создали политику архива и удаления для организации Alpine House.

> [!NOTE]
> Как уже говорилось ранее, помощник по управляемым папкам обрабатывает почтовые ящики не реже одного раза в 7 дней. Так что возможно, что почтовый ящик может обрабатываться помощником управляемых папок чаще. Кроме того, администраторы не могут предсказать, когда почтовый ящик будет обработан помощником управляемых папок, что является одной из причин, по которой вы можете запустить его вручную. Однако если вы хотите временно запретить помощнику управляемых папок применять новые параметры хранения к почтовому ящику, можно запустить команду, чтобы временно отключить помощник управляемой папки от обработки почтового `Set-Mailbox -ElcProcessingDisabled $true` ящика. Чтобы повторно включить помощник управляемой папки для почтового ящика, запустите `Set-Mailbox -ElcProcessingDisabled $false` команду. Наконец, если у пользователя почтового ящика отключена учетная запись, мы не будем обрабатывать элементы перемещения в архивное действие для этого почтового ящика.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>(Необязательный) Шаг 6. Сделайте новую политику хранения по умолчанию для организации

На шаге 4 необходимо назначить новую политику хранения существующим почтовым ящикам. Но вы можете настроить Exchange Online, чтобы новая политика хранения была назначена новым почтовым ящикам, созданным в будущем. Это необходимо с помощью Exchange Online PowerShell для обновления плана почтовых ящиков организации по умолчанию. План *почтовых ящиков* — это шаблон, который автоматически настраивает свойства на новых почтовых ящиках.  На этом необязательный шаг можно заменить текущую политику хранения, назначенную плану почтовых ящиков (по умолчанию, политика MRM по умолчанию) политикой хранения, созданной в шаге 3. После обновления плана почтовых ящиков новая политика хранения будет назначена новым почтовым ящикам.

1. [Подключение к PowerShell для Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Запустите следующую команду, чтобы отобразить сведения о планах почтовых ящиков в организации.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    Обратите внимание на план почтового ящика, за который установлено значение по умолчанию.

3. Запустите следующую команду, чтобы назначить новую политику хранения, созданную в шаге 3 (например, **Alpine House Archive and Retention Policy)** к плану почтовых ящиков по умолчанию. В этом примере предполагается, что имя плана почтовых ящиков по умолчанию **exchangeOnlineEnterprise.**

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Вы можете повторно перезаписи команды на шаге 2, чтобы убедиться, что политика хранения, назначенная плану почтовых ящиков по умолчанию, была изменена.

## <a name="more-information"></a>Дополнительные сведения

- Как рассчитывается возраст хранения? Возраст хранения элементов почтовых ящиков рассчитывается с даты доставки или даты создания таких элементов, как черновики сообщений, которые не отправляются, но создаются пользователем. Когда помощник для управляемых папок обрабатывает элементы в почтовом ящике, он помечает дату начала и дату окончания срока хранения для всех элементов, которые имеют теги хранения с действием хранения Удалить и разрешить восстановление или Удалить навсегда. Элементы с тегом архива штампуются датой перемещения. 

- В следующей таблице содержится больше сведений о каждом теге хранения, который добавляется в настраиваемую политику хранения, созданную после действий в этом разделе.

    | Тег хранения | Что делает этот тег | Встроенный или настраиваемый? | Type |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 Year Move to Archive  <br/> |Перемещает элементы со сроком действия 1095 дней (3 года) в почтовый ящик архива.  <br/> |Custom [(См. шаг 2. Создание новых](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)тегов хранения для политик архива и удаления)  <br/> |Тег политики по умолчанию (архив); этот тег автоматически применяется для всего почтового ящика.  <br/> |
    |Alpine House 7 Year Permanently Delete  <br/> |Постоянно удаляет элементы в основном почтовом ящике или архивном почтовом ящике, когда им 7 лет.  <br/> |Custom [(См. шаг 2. Создание новых](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)тегов хранения для политик архива и удаления)  <br/> |Тег политики по умолчанию (удаление); этот тег автоматически применяется для всего почтового ящика.  <br/> |
    |Alpine House Deleted Items 5 Years Delete and Allow Recovery  <br/> |Удаляет элементы из папки "Удаленные элементы", которая составляет 5 лет. Пользователи могут восстановить эти элементы в течение 14 дней после их удаления.<sup>\*</sup> <br/> |Custom [(См. шаг 2. Создание новых](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)тегов хранения для политик архива и удаления)  <br/> |Тег политики хранения (удаленные элементы); этот тег автоматически применяется к пунктам в папке Удаленные элементы.  <br/> |
    |Извлекаемые элементы 14 дней Переход в архив  <br/> |Перемещает элементы, которые были в папке "Извлекаемые элементы" в течение 14 дней, в папку "Извлекаемые элементы" в архивном почтовом ящике.  <br/> |Встроенные  <br/> |Тег политики хранения (элементы, которые можно восстановить); этот тег автоматически применяется к пунктам в папке "Извлекаемые элементы".  <br/> |
    |Нежелательной почты  <br/> |Постоянно удаляет элементы, которые были в папке нежелательной почты в течение 30 дней. Пользователи могут восстановить эти элементы в течение 14 дней после их удаления.<sup>\*</sup> <br/> |Встроенные  <br/> |Тег политики хранения (нежелательной почты); этот тег автоматически применяется к пунктам в папке нежелательной почты.  <br/> |
    |Удалять через 1 месяц  <br/> |Постоянно удаляет элементы, которые находятся в течение 30 дней. Пользователи могут восстановить эти элементы в течение 14 дней после их удаления.<sup>\*</sup> <br/> |Встроенные  <br/> |Личный; этот тег может применяться пользователями.  <br/> |
    |Удалять через 1 год  <br/> |Постоянно удаляет элементы, которые находятся в течение 365 дней. Пользователи могут восстановить эти элементы в течение 14 дней после их удаления.<sup>\*</sup> <br/> |Встроенные  <br/> |Личный; этот тег может применяться пользователями.  <br/> |
    |Никогда не удалять  <br/> |Этот тег предотвращает удаление элементов политикой хранения.  <br/> |Встроенные  <br/> |Личный; этот тег может применяться пользователями.  <br/> |
    |Личный тег. Перемещать элементы в архив через 1 год  <br/> |Перемещает элементы в почтовый ящик архива после 1 года.  <br/> |Встроенные  <br/> |Личный; этот тег может применяться пользователями.  <br/> |

    > <sup>\*</sup>Пользователи могут использовать средство Восстановления удаленных элементов в Outlook и Outlook в Интернете (ранее известный как Outlook Web App) для восстановления удаленных элементов в период хранения удаленных элементов, который по умолчанию составляет 14 дней в Exchange Online. Администратор может использовать Windows PowerShell, чтобы увеличить срок хранения удаленных элементов до 30 дней. Дополнительные сведения см. в статье: Восстановление удаленных элементов в Outlook для [Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) и изменение периода хранения удаленных элементов для [почтового ящика в Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention)
  
- Использование **тега "Извлеченные элементы 14** дней Перейти к архиву" позволяет освободить пространство для хранения в папке "Извлекаемые элементы" в основном почтовом ящике пользователя. Это полезно, когда почтовый ящик пользователя находится на удержании, что означает, что никогда не будет удален почтовый ящик пользователя навсегда. Не перемещая элементы в архивный почтовый ящик, возможно, будет достигнута квота хранилища для папки "Извлекаемые элементы" в основном почтовом ящике. Дополнительные сведения об этом и о том, как этого избежать, см. в статьи Увеличение квоты извлекаемых элементов для почтовых [ящиков в удержании.](./increase-the-recoverable-quota-for-mailboxes-on-hold.md)
