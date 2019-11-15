---
title: Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 корпоративный
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Используйте это руководство по лаборатории тестирования для включения дополнительных параметров безопасности Microsoft 365 для тестовой среды Microsoft 365 Enterprise.
ms.openlocfilehash: f430acb4a7fd1842a4ae26025ad5a63cccf8392f
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640371"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Повышенная безопасность Microsoft 365 для тестовой среды Microsoft 365 корпоративный

С помощью инструкций, описанных в этой статье, вы настраиваете дополнительные параметры Microsoft 365 для повышения безопасности в тестовой среде Microsoft 365 Enterprise.

![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Щелкните [здесь](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный

Если вы просто хотите настроить усиленную безопасность Microsoft 365 в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите настроить усиленную безопасность Microsoft 365 на имитации предприятия, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> При тестировании повышенной безопасности Microsoft 365 не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов, для леса доменных служб Active Directory (AD DS). Он предоставляется в качестве параметра, чтобы можно было протестировать автоматизированное членство и членство в группах и поэкспериментировать с ним в среде, представляющей типичную организацию. 


## <a name="phase-2-configure-increased-microsoft-365-security"></a>Этап 2: Настройка усиленной безопасности Microsoft 365

На этом этапе вы включите повышенную безопасность Microsoft 365 для тестовой среды Microsoft 365 Enterprise. Дополнительные сведения и параметры можно найти [в статье Настройка клиента Office 365 для повышения безопасности](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Настройка SharePoint Online для блокирования приложений, не поддерживающих современные проверки подлинности

Приложения, не поддерживающие современные проверки подлинности, не могут иметь примененные к ним [конфигурации удостоверений и доступа к устройствам](microsoft-365-policies-configurations.md) , которые являются важным элементом защиты подписки Microsoft 365 и ее цифровых активов. 

1. Перейдите в центр администрирования Microsoft 365 ([https://portal.microsoft.com](https://portal.microsoft.com)) и войдите в свою подписку на тестовую лаборатория Office 365 с помощью учетной записи глобального администратора.
    
  - Если вы используете упрощенную тестовую среду Microsoft 365, войдите с локального компьютера.
    
  - Если вы используете имитируемую тестовую среду Microsoft 365, используйте [портал Azure](https://portal.azure.com) , чтобы подключиться к ВИРТУАЛЬНОЙ машине CLIENT1, а затем выполните вход с компьютера CLIENT1.
 
2. На новой вкладке **центра администрирования Microsoft 365** выберите **центр администрирования > SharePoint**.
3. На вкладке Новая **центр администрирования SharePoint** выберите **Управление доступом**.
4. В разделе **приложения, для которых не поддерживается современная проверка подлинности**, выберите пункт **блокировать**, а затем нажмите кнопку **ОК**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Включение расширенной защиты от угроз для SharePoint, OneDrive для бизнеса и Microsoft Teams

Office 365 Advanced Threat protection (ATP) для SharePoint, OneDrive и Microsoft Teams защищает организацию от случайного предоставления вредоносных файлов.

1. Перейдите в [Центр безопасности & безопасности Office 365](https://protection.office.com) и войдите в свою учетную запись глобального администратора.

2. В левой области навигации в разделе **Управление угрозами**выберите пункт **Политика > безопасные вложения**. 

3. Выберите **включить ATP для SharePoint, OneDrive и Microsoft Teams**.

4. Нажмите кнопку **Сохранить**.


### <a name="enable-anti-malware"></a>Включение защиты от вредоносных программ

Вредоносные программы состоят из вирусов и программ-шпионов. Вирусы заражают другие программы и данные, а также распространяются по компьютеру в поисках программ, которые можно заразить. Программы-шпионы относятся к вредоносным программам, которые собирают личные сведения пользователей, например данные для входа и персональные данные, и отправляют их обратно создателю этих программ. 

В Office 365 имеются встроенные возможности фильтрации вредоносных программ и нежелательной почты, которые помогают защитить входящие и исходящие сообщения от вредоносных программ и защищать вас от нежелательной почты. Дополнительные сведения содержатся в статье [Защита от нежелательной почты & вредоносных программ в Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Чтобы обеспечить выполнение защиты от вредоносных программ для файлов с распространенными типами файлов вложений:

1. Нажмите кнопку "назад" в браузере, чтобы вернуться на страницу " **Политика** ".
2. Нажмите кнопку **Защита от вредоносных программ**.
3. Дважды щелкните политику с именем **Default**.
4. В окне **Политика защиты от вредоносных программ** нажмите кнопку **Параметры**.
4. В разделе **общий фильтр типов вложений**нажмите кнопку **> сохранить**.


## <a name="phase-3-examine-the-threat-management-dashboard"></a>Этап 3: Проверка панели мониторинга управления угрозами

Управление угрозами Office 365 помогает управлять доступом мобильных устройств к данным вашей организации, защитить организацию от потери данных и защищать входящие и исходящие сообщения от вредоносных программ и спама. Кроме того, управление угрозами используется для защиты репутации домена и определения того, являются ли отправители неумышленно подложными учетными записями из вашего домена. Дополнительные сведения см в разделе [Управление угрозами в центре безопасности Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/threat-management).

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a>Дальнейшие действия

Сведения и ссылки для настройки этих параметров в рабочей среде можно найти в статье [Настройка повышенной безопасности для Microsoft 365](infoprotect-configure-increased-security-office-365.md) на этапе **защиты информации** .

Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.

## <a name="see-also"></a>См. также

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)

