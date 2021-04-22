---
title: Подключение с помощью Microsoft Endpoint Manager
description: Узнайте, как учиться в Microsoft Defender для конечной точки с помощью Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, Microsoft endpoint manager
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
ms.openlocfilehash: e744262cfd63383e69abf02be9fbf91d2d229db2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935261"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a>Подключение с помощью Microsoft Endpoint Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Эта статья является частью руководства по развертыванию и выступает в качестве примера бортового метода. 

В разделе [Планирование](deployment-strategy.md) для бортовых устройств для службы было предоставлено несколько методов. В этом разделе описывается облачная архитектура. 

![Изображение облачной архитектуры ](images/cloud-native-architecture.png)
 *Схема архитектуры среды*

Несмотря на то, что Defender для конечной точки поддерживает вовсю различные конечные точки и средства, эта статья не охватывает их. Сведения об общей онбордации с помощью других поддерживаемых средств развертывания и методов см. в [обзоре onboarding.](onboarding.md)


[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) — это платформа решений, которая объединяет несколько служб. Она включает [Microsoft Intune для](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) управления облачными устройствами.


В этом разделе данная тема направляет пользователей в:
- Шаг 1. Создание группы в Microsoft Endpoint Manager (MEM) для назначения конфигураций на службе.
- Шаг 2. Настройка функций Defender для конечных точек с помощью Microsoft Endpoint Manager

Это руководство по учету поможет вам пройти следующие основные действия, которые необходимо предпринять при использовании Microsoft Endpoint Manager:

-   [Определение целевых устройств или пользователей](#identify-target-devices-or-users)

    -   Создание группы Azure Active Directory (пользователь или устройство)

-   [Создание профиля конфигурации](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   В Microsoft Endpoint Manager мы назначим вам создание отдельной политики для каждой возможности.





## <a name="resources"></a>Ресурсы


Вот ссылки, необходимые для остальной части процесса:

-   [Портал MEM](https://aka.ms/memac)

-   [Центр безопасности](https://securitycenter.windows.com/)

-   [Базовые показатели безопасности Intune](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

Дополнительные сведения о Microsoft Endpoint Manager ознакомьтесь с этими ресурсами:
- [Страница Microsoft Endpoint Manager](https://docs.microsoft.com/mem/)
- [Сообщение в блоге о схождении Intune и ConfigMgr](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [Введение видео на MEM](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a>Шаг 1. На борту устройств путем создания группы в MEM для назначения конфигураций на
### <a name="identify-target-devices-or-users"></a>Определение целевых устройств или пользователей
В этом разделе мы создадим тестовую группу для назначения конфигураций.

>[!NOTE]
>Intune использует группы Azure Active Directory (Azure AD) для управления устройствами и пользователями. В качестве администратора Intune можно настроить группы в соответствии с вашими организационными потребностями.<br>
Дополнительные сведения см. в [добавлении групп для организации пользователей и устройств.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)

### <a name="create-a-group"></a>Создание группы

1.  Откройте портал MEM.

2.  Open **Groups > New Group**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager1](images/66f724598d9c3319cba27f79dd4617a4.png)

3.  Введите сведения и создайте новую группу.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager2](images/b1e0206d675ad07db218b63cd9b9abc3.png)

4.  Добавьте тестовый пользователь или устройство.

5.  Откройте новую **группу из > групп.**

6.  Выберите  **члены > добавить членов**.

7.  Найдите тестовый пользователь или устройство и выберите его.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager3](images/149cbfdf221cdbde8159d0ab72644cd0.png)

8.  Теперь в группе тестирования есть член, который необходимо протестировать.

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a>Шаг 2. Создание политик конфигурации для настройки возможностей Microsoft Defender для конечных точек
В следующем разделе будет создаваться ряд политик конфигурации.

Во-первых, это политика конфигурации, чтобы выбрать, какие группы пользователей или устройств будут на борту в Defender для конечной точки:

- [Обнаружение и устранение угроз на конечных точках](#endpoint-detection-and-response) 

Затем вы продолжите создание нескольких различных типов политик безопасности конечных точек:

- [Защита нового поколения](#next-generation-protection)
- [Сокращение направлений атак](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a>Обнаружение и устранение угроз на конечных точках

1.  Откройте портал MEM.

2.  Перейдите к **службе безопасности > endpoint detection and response**. Нажмите **кнопку Создать профиль**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager4](images/58dcd48811147feb4ddc17212b7fe840.png)

3.  В **платформе выберите Windows 10 и более поздние версии Profile - Endpoint detection and response > Create**.

4.  Введите имя и описание, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)

5.  Выберите параметры по мере необходимости, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager6](images/cea7e288b5d42a9baf1aef0754ade910.png)

    > [!NOTE]
    > В этом примере это было автоматически заполнено, так как Defender для конечной точки уже интегрирован с Intune. Дополнительные сведения об интеграции см. в дополнительных сведениях [включить Microsoft Defender для конечной точки в Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)
    > 
    > Ниже приводится пример того, что вы увидите, когда Microsoft Defender для конечной точки не интегрирована с Intune:
    >
    > ![Изображение портала Microsoft Endpoint Manager7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  При необходимости добавьте теги области, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager8](images/ef844f52ec2c0d737ce793f68b5e8408.png)

7.  Добавьте тестовую группу, нажав на **Выберите группы,** чтобы включить и выбрать группу, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager9](images/fc3525e20752da026ec9f46ab4fec64f.png)

8.  Просмотрите и примите, а затем выберите  **Create**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager10](images/289172dbd7bd34d55d24810d9d4d8158.png)

9.  Вы можете просмотреть завершенную политику.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager11](images/5a568b6878be8243ea2b9d82d41ed297.png)

### <a name="next-generation-protection"></a>Защита нового поколения

1.  Откройте портал MEM.

2.  Перейдите в **конечную > антивирусную > создать политику**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager12](images/6b728d6e0d71108d768e368b416ff8ba.png)

3.  Выберите **платформу — Windows 10 и более поздние версии — Windows и Profile — антивирус Microsoft Defender > Create**.

4.  Введите имя и описание, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager13](images/a7d738dd4509d65407b7d12beaa3e917.png)

5.  На странице **Параметры** конфигурации : Установите конфигурации, необходимые для антивируса Microsoft Defender (облачная защита, исключения, Real-Time защита и исправление).

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)

6.  При необходимости добавьте теги области, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager15](images/2055e4f9b9141525c0eb681e7ba19381.png)

7.  Выберите группы, которые необходимо включить, назначьте тестовой группе, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager16](images/48318a51adee06bff3908e8ad4944dc9.png)

8.  Просмотрите и создайте, а затем выберите  **Create**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager17](images/dfdadab79112d61bd3693d957084b0ec.png)

9.  Вы увидите созданную политику конфигурации.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager18](images/38180219e632d6e4ec7bd25a46398da8.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Уменьшение поверхности атаки — правила уменьшения поверхности атаки

1.  Откройте портал MEM.

2.  Перейдите к **области безопасности конечных точек > для уменьшения поверхности Attack.**

3.  Выберите  **создать политику**.

4.  Выберите **платформу — Windows 10 и более поздние — Правила** уменьшения поверхности атаки > Создать .

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager19](images/522d9bb4288dc9c1a957392b51384fdd.png)

5.  Введите имя и описание, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)

6.  На странице **Параметры конфигурации:** Установите конфигурации, необходимые для правил уменьшения поверхности Атаки, а затем выберите  **Далее**.

    > [!NOTE]
    > Мы настроим все правила снижения поверхности атаки на аудит.
    > 
    > Дополнительные сведения см. в [правилах уменьшения поверхности Attack.](attack-surface-reduction.md)

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager21](images/dd0c00efe615a64a4a368f54257777d0.png)

7.  Добавьте теги области по мере необходимости, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Выберите группы, включив и назначив группе тестирования, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager23](images/45cefc8e4e474321b4d47b4626346597.png)

9. Просмотрите сведения, а затем выберите  **Создать**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)

10. Просмотр политики.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager25](images/7a631d17cc42500dacad4e995823ffef.png)

### <a name="attack-surface-reduction--web-protection"></a>Уменьшение поверхности атаки — веб-защита

1.  Откройте портал MEM.

2.  Перейдите к **области безопасности конечных точек > для уменьшения поверхности Attack.**

3.  Выберите  **создать политику**.

4.  Выберите **Windows 10 и более поздние версии — веб> создать**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)

5.  Введите имя и описание, а затем выберите  **Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager27](images/5be573a60cd4fa56a86a6668b62dd808.png)

6.  На странице **Параметры конфигурации**: Установите конфигурации, необходимые для веб-защиты, а затем выберите  **Далее**.

    > [!NOTE]
    > Мы настраиваем веб-защиту для блокировки.
    > 
    > Дополнительные сведения см. в [веб-защите.](web-protection-overview.md)

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager28](images/6104aa33a56fab750cf30ecabef9f5b6.png)

7.  Добавьте теги области по мере **необходимости > Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)

8.  Выберите **Назначение для тестирования группы > Далее**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager30](images/45cefc8e4e474321b4d47b4626346597.png)

9.  Выберите **обзор и создайте > создать**.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)

10. Просмотр политики.

    > [!div class="mx-imgBorder"]
    > ![Изображение портала Microsoft Endpoint Manager32](images/e74f6f6c150d017a286e6ed3dffb7757.png)

## <a name="validate-configuration-settings"></a>Проверка параметров конфигурации


### <a name="confirm-policies-have-been-applied"></a>Подтверждение примененных политик


После того, как политика конфигурации назначена, на ее применение уйма времени займет некоторое время.

Сведения о сроках см. в [сведениях о конфигурации Intune.](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)

Чтобы подтвердить, что политика конфигурации применена к тестовом устройству, выполните следующий процесс для каждой политики конфигурации.

1.  Откройте портал MEM и перейдите к соответствующей политике, как показано на шагах выше. В следующем примере показаны параметры защиты следующего поколения.

    > [!div class="mx-imgBorder"]
    > [![Изображение портала Microsoft Endpoint Manager33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)

2.  Выберите политику **конфигурации,** чтобы просмотреть состояние политики.

    > [!div class="mx-imgBorder"]
    > [![Изображение портала Microsoft Endpoint Manager34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)

3.  Чтобы  **увидеть состояние,** выберите состояние устройства.

    > [!div class="mx-imgBorder"]
    > [![Изображение портала Microsoft Endpoint Manager35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)

4.  Чтобы  **увидеть** состояние, выберите состояние пользователя.

    > [!div class="mx-imgBorder"]
    > [![Изображение портала Microsoft Endpoint Manager36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)

5.  Выберите  **состояние per-setting,** чтобы увидеть состояние.

    >[!TIP]
    >Это представление очень полезно для определения параметров, которые конфликтуют с другой политикой.

    > [!div class="mx-imgBorder"]
    > [![Изображение портала Microsoft Endpoint Manager37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)

### <a name="endpoint-detection-and-response"></a>Обнаружение и устранение угроз на конечных точках


1.  Перед применением конфигурации не следует задействовать службу защиты конечных точек Defender для конечной точки.

    > [!div class="mx-imgBorder"]
    > [![Изображение панели Services1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)

2.  После того, как конфигурация будет применена, следует начать работу службы защиты конечных точек Defender для конечных точек.

    > [!div class="mx-imgBorder"]
    > [![Изображение панели Services2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)

3.  После запуска служб на устройстве устройство отображается в центре безопасности Microsoft Defender.

    > [!div class="mx-imgBorder"]
    > [![Изображение Центра безопасности Защитника Майкрософт ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)

### <a name="next-generation-protection"></a>Защита нового поколения

1.  Прежде чем применять политику на тестовом устройстве, вы должны иметь возможность вручную управлять настройками, как показано ниже.

    > [!div class="mx-imgBorder"]
    > ![Изображение параметра page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)

2.  После того, как политика будет применена, вы не сможете вручную управлять настройками.

    > [!NOTE]
    > На следующем изображении **включаем облачную защиту** и включаем защиту в режиме реального времени. 

    > [!div class="mx-imgBorder"]
    > ![Изображение параметра page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a>Уменьшение поверхности атаки — правила уменьшения поверхности атаки


1.  Перед тем как применить политику на тестовом устройстве, введите окно PowerShell и введите `Get-MpPreference` .

2.  Это должно отвечать следующими строками без контента:

    > AttackSurfaceReductionOnlyExclusions:
    > 
    > AttackSurfaceReductionRules_Actions:
    > 
    > AttackSurfaceReductionRules_Ids:

    ![Изображение командной строки1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  После применения политики на тестовом устройстве откройте Windows PowerShell и введите `Get-MpPreference` .

4.  Это должно отвечать следующими строками содержимым, как показано ниже:

    ![Изображение командной строки2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a>Уменьшение поверхности атаки — веб-защита

1.  На тестовом устройстве откройте Windows PowerShell и введите `(Get-MpPreference).EnableNetworkProtection` .

2.  Это должно отвечать с 0, как показано ниже.

    ![Изображение командной строки3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  После применения политики откройте Windows PowerShell и введите `(Get-MpPreference).EnableNetworkProtection` .

4.  Это должно отвечать с 1, как показано ниже.

    ![Изображение командной строки4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
