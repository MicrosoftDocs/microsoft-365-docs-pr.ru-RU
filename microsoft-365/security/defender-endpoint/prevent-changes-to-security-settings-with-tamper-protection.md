---
title: Защита параметров безопасности с помощью защиты от подделки
ms.reviewer: shwjha, hayhov
manager: dansimp
description: Используйте защиту от взлома, чтобы предотвратить изменение важных параметров безопасности вредоносными приложениями.
keywords: вредоносные программы, защитник, антивирус, защита от взлома
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 05/17/2021
ms.openlocfilehash: ed9eb425d718a2dbdaa2cdb3ab1e6899c9870124
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538895"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Защита параметров безопасности с помощью защиты от подделки

**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Защита от взлома доступна для устройств, которые запускают одну из следующих версий Windows:

- Windows 10
- Windows Server 2019
- Windows Сервер, версия 1803 или более поздней версии
- Windows Server 2016

## <a name="overview"></a>Обзор

Во время некоторых видов кибератак злоумышленники пытаются отключить функции безопасности, такие как антивирусная защита, на компьютерах. Злоумышленникам нравится отключать функции безопасности, чтобы упростить доступ к данным, установить вредоносные программы или иным образом использовать данные, удостоверения и устройства. Защита от взлома помогает предотвратить подобные вещи.

С защитой от взлома вредоносные приложения не могут принимать такие действия, как:

- Отключение защиты от вирусов и угроз
- Отключение защиты в режиме реального времени
- Отключение мониторинга поведения
- Отключение антивируса (например, IOfficeAntivirus (IOAV))
- Отключение облачной защиты
- Удаление обновлений разведки безопасности

### <a name="how-it-works"></a>Принципы работы

Защита от взлома по сути блокирует антивирусная программа в Microsoft Defender и предотвращает изменения параметров безопасности с помощью приложений и методов, таких как:

- Настройка параметров в редакторе реестра на Windows устройстве
- Изменение параметров с помощью cmdlets PowerShell
- Редактирование или удаление параметров безопасности с помощью групповых политик

Защита от взлома не мешает вам просматривать параметры безопасности. Защита от взлома не влияет на регистрацию сторонних антивирусных приложений с Безопасность Windows приложением. Если ваша организация использует Windows 10 Корпоративная E5, отдельные пользователи не могут изменить параметр защиты от взлома; в этих случаях защита от взлома управляется вашей командой безопасности.

### <a name="what-do-you-want-to-do"></a>Что нужно сделать

| Для выполнения этой задачи... | См. в этом разделе... |
|:---|:---|
| Управление защитой от взлома в клиенте <p>Используйте Центр безопасности в Microsoft Defender, чтобы включить или отключить защиту от взлома | [Управление защитой от взлома для организации с помощью Центр безопасности в Microsoft Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| Настройка параметров защиты от взлома в организации <p>Используйте Intune (Microsoft Endpoint Manager) для отключения защиты от взлома. С помощью этого метода можно настроить защиту от взлома для некоторых или всех пользователей. | [Управление защитой от взлома для организации с помощью Intune](#manage-tamper-protection-for-your-organization-using-intune) |
| Включите защиту от взлома (или отключение) для организации с помощью диспетчера конфигурации | [Управление защитой от взлома для организации с помощью присоединений клиента к Configuration Manager версии 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| Включите защиту от взлома (или выключение) для отдельного устройства | [Управление защитой от взлома на отдельном устройстве](#manage-tamper-protection-on-an-individual-device) |
| Просмотр сведений о попытках фальсификации на устройствах | [Просмотр сведений о попытках фальсификации](#view-information-about-tampering-attempts) |
| Просмотрите рекомендации по безопасности | [Обзор рекомендаций по безопасности](#review-your-security-recommendations) |
| Просмотрите список часто задаваемого вопроса (часто задаваемой вопросы) | [Просмотр задаваемой темы](#view-information-about-tampering-attempts) |

В зависимости от метода или средства управления, используемого для обеспечения защиты Tamper, может возникнуть зависимость от MAPS (облачной защиты). 

В следующей таблице приводится подробная информация о методах, средствах и зависимостях.

| Как включена защита tamper  | Зависимость от MAPS (облачная защита)    |
|:----|:----|
| Microsoft Intune  | Нет |
| Microsoft Endpoint Configuration Manager + Присоединение клиента  |     Нет  |
| Центр безопасности в Microsoft Defender ( [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) )    |     Да |
| Microsoft 365 центра безопасности ( [https://security.microsoft.com](https://security.microsoft.com) )  |     Да  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>Управление защитой от взлома для организации с помощью Центр безопасности в Microsoft Defender

Защита от взлома может быть включена или отключена для клиента с помощью Центр безопасности в Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). Вот несколько моментов, которые необходимо иметь в виду:

- В настоящее время для новых развертывания по умолчанию Центр безопасности в Microsoft Defender для управления защитой от Центр безопасности в Microsoft Defender. В существующих развертываниях защита от взлома доступна на основе выбора, и в ближайшее время планируется сделать выбор в методе по умолчанию. (Чтобы выбрать в Центр безопасности в Microsoft Defender, выберите **Параметры**  >  **Расширенные функции**  >  **Защита tamper**.) 

- При использовании Центр безопасности в Microsoft Defender защиты от взлома не нужно использовать метод Intune или присоединение клиента.

- При управлении защитой от Центр безопасности в Microsoft Defender в Центр безопасности в Microsoft Defender параметр применяется широкий клиент, затрагивающий все устройства, работающие Windows 10, Windows Server 2016 или Windows Server 2019. Чтобы настроить защиту от взлома (например, на некоторых устройствах есть защита от взлома, но отключена для других), используйте [intune](#manage-tamper-protection-for-your-organization-using-intune) или Configuration Manager с присоединением [клиента.](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)

- Если у вас гибридная среда, параметры защиты от взлома, настроенные в Intune, имеют приоритет над настройками, настроенными в Центр безопасности в Microsoft Defender. 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>Требования к управлению защитой от взлома в Центр безопасности в Microsoft Defender

- Вы должны иметь соответствующие [разрешения,](/microsoft-365/security/defender-endpoint/assign-portal-access)такие как глобальный администратор, администратор безопасности или операции безопасности.

- На Windows устройствах должна быть запущена одна из следующих версий Windows:
   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Сервер, версия [1803 или](/windows/release-health/status-windows-10-1803) более поздней версии
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - Дополнительные сведения о выпусках см. в [Windows 10 сведения о выпуске.](/windows/release-health/release-information)

- Ваши устройства должны быть на борту в [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/onboarding).

- Устройства должны использовать платформу для антивирусных программ версии 4.18.2010.7 (или выше) и версию 1.1.17600.5 (или выше). ([Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md).)

- [Необходимо включить](enable-cloud-protection-microsoft-defender-antivirus.md) облачную защиту.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>Включите защиту от взлома (или выключение) в Центр безопасности в Microsoft Defender 

![Включив защиту от взлома в Центр безопасности в Microsoft Defender](images/mde-turn-tamperprotect-on.png)

1. Перейдите в Центр безопасности в Microsoft Defender [https://securitycenter.windows.com](https://securitycenter.windows.com) () и войдите.

2. Выберите **Параметры**.

3. Перейдите **к функциям General**  >  **Advanced** и включи защиту от взлома.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Управление защитой от взлома для организации с помощью Intune

Если вы входите в группу безопасности организации, а ваша подписка включает [Intune,](/intune/fundamentals/what-is-intune)вы можете включить (или отключить) защиту от взлома для организации в центре администрирования Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ). Используйте Intune для настройки параметров защиты от взлома. Например, если вы хотите включить защиту от взлома на некоторых устройствах, но не на всех, используйте Intune.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Требования к управлению защитой от взлома в Intune

- Вы должны иметь соответствующие [разрешения,](/microsoft-365/security/defender-endpoint/assign-portal-access)такие как глобальный администратор, администратор безопасности или операции безопасности.

- Ваша организация использует [Intune для управления устройствами.](/intune/fundamentals/what-is-device-management) ([Требуются лицензии intune;](/intune/fundamentals/licenses) Intune входит в Microsoft 365 E5.)

- Ваши Windows устройства должны работать Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) или более поздней. (Дополнительные сведения о выпусках см. в Windows 10 [сведения о выпуске.)](/windows/release-health/release-information)

- Необходимо использовать Windows с помощью [](https://www.microsoft.com/wdsi/definitions) сведений о безопасности, обновленных до версии 1.287.60.0 (или выше).

- Устройства должны использовать платформу для антивирусных программ версии 4.18.1906.3 (или выше) и версию 1.1.15500.X (или выше). ([Управление антивирусная программа в Microsoft Defender обновлениями и применение базовых показателей](manage-updates-baselines-microsoft-defender-antivirus.md).)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Включите защиту от взлома (или отключение) в Intune

![Включить защиту от взлома с помощью Intune](images/turnontamperprotect-MEM.png)

1. Перейдите в [центр администрирования Microsoft Endpoint Manager](https://endpoint.microsoft.com) и войдите в свою работу или учетную запись учебного заведения.

2. Выберите   >  **профили конфигурации устройств.**

3. Создайте профиль, который включает следующие параметры:
    - **Платформа: Windows 10 и более поздней**
    - **Тип профиля: защита конечной точки**
    - **Категория: Центр безопасности в Microsoft Defender**
    - **Защита от взлома: включена**

4. Назначьте профиль одной или несколько групп.

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a>Используете ли вы Windows OS 1709, 1803 или 1809?

Если вы используете Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803)или [1809,](/windows/release-health/status-windows-10-1809-and-windows-server-2019)вы не увидите защиту **tamper** в Безопасность Windows приложении. Вместо этого с помощью PowerShell можно определить, включена ли защита от взлома.

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a>Используйте PowerShell, чтобы определить, включена ли защита от взлома

1. Откройте приложение Windows PowerShell.

2. Используйте [комлет Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell.

3. В списке результатов и посмотрите `IsTamperProtected` . (Значение true *означает,* что включена защита от взлома.)

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Управление защитой от взлома для организации с помощью Configuration Manager, версия 2006

Если вы используете версию [2006](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)configuration Manager, вы можете управлять настройками защиты от взлома на Windows 10, Windows Server 2016 и Windows Server 2019 с помощью метода, называемого присоединением клиента *.* Присоединение к клиенту позволяет синхронизировать локальное устройство Configuration Manager в центр администрирования Microsoft Endpoint Manager, а затем доставить политики конфигурации конечных точек в локальное & устройства.

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Безопасность Windows в Endpoint Manager":::

> [!NOTE]
> Процедура может быть использована для расширения защиты от взлома на устройства, работающие Windows 10 и Windows Server 2019. Обязательно просмотрите необходимые условия и другие сведения в ресурсах, указанных в этой процедуре.

1. Настройка присоединений клиента. Подробнее см. в Microsoft Endpoint Manager [присоединении клиента: синхронизация](/mem/configmgr/tenant-attach/device-sync-actions)устройств и действия устройства.

2. В центре [администрирования Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)перейти к **антивирусу безопасности Endpoint,** а затем  >  выбрать + **Создать политику**.<br/> 
   - В **списке Платформы** выберите **Windows 10 и Windows Server (ConfigMgr).**  
   - В **списке Профилей** **выберите Безопасность Windows (предварительный просмотр).** <br/>

3. Развертывание политики в коллекции устройств.

### <a name="need-help-with-this-method"></a>Нужна помощь с этим методом? 

См. следующие ресурсы:

- [Параметры для профиля Безопасность Windows в Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Блог Community технологий: объявление о защите от взлома для клиентов-клиентов клиента configuration Manager Tenant Attach](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Управление защитой от взлома на отдельном устройстве

> [!NOTE]
> Блоки защиты tamper блокируют попытки антивирусная программа в Microsoft Defender параметров через реестр.
>
> Чтобы защита от взлома не мешала сторонним продуктам безопасности или корпоративным сценариям  установки, которые изменяют  эти параметры, перейдите к Безопасность Windows и обновив сведения о безопасности до версии 1.287.60.0 или более поздней версии. [(См. обновления разведки безопасности.)](https://www.microsoft.com/wdsi/definitions)
>
> После этого обновления защита от взлома продолжает защищать параметры реестра, и журналы пытаются изменить их, не возвращая ошибок.

Если вы домашний пользователь или не подвержены настройкам, управляемым командой безопасности, вы можете использовать приложение Безопасность Windows для управления защитой от взлома. Для изменения параметров безопасности, таких как защита от взлома, на устройстве должны быть соответствующие разрешения администратора.

Вот что вы видите в приложении Безопасность Windows:

![Защита tamper включена в Windows 10 Домашняя](images/tamperprotectionturnedon.png)

1. Выберите **Начните** и начните вводить *безопасность.* В результатах поиска выберите **Безопасность Windows**.

2. Выберите **параметры защиты &**  >  **вирусов & угрозы.**

3. Установите **защиту от взлома** **для включаемой** или **отключенной.**

## <a name="view-information-about-tampering-attempts"></a>Просмотр сведений о попытках фальсификации

Попытки взлома обычно указывают на крупные кибератаки. Плохие субъекты пытаются изменить параметры безопасности в качестве способа сохраняться и оставаться незамеченными. Если вы входите в команду безопасности организации, вы можете просматривать сведения о таких попытках, а затем принимать соответствующие меры для уменьшения угроз.

При обнаружении попытки взлома в Центр безопасности в Microsoft Defender [](/microsoft-365/security/defender-endpoint/portal-overview) [https://securitycenter.windows.com](https://securitycenter.windows.com) ().

![Центр безопасности в Microsoft Defender](images/tamperattemptalert.png)

Используя [обнаружение и нейтрализация атак на конечные точки](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) и [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) расширенные возможности охоты в Microsoft Defender for Endpoint, группа операций безопасности может исследовать и решать такие попытки.

## <a name="review-your-security-recommendations"></a>Просмотрите рекомендации по безопасности

Защита от взлома интегрируется с [возможностями управления & уязвимостей.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Рекомендации по безопасности включают](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) обеспечение включенной защиты от взлома. Например, можно искать в *подделывателье,* как показано на следующем изображении:

![Защита от взлома приводит к рекомендациям по безопасности](/images/securityrecs-tamperprotect.jpg)

В результатах можно выбрать **включить защиту от взлома,** чтобы узнать больше и включить ее.

![Включив защиту от взлома](images/tamperprotectsecurityrecos.png)

Дополнительные информацию об управлении & уязвимостей см. в & Управление уязвимостей в [Центр безопасности в Microsoft Defender.](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)

## <a name="frequently-asked-questions"></a>Вопросы и ответы

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>К какой Windows оси применяется настройка защиты от взлома?

Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), или позже вместе с [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint).

Если используется диспетчер конфигурации, версия 2006 с присоединением клиента, защита от взлома может быть расширена до Windows Server 2019. См. присоединение к клиенту: Создание и развертывание политики антивирусной защиты конечной точки из [центра администрирования (предварительный просмотр).](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>Повлияет ли защита от взлома на регистрацию сторонних антивирусов?

Нет. Сторонние антивирусные предложения будут продолжать регистрироваться в приложении Безопасность Windows.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>Что произойдет, антивирусная программа в Microsoft Defender не активен на устройстве?

Устройства, которые находятся в Microsoft Defender для конечной точки, будут антивирусная программа в Microsoft Defender в пассивном режиме. Защита от взлома будет по-прежнему защищать службу и ее функции. 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>Как включить/отключить защиту от взлома?

Если вы домашний пользователь, см. в статью Управление защитой от взлома [на отдельном устройстве.](#manage-tamper-protection-on-an-individual-device)

Если вы — организация, использующая [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint)точки, вы должны иметь возможность управлять защитой от взлома в Intune, аналогично тому, как вы управляете другими функциями защиты конечных точек. См. следующие разделы этой статьи: 

- [Управление защитой от взлома с помощью Intune](#manage-tamper-protection-for-your-organization-using-intune)
- [Управление защитой от взлома с помощью Configuration Manager, версия 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Управление защитой от взлома](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) с помощью Центр безопасности в Microsoft Defender (в настоящее время в предварительном просмотре)

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>Как настройка защиты от взлома в Intune влияет на управление антивирусная программа в Microsoft Defender с помощью групповой политики?

Обычная политика группы не применяется к защите от взлома, и изменения антивирусная программа в Microsoft Defender параметры игнорируются при внесения защиты от взлома. 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>Для Microsoft Defender для конечной точки настройка защиты от взлома в Intune ориентирована только на всю организацию?

Настройка защиты от взлома в Intune или Microsoft Endpoint Manager может быть ориентирована на всю организацию, а также на определенные устройства и группы пользователей.

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>Можно ли настроить защиту tamper в Microsoft Endpoint Configuration Manager?

Если вы используете присоединение клиента, вы можете использовать Microsoft Endpoint Configuration Manager. См. следующие ресурсы:
- [Управление защитой от взлома для организации с помощью Configuration Manager, версия 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Блог Community технологий: объявление о защите от тампера для клиентов клиента configuration Manager Tenant Attach](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>У меня есть Windows E3. Можно ли использовать настройку защиты от взлома в Intune?

В настоящее время настройка защиты от взлома в Intune доступна только для клиентов с [Microsoft Defender для конечной точки.](/microsoft-365/security/defender-endpoint)

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>Что произойдет, если я попытаюсь изменить параметры Microsoft Defender для конечных точек в intune, Microsoft Endpoint Configuration Manager и Windows инструментарии управления при включенной защите tamper на устройстве?

Вы не сможете изменить функции, защищенные защитой от взлома; такие запросы на изменение игнорируются.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Я корпоративный клиент. Могут ли местные администраторы изменить защиту от взлома на своих устройствах?

Нет. Местные администраторы не могут изменять или изменять параметры защиты от взлома.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>Что произойдет, если устройство находится на борту с Microsoft Defender для конечной точки, а затем переходит в отключенное состояние?

Если устройство отключено от Microsoft Defender для конечной точки, включена защита от взлома, что является состоянием по умолчанию для неукомплектоваемых устройств. 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>Будет ли предупреждение об изменении состояния защиты от взлома в Центр безопасности в Microsoft Defender?

Да. Оповещение отображается в [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) под **оповещении**.

Группа операций безопасности также может использовать поисковые запросы, например следующий пример:

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[Просмотр сведений о попытках фальсификации.](#view-information-about-tampering-attempts)

## <a name="see-also"></a>См. также

[Помощь в Windows компьютеров с Endpoint Protection для Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[Получить обзор Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint)

[Вместе лучше: антивирусная программа в Microsoft Defender и Microsoft Defender для конечной точки](why-use-microsoft-defender-antivirus.md)