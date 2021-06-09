---
title: Подключение с помощью Microsoft Endpoint Configuration Manager
description: Узнайте, как в Microsoft Defender для конечной точки использовать Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, Microsoft endpoint configuration manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843510"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Подключение с помощью Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Эта статья является частью руководства по развертыванию и выступает в качестве примера бортового метода. 

В разделе [Планирование](deployment-strategy.md) для бортовых устройств для службы было предоставлено несколько методов. В этом разделе описывается архитектура совместного управления. 

![Изображение облачной архитектуры ](images/co-management-architecture.png)
 *Схема архитектуры среды*


Несмотря на то, что Defender для конечной точки поддерживает вовсю различные конечные точки и средства, эта статья не охватывает их. Сведения об общей онбордации с помощью других поддерживаемых средств развертывания и методов см. в [обзоре onboarding.](onboarding.md)



В этом разделе данная тема направляет пользователей в:
- Шаг 1: Windows устройств в службу 
- Шаг 2. Настройка функций Defender для конечных точек

Это руководство по введению поможет вам пройти следующие основные действия, которые необходимо предпринять при использовании Microsoft Endpoint Configuration Manager:
- **Создание коллекции в Microsoft Endpoint Configuration Manager**
- **Настройка возможностей Microsoft Defender для конечных точек с помощью Microsoft Endpoint Configuration Manager**

>[!NOTE]
>В этом примере Windows только устройства. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Шаг 1. Бортовые Windows устройства с Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Создание коллекции
Для Windows 10 устройств с Microsoft Endpoint Configuration Manager развертывание может быть ориентировано на существующую коллекцию или может быть создана новая коллекция для тестирования. 

При использовании таких средств, как групповой политики или ручного метода, в системе не устанавливается агент. 

В консоли Microsoft Endpoint Configuration Manager процесс вставки будет настраиваться как часть параметров соответствия требованиям в консоли.

Любая система, которая получает эту необходимую конфигурацию, будет поддерживать эту конфигурацию до тех пор, пока клиент Configuration Manager продолжает получать эту политику из точки управления. 

Следуйте ниже шагам к конечным точкам на борту с Microsoft Endpoint Configuration Manager.

1. В Microsoft Endpoint Configuration Manager консоли перейдите к **коллекциям устройств Assets и \> Compliance Overview Device \> Collections.**            

    ![Изображение мастера Microsoft Endpoint Configuration Manager 1](images/configmgr-device-collections.png)

2. Щелкните **правой кнопкой мыши коллекцию устройств** и выберите Создать **коллекцию устройств.**

    ![Изображение мастера Microsoft Endpoint Configuration Manager 2](images/configmgr-create-device-collection.png)

3. Предоставление имени **и** **ограничение коллекции**, а затем выберите **Далее**.

    ![Изображение Microsoft Endpoint Configuration Manager wizard3](images/configmgr-limiting-collection.png)

4. Выберите **правило Добавить** и выберите правило **запроса**.

    ![Изображение мастера Microsoft Endpoint Configuration Manager 4](images/configmgr-query-rule.png)

5.  Нажмите **кнопку Далее** по **мастеру прямого членства** и нажмите кнопку **Изменить заявление запроса**.

     ![Изображение Microsoft Endpoint Configuration Manager wizard5](images/configmgr-direct-membership.png)

6. Выберите **Критерии** и выберите значок звезды.

     ![Изображение Microsoft Endpoint Configuration Manager wizard6](images/configmgr-criteria.png)

7. Сохраняйте тип критерия как простое **значение,**  выберите, где в качестве операционной системы **—** номер сборки, оператор больше или равен и значение **14393** и нажмите кнопку **ОК**.

    ![Изображение Microsoft Endpoint Configuration Manager wizard7](images/configmgr-simple-value.png)

8. Выберите **Далее** и **закрой**.

    ![Изображение Microsoft Endpoint Configuration Manager wizard8](images/configmgr-membership-rules.png)

9. Нажмите кнопку **Далее**.

    ![Изображение мастера Microsoft Endpoint Configuration Manager 9](images/configmgr-confirm.png)


После выполнения этой задачи у вас теперь есть коллекция устройств со всеми конечными точками Windows 10 в среде. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Шаг 2. Настройка microsoft Defender для возможностей конечных точек 
В этом разделе приводится руководство по настройке следующих возможностей с помощью Microsoft Endpoint Configuration Manager на Windows устройствах:

- [**Обнаружение и устранение угроз на конечных точках**](#endpoint-detection-and-response)
- [**Защита нового поколения**](#next-generation-protection)
- [**Сокращение направлений атак**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>Обнаружение и устранение угроз на конечных точках
#### <a name="windows-10"></a>Windows 10
Из Центр безопасности в Microsoft Defender можно скачать политику ".onboarding", которую можно использовать для создания политики в System Center Configuration Manager и развернуть эту политику для Windows 10 устройств.

1. На портале Центр безопасности в Microsoft Defender выберите [Параметры, а затем на борту.](https://securitycenter.windows.com/preferences2/onboarding)



2. В методе Развертывания выберите поддерживаемую версию **Microsoft Endpoint Configuration Manager.**

    ![Изображение мастера бортовой точки Microsoft Defender для конечной точки10](images/mdatp-onboarding-wizard.png)

3. Выберите **пакет Загрузка**.

    ![Изображение мастера бортовой точки Microsoft Defender для конечной точки11](images/mdatp-download-package.png)

4. Сохраните пакет в доступном расположении.
5. В Microsoft Endpoint Configuration Manager перейдите к: **Assets and Compliance > Обзор > Endpoint Protection > ATP в Защитнике Microsoft политики**.

6. Щелкните **правой кнопкой мыши ATP в Защитнике Microsoft политики** и выберите **Create ATP в Защитнике Microsoft Policy**.

    ![Изображение мастера Microsoft Endpoint Configuration Manager 12](images/configmgr-create-policy.png)

7. Введите имя и описание, убедитесь, что выбрана **onboarding,** а затем выберите **Далее**.

    ![Изображение Microsoft Endpoint Configuration Manager wizard13](images/configmgr-policy-name.png)


8. Нажмите кнопку **Обзор**.

9. Перейдите к расположению скачаного файла на шаге 4 выше.

10. Нажмите **Далее**.
11. Настройка агента с соответствующими примерами **(None** or **All file types).**

    ![Изображение параметров конфигурации1](images/configmgr-config-settings.png)

12. Выберите соответствующую телеметрию **(обычная или** **ускоренная),** а затем нажмите **кнопку Далее**.

    ![Изображение параметров конфигурации2](images/configmgr-telemetry.png)

14. Проверьте конфигурацию, а затем нажмите **кнопку Далее**.

     ![Изображение параметров конфигурации3](images/configmgr-verify-configuration.png)

15. Нажмите **кнопку Закрыть,** когда мастер завершится.

16.  В консоли Microsoft Endpoint Configuration Manager нажмите правой кнопкой мыши политику Defender для конечных точек, созданную только что, и выберите **Развертывание.**

     ![Изображение параметров конфигурации4](images/configmgr-deploy.png)

17. На правой панели выберите ранее созданную коллекцию и нажмите **кнопку ОК**.

    ![Изображение параметров конфигурации5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Предыдущие версии Windows (Windows 7 и Windows 8.1)
Следуйте ниже шагам, чтобы определить ID и ключ рабочего пространства Defender для конечного пространства, которые потребуются для вовсю предыдущих версий Windows.

1. На портале Центр безопасности в Microsoft Defender выберите Параметры > **onboarding**.

2. В операционной системе **выберите Windows 7 SP1 и 8.1**.

3. **Скопируйте ID рабочего пространства и** **клавишу Рабочей области и** сохраните их. Они будут использоваться позже в процессе.

    ![Изображение бортового](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Установка Microsoft Monitoring Agent (MMA). <br>
    MMA в настоящее время (по данным на январь 2019 г.) поддерживается в следующих Windows операционных системах:

    -   Сервер SKUs: Windows Server 2008 SP1 или Newer

    -   Клиентские СКУ: Windows 7 SP1 и более поздний

    Агент MMA должен быть установлен на Windows устройствах. Чтобы установить агента, некоторым системам [](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) необходимо скачать обновление для работы с клиентами и диагностическую телеметрию для сбора данных с помощью MMA. Эти системные версии включают, но не могут ограничиваться:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    В частности, для Windows 7 SP1 необходимо установить следующие исправления:

    -   Установка [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Установите платформа .NET Framework [4.5](https://www.microsoft.com/download/details.aspx?id=30653) (или более **поздней)** или 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).
        Не устанавливайте обе системы в одной и той же системе.

5. Если вы используете прокси для подключения к Интернету, см. раздел Настройка параметров прокси.

После завершения работы в течение часа на портале должны быть понастройки конечных точек.

### <a name="next-generation-protection"></a>Защита нового поколения 
Антивирусная программа в Microsoft Defender — это встроенное антивредоносное решение, которое предоставляет защиту нового поколения для настольных компьютеров, портативных компьютеров и серверов.

1. В консоли Microsoft Endpoint Configuration Manager перейдите к обзору активов и соответствия требованиям Endpoint Protection **\> \> \> антивирусных** политик и выберите Создать политику по борьбе с **антивирусами.**

    ![Изображение политики противомалярийных программ](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Выберите запланированные проверки, параметры сканирования, действия по умолчанию, защита в режиме реального **времени,** параметры исключения, расширенные, переопределения угрозы, облачные службы защиты и обновления аналитики безопасности и выберите **ОК**.        

    ![Изображение области защиты следующего поколения1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    В определенных отраслях или некоторых отдельных корпоративных клиентах могут возникнуть определенные потребности в настройке антивируса.

  
    [Быстрое сканирование по сравнению с полным сканированием и пользовательским сканированием](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Дополнительные сведения см. [в Безопасность Windows конфигурации](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Изображение области защиты следующего поколения2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Изображение области защиты следующего поколения3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Изображение области защиты следующего поколения4](images/a28afc02c1940d5220b233640364970c.png)

    ![Изображение области защиты следующего поколения5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Изображение области защиты следующего поколения6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Изображение области защиты следующего поколения7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Изображение области защиты следующего поколения8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Изображение области защиты следующего поколения9](images/3876ca687391bfc0ce215d221c683970.png)

3. Щелкните правой кнопкой мыши по недавно созданной политике антивирусного обеспечения и выберите **Развертывание.**

    ![Изображение области защиты следующего поколения10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Найдите новую политику противомалярийных программ для Windows 10 и нажмите **кнопку ОК.**

     ![Изображение области защиты следующего поколения11](images/configmgr-select-collection.png)

После выполнения этой задачи вы успешно настроили антивирусная программа .

### <a name="attack-surface-reduction"></a>Сокращение направлений атак
Столб сокращения поверхности атаки Defender для конечной точки включает набор функций, доступный в статье Exploit Guard. Правила уменьшения поверхности атаки, управляемый доступ к папкам, защита сети и защита от эксплойтов. 

Все эти функции обеспечивают режим аудита и режим блокировки. В режиме аудита не влияет на конечных пользователей. Все, что он делает, это собирает дополнительную телеметрию и делает ее доступной в Центр безопасности в Microsoft Defender. Цель развертывания — пошаговые перемещения элементов управления безопасностью в режим блокировки.

Чтобы установить правила ASR в режиме аудита:

1. В консоли Microsoft Endpoint Configuration Manager перейдите к обзору активов и соответствия требованиям Endpoint Protection **\> Защитник Windows Exploit \> \> Guard** и выберите Политику защиты от **эксплойтов**.

   ![Изображение Microsoft Endpoint Configuration Manager console0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Выберите **уменьшение поверхности атаки.**
   

3. Установите правила **аудита и** нажмите **кнопку Далее**.


    ![Изображение консоли Microsoft Endpoint Configuration Manager 1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Подтвердит новую политику Exploit Guard, нажав кнопку **Далее**.

    ![Изображение консоли Microsoft Endpoint Configuration Manager 2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. После создания политики нажмите кнопку **Закрыть**.

    ![Изображение консоли Microsoft Endpoint Configuration Manager 3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Изображение консоли Microsoft Endpoint Manager 1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Щелкните правой кнопкой мыши по вновь созданной политике и выберите **Развертывание.**
    
    ![Изображение Microsoft Endpoint Configuration Manager console4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Нацелить политику на недавно созданную коллекцию Windows 10 и нажмите **кнопку ОК**.

    ![Изображение консоли Microsoft Endpoint Configuration Manager 5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

После выполнения этой задачи вы успешно настроили правила ASR в режиме аудита.  
  
Ниже приведены дополнительные действия, чтобы убедиться, правильно ли правила ASR применяются к конечным точкам. (Это может занять несколько минут)


1. Из веб-браузера перейдите на <https://securitycenter.windows.com> .

2.  Выберите **управление конфигурацией** из левого бокового меню.

3. Нажмите **кнопку Перейти к управлению поверхностью** атаки в панели управления поверхностью атаки. 
    
    ![Изображение управления поверхностью атаки](images/security-center-attack-surface-mgnt-tile.png)

4. Щелкните **вкладку Configuration** в отчетах о снижении поверхности атаки. В нем показан обзор конфигурации правил ASR и состояние правил ASR на каждом устройстве.

    ![Скриншот отчетов о правилах уменьшения поверхности атаки1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Щелкните каждое устройство, отображающее сведения о конфигурации правил ASR.

    ![Снимок экрана отчетов о снижении поверхности атаки2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Дополнительные сведения см. в материале Оптимизируйте развертывание и обнаружение правил [ASR.](/microsoft-365/security/defender-endpoint/configure-machines-asr)  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Установите правила защиты сети в режиме аудита:
1. В консоли Microsoft Endpoint Configuration Manager перейдите к обзору активов и соответствия требованиям Endpoint Protection **\> Защитник Windows Exploit \> \> Guard** и выберите Политику защиты от **эксплойтов**.

    ![Снимок экрана System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Выберите **защиту сети.**

3. Установите параметр Аудит **и нажмите** кнопку **Далее**. 

    ![Снимок экрана System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Подтвердит новую политику защиты эксплойтов, нажав **кнопку Далее**.
    
    ![Снимок экрана Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. После создания политики нажмите кнопку **Закрыть**.

    ![Снимок экрана Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Щелкните правой кнопкой мыши по вновь созданной политике и выберите **Развертывание.**

    ![Снимок экрана Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Выберите политику в недавно созданной Windows 10 и выберите **ОК.**

    ![Снимок экрана Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



После выполнения этой задачи успешно настроена защита сети в режиме аудита.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>Настройка правил доступа к управляемым папкам в режиме аудита:

1. В консоли Microsoft Endpoint Configuration Manager перейдите к обзору активов и соответствия требованиям Endpoint Protection **\> Защитник Windows Exploit \> \> Guard** и выберите Политику защиты от **эксплойтов**.

    ![Снимок экрана Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Выберите **управляемый доступ к папке.**
    
3. Установите конфигурацию для **аудита и** нажмите **кнопку Далее**.

    ![Снимок экрана microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Подтвердит новую политику защиты эксплойтов, нажав кнопку **Далее**.

    ![Снимок экрана Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. После создания политики нажмите кнопку **Закрыть**.

    ![Снимок экрана microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Щелкните правой кнопкой мыши по вновь созданной политике и выберите **Развертывание.**

    ![Снимок экрана Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Нацелить политику на недавно созданную коллекцию Windows 10 и нажмите **кнопку ОК**.

    ![Снимок экрана Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Теперь вы успешно настраивали управляемый доступ к папкам в режиме аудита.

## <a name="related-topic"></a>Связанная тема
- [Подключение с помощью Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
