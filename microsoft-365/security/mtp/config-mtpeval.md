---
title: Настройка основ Защитника Microsoft 365 для пробной или пилотной среды
description: Настройте основы Защитника Microsoft 365, такие как Microsoft Defender для Office 365, Microsoft Defender для удостоверений, Microsoft Cloud App Security и Microsoft Defender для конечной точки, для пробной или пилотной среды.
keywords: настройка пробного комплекта Защиты от угроз (Майкрософт), конфигурация пробного комплекта Защиты от угроз (Майкрософт), настройка пилотного проекта Защиты от угроз (Майкрософт), настройка основ Защиты от угроз (Майкрософт), основы Защиты от угроз (Майкрософт)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932242"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Настройка основных элементов Microsoft 365 Defender для пробной лабораторной или пилотной среды

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender


Создание пробной лабораторной или пилотной среды Microsoft 365 Defender и ее развертывание — это трех этапов:

|[![Этап 1. Подготовка](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Этап 1. Подготовка](prepare-mtpeval.md) |[![Этап 2. Настройка](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Этап 2. Настройка](setup-mtpeval.md) |![Этап 3. Ветвь](../../media/phase-diagrams/onboard.png)<br/>Этап 3. Ветвь | [![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Вернуться к пилотной книге](mtp-pilot.md) |
|--|--|--|--|
|| |*Вы здесь!* | |

В настоящее время вы работаете на этапе настройки.

Подготовка — это ключ к успешному развертыванию. В этой статье вы получите руководство по пунктам, которые необходимо учитывать при подготовке к развертыванию Microsoft Defender для конечной точки.


## <a name="microsoft-365-defender-pillars"></a>Основы Защитника Microsoft 365
Защитник Microsoft 365 состоит из четырех основных элементов. Хотя один из основных принципов уже может быть важным для безопасности вашей сетевой организации, включение четырех опор Защитника Microsoft 365 придаст вашей организации наибольшее значение.

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

В этом разделе вы сможете настроить:
-   Microsoft Defender для Office 365
-   Microsoft Defender для удостоверений 
-   Microsoft Cloud App Security
-   Microsoft Defender для конечной точки


## <a name="configure-microsoft-defender-for-office-365"></a>Настройка Microsoft Defender для Office 365

>[!NOTE]
>Пропустите этот шаг, если вы уже включили Защитник для Office 365. 

Существует модуль PowerShell под названием *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* который помогает определить некоторые из этих параметров. При запуске в качестве администратора в клиенте get-ORCAReport поможет создать оценку параметров защиты от нежелательной почты, фишинга и других параметров санации сообщений. Вы можете скачать этот модуль из https://www.powershellgallery.com/packages/ORCA/ . 

1. Перейдите к политике управления угрозами в Центре & безопасности и соответствия требованиям [Office 365.](https://protection.office.com/homepage)  >    >  

   ![Изображение of_Office 365 security & Compliance Center Threat management page](../../media/mtp-eval-32.png)
 
2. Щелкните **"Антифишинг",** **выберите "Создать"** и в заполните имя и описание политики. Нажмите кнопку **Далее**.

   ![Изображение of_Office 365 security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Изменение политики advanced anti-phishing в Microsoft Defender для Office 365. Change **Advanced Phishing Threshold** to **2 - Aggressive**.

3. Щелкните **меню "Добавить условия"** и выберите домены в качестве домена получателя. Нажмите кнопку **Далее**.

   ![Изображение of_Office 365 security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)
 
4. Просмотрите параметры. Нажмите **кнопку "Создать эту политику"** для подтверждения. 

   ![Изображение of_Office 365 security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)
 
5. Выберите **"Безопасные вложения"** и выберите параметр **"Включить ATP для SharePoint, OneDrive и Microsoft Teams".**

   ![Изображение of_Office 365 & соответствия требованиям, на которой можно включить ATP для SharePoint, OneDrive и Microsoft Teams](../../media/mtp-eval-36.png)

6. Щелкните значок "+", чтобы создать новую политику безопасных вложений, примените ее в качестве домена получателя к доменам. Щелкните **Сохранить**.

   ![Изображение of_Office 365 security & Compliance Center, где можно создать новую политику безопасных вложений](../../media/mtp-eval-37.png)
 
7. Затем выберите политику **безопасных ссылок,** а затем щелкните значок карандаша, чтобы изменить политику по умолчанию.

8. Убедитесь, **что** параметр "Не отслеживать" при выборе пользователями параметра "Безопасные ссылки" не выбран, а остальные параметры выбраны. Подробные [сведения см. в параметрах безопасных](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) ссылок. Щелкните **Сохранить**. 

   ![Изображение of_Office 365 security & Compliance Center, на которой показано, что параметр "Не отслеживать" при нажатии кнопки "Безопасный" не выбран](../../media/mtp-eval-38.png)

9. Затем выберите политику **борьбы с вредоносными** программами, выберите значение по умолчанию и значок карандаша.

10. Щелкните **"Параметры",** выберите **"Да" и используйте** текст уведомления по умолчанию, чтобы включить ответ **на обнаружение вредоносных программ.** **Включите фильтр общих типов вложений.** Щелкните **Сохранить**.

    ![Изображение of_Office 365 security & Compliance Center, на которой показано, что ответ на обнаружение вредоносных программ включен с уведомлением по умолчанию и включен фильтр общих типов вложений](../../media/mtp-eval-39.png)
  
11. Перейдите к поиску в журнале аудита & центра безопасности и & Office [365](https://protection.office.com/homepage)  >    >   и включите аудит.

    ![Изображение of_Office 365 security & Compliance Center, где можно включить поиск в журнале аудита](../../media/mtp-eval-40.png)

12. Интеграция Microsoft Defender для Office 365 с Microsoft Defender для конечной точки. Перейдите в обозреватель управления угрозами Центра безопасности и соответствия & Office [365](https://protection.office.com/homepage)и выберите "Параметры конечной точки в Microsoft Defender для конечных точек" в правом верхнем  >    >   углу  экрана. В диалоговом окне "Защитник конечной точки" включите подключение к **Microsoft Defender для конечной точки.**

    ![Изображение of_Office 365 security & Compliance Center, где можно включить подключение к конечной точке в Microsoft Defender](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Настройка Microsoft Defender для удостоверений

>[!NOTE]
>Пропустите этот шаг, если вы уже включили Microsoft Defender для удостоверений

1. Перейдите в [Центр безопасности Microsoft 365>](https://security.microsoft.com/info) выберите "Дополнительные **ресурсы** Microsoft Defender  >  **для удостоверений".**

   ![Изображение of_Microsoft 365: страница "Центр безопасности 365", на которой можно открыть Microsoft Defender для удостоверений](../../media/mtp-eval-42.png)

2. Нажмите **кнопку** "Создать", чтобы запустить мастер Microsoft Defender для удостоверений. 

   ![Страница of_Microsoft защитника удостоверений, на которой нужно нажать кнопку "Создать"](../../media/mtp-eval-43.png)

3. Choose **Provide a username and password to connect to your Active Directory forest**.  

   ![Страница of_Microsoft защитника удостоверений](../../media/mtp-eval-44.png)

4. Введите свои учетные данные Active Directory в локальной службе. Это может быть любая учетная запись пользователя с доступом на чтение в Active Directory.

   ![Страница of_Microsoft Службы каталогов удостоверений в Защитнике удостоверений, на которой необходимо вложить учетные данные](../../media/mtp-eval-45.png)

5. Затем выберите **"Скачать установку датчика"** и передать файл на контроллер домена.

   ![Страница of_Microsoft защитника удостоверений, на которой можно выбрать "Загрузка программы установки датчика"](../../media/mtp-eval-46.png)

6. Выполните установку датчика удостоверений в Microsoft Defender и начните следовать за мастером.

   ![Страница of_Microsoft защитника удостоверений, на которой нужно щелкнуть рядом, чтобы следовать за мастером датчика identity в Microsoft Defender для удостоверений](../../media/mtp-eval-47.png)
 
7. Нажмите **кнопку** "Далее" в типе развертывания датчика.

   ![Страница of_Microsoft защитника изображений для удостоверений, на которой нужно щелкнуть рядом, чтобы перейти к следующей странице](../../media/mtp-eval-48.png)
 
8. Скопируйте ключ доступа, так как его необходимо ввести в мастере.

   ![Страница of_the датчиков изображений, на которой необходимо скопировать ключ доступа, который необходимо ввести на следующей странице мастера настройки датчиков удостоверений в Microsoft Defender для удостоверений](../../media/mtp-eval-49.png)
 
9. Скопируйте ключ доступа в мастер и нажмите кнопку **"Установить".** 

   ![Страница of_Microsoft датчика удостоверений в Защитнике изображений, на которой необходимо предоставить клавишу доступа и нажать кнопку установки](../../media/mtp-eval-50.png)

10. Поздравляем, вы успешно настроили Microsoft Defender для удостоверений на контроллере домена.

    ![Завершение of_Microsoft защитника удостоверений для датчика удостоверений, где следует нажать кнопку "Готово"](../../media/mtp-eval-51.png)
 
11. Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Microsoft Defender for Endpoint **, then turn on the toggle. Щелкните **Сохранить**. 

    ![Изображение of_the параметров Microsoft Defender для удостоверений, на которой необходимо включить выключает Microsoft Defender для конечной точки](../../media/mtp-eval-52.png)

>[!NOTE]
>Защитник Windows ATP был повторно установлен в качестве Microsoft Defender для конечной точки. Изменения, внесенные во все наши порталы, развявываются для согласованности.


## <a name="configure-microsoft-cloud-app-security"></a>Настройка Microsoft Cloud App Security

>[!NOTE]
>Пропустите этот шаг, если вы уже включили Microsoft Cloud App Security. 

1. Перейдите в [Центр безопасности Microsoft 365](https://security.microsoft.com/info)  >  **дополнительные ресурсы** Microsoft Cloud App  >  **Security.**

   ![Изображение of_Microsoft 365 Security Center, где вы можете увидеть карточку Microsoft Cloud App и нажать кнопку "Открыть"](../../media/mtp-eval-53.png)

2. В информационном запросе на интеграцию Microsoft Defender для удостоверений выберите **"Включить Microsoft Defender для интеграции данных удостоверений".**
  
   ![Запрос of_the сведений об интеграции Microsoft Defender для удостоверений, где следует выбрать ссылку "Включить Microsoft Defender для интеграции данных удостоверений"](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Если вы не видите этот запрос, это может означать, что интеграция данных в Microsoft Defender для удостоверений уже включена. Однако если вы не уверены, обратитесь к ИТ-администратору для подтверждения. 

3. Перейдите **в "Параметры",** включите выключаель интеграции с Microsoft Defender для **удостоверений** и нажмите кнопку **"Сохранить".** 

   ![Страница of_the параметров изображения, на которой необходимо включить выключаель интеграции с Microsoft Defender для удостоверений и нажать кнопку "Сохранить"](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Для новых экземпляров Microsoft Defender для удостоверений этот переключель интеграции автоматически включен. Перед тем как перейти к следующему шагу, подтвердите, что интеграция с Microsoft Defender для удостоверений включена.
 
4. В параметрах облачного обнаружения выберите Microsoft Defender для интеграции **конечных** точек, а затем в включить интеграцию. Щелкните **Сохранить**.

   ![Изображение of_the в Microsoft Defender для конечной точки, где в Microsoft Defender для интеграции конечных точек выбран блок несанкционированная проверка приложений. Нажмите кнопку "Сохранить".](../../media/mtp-eval-56.png)

5. В параметрах облачного обнаружения выберите "Обогащение пользователей", а затем в рамках интеграции с Azure Active Directory.

   ![Изображение раздела "Обогащение пользователей", в котором выбрано обогатить обнаруженные идентификаторы пользователей с помощью проверки имен пользователей Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Настройка Microsoft Defender для конечной точки

>[!NOTE]
>Пропустите этот шаг, если вы уже включили Microsoft Defender для конечной точки.

1. Перейдите в [Центр безопасности Microsoft 365.](https://security.microsoft.com/info)  >  **Дополнительные ресурсы в** Центре безопасности Microsoft  >  **Defender.** Нажмите кнопку **Open** (Открыть).

   ![Изображение of_Microsoft Центр безопасности Защитника на странице Центра безопасности Microsoft 365](../../media/mtp-eval-58.png)
 
2. Следуйте мастеру Microsoft Defender для конечной точки. Нажмите кнопку **Далее**. 

   ![Изображение of_the мастера приветствия в Центре безопасности Microsoft Defender](../../media/mtp-eval-59.png)

3. Выберите в зависимости от предпочтительного расположения хранения данных, политики хранения данных, размера организации и отказа от предварительного просмотра функций.

   ![Страница of_the для выбора страны хранения данных, политики хранения и размера организации. После выбора нажмите кнопку "Далее".](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Впоследствии вы не сможете изменить некоторые параметры, например расположение хранилища данных. 

   Нажмите кнопку **Далее**. 

4. Нажмите **кнопку** "Продолжить", и она подавит Ваш Microsoft Defender для клиента endpoint.

   ![Страница of_the с запросом нажать кнопку "Продолжить", чтобы создать облачный экземпляр](../../media/mtp-eval-61.png)

5. Подавите конечные точки с помощью групповых политик, Microsoft Endpoint Manager или с помощью локального сценария в Microsoft Defender для конечной точки. Для простоты в этом руководстве используется локальный сценарий.

6. Щелкните **"Загрузить пакет"** и скопируйте сценарий в конечные точки.

   ![Изображение of_page нажать кнопку "Загрузить пакет", чтобы скопировать сценарий в конечную точку или конечную точку](../../media/mtp-eval-62.png)

7. На конечной точке запустите сценарий под учетной записи администратора и выберите "Y". 

   ![Изображение of_the командной линии, в которой вы запустите сценарий подбора и выберите Y, чтобы продолжить](../../media/mtp-eval-63.png)

8. Поздравляем, вы вошел в свою первую конечную точку.

   ![Изображение of_the командной точки, где вы получаете подтверждение того, что вы вошел в первую конечную точку. Нажмите любую клавишу, чтобы продолжить](../../media/mtp-eval-64.png)

9. Скопируйте тест обнаружения из мастера Microsoft Defender для конечных точек.

   ![Изображение of_the выполнить тест обнаружения, где необходимо нажать кнопку "Копировать", чтобы скопировать тестовый сценарий обнаружения, который необходимо вжать в командную подсказку](../../media/mtp-eval-65.png)

10. Скопируйте сценарий PowerShell в командную команду с повышенными полномочиями и запустите его. 

    ![Изображение of_command, где следует скопировать сценарий PowerShell в командную командную команду с повышенными полномочиями и запустить его](../../media/mtp-eval-66.png)

11. Выберите **"Начать использовать Microsoft Defender для конечной точки"** в мастере.

    ![Запрос of_the подтверждения изображения из мастера, в котором следует нажать кнопку "Начать использовать Microsoft Defender для конечной точки"](../../media/mtp-eval-67.png)
 
12. Посетите Центр [безопасности Microsoft Defender.](https://securitycenter.windows.com/) Перейдите **в "Параметры"** и выберите **дополнительные функции.** 

    ![Изображение of_Microsoft меню "Параметры центра безопасности Защитника", в котором следует выбрать дополнительные функции](../../media/mtp-eval-68.png)

13. Включив интеграцию с **Microsoft Defender для удостоверений.**  

    ![Дополнительные of_Microsoft центра безопасности Защитника изображений, параметр "Защитник Майкрософт для удостоверений", который необходимо включить](../../media/mtp-eval-69.png)

14. Включив интеграцию с **Office 365 Threat Intelligence.**

    ![Дополнительные of_Microsoft Центра безопасности Защитника изображений, параметр "Аналитика угроз Office 365", который необходимо включить](../../media/mtp-eval-70.png)

15. Включит **интеграцию с Microsoft Cloud App Security.**

    ![Дополнительные of_Microsoft Центра безопасности Защитника изображений, параметр Microsoft Cloud App Security, который необходимо включить](../../media/mtp-eval-71.png)

16. Прокрутите вниз и **нажмите кнопку "Сохранить** параметры", чтобы подтвердить новые интеграции.

    ![Кнопка of_Save настройки изображения, которую необходимо нажать](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Запуск службы Microsoft 365 Defender

>[!NOTE]
>С 1 июня 2020 г. корпорация Майкрософт автоматически включает функции Защитника Microsoft 365 для всех соответствующих требованиям клиентов. Подробные сведения см. в этой статье Технического сообщества Майкрософт о [правах на лицензию.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 


Перейдите [в Центр безопасности Microsoft 365.](https://security.microsoft.com/homepage) Перейдите **в "Параметры"** и выберите **Microsoft 365 Defender.**

![Снимок of_Microsoft 365 Defender со страницы параметров Центра безопасности Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Более полное руководство см. в [подключе "Защитник Microsoft 365".](mtp-enable.md) 

Поздравляем! Вы только что создали пробную или пилотную среду Microsoft 365 Defender! Теперь вы можете ознакомиться с пользовательским интерфейсом Защитника Microsoft 365! Узнайте, что вы можете узнать из следующего интерактивного руководства По Защитнику Microsoft 365 и узнать, как использовать каждую панель мониторинга для выполнения задач по ежедневной безопасности.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Далее можно смоделировать атаку и увидеть, как возможности разных продуктов обнаруживают, создают оповещения и автоматически реагируют на атаки без файлов на конечную точку.

## <a name="next-step"></a>Следующий этап
|[Этап моделирования атаки](mtp-pilot-simulate.md) | Запустите имитацию атаки для пилотной среды Microsoft 365 Defender.
|:-------|:-----|
