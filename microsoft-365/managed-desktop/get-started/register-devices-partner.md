---
title: Этапы регистрации устройств для партнеров
description: Как партнеры могут регистрировать устройства, чтобы управлять ими с помощью Microsoft Managed Desktop
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445594"
---
# <a name="steps-for-partners-to-register-devices"></a>Этапы регистрации устройств для партнеров


В этом разделе описываются действия для партнеров для регистрации устройств. Процесс самостоятельной регистрации устройств задокументирован на [устройствах Register в Microsoft Managed Desktop.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Подготовка к регистрации 
Прежде чем завершить регистрацию для клиента, сначала необходимо установить отношения с ними в [Центре партнеров.](https://partner.microsoft.com/dashboard) Дополнительные [сведения об](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) этом процессе см. в документации по согласию. Любой партнер CSP может добавлять устройства от имени любого клиента, если клиент соглашается. Вы также можете узнать больше о партнерских отношениях и разрешениях автопилота в [справке Центра партнеров.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Эта документация только для партнеров и OEMs. Процесс саморегистрации задокументирован на [устройствах Register в Microsoft Managed Desktop самостоятельно.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Регистрация устройств с помощью Центра партнеров

После того как вы установили отношения с клиентами, вы можете использовать Центр партнеров для добавления устройств в автопилот для любого из клиентов, с которые у вас есть отношения, следуя следующим шагам:

1. Перейдите в [Центр партнеров](https://partner.microsoft.com/dashboard)
2. Выберите **клиентов** из меню Центра партнеров, а затем выберите клиента, устройства которого вы хотите управлять.
3. На странице детализации клиента выберите **Устройства**.
4. В **статье Применение профилей к** устройствам выберите Добавить **устройства.**
5. Введите **Microsoft365Managed_Autopilot** имя группы, а затем выберите **Просмотр,** чтобы загрузить список клиента (в формате файлов csv) в Центр партнеров.


> [!IMPORTANT]
> Имя группы должно соответствовать **Microsoft365Managed_Autopilot,** включая капитализацию и специальные символы. Это позволит вновь зарегистрированным устройствам быть назначены с профилем Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Вы должны были получить этот файл CSV с покупкой устройства. Если вы не получили файл CSV, вы можете создать его самостоятельно, следуя шагам в добавлении устройств в [Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Сценарий Windows PowerShell отличается от сценария, используемого для портала [администрирования microsoft Managed Desktop.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash) Партнеры должны использовать [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) для регистрации устройств для устройств Microsoft Managed Desktop в Центре партнеров.

Если вы получаете сообщение об ошибке при попытке загрузить файл .csv, проверьте формат файла. Убедитесь, что порядок столбца совпадает с тем, что описано в профилей [Автопилота Windows](/partner-center/autopilot#add-devices-to-a-customers-account)на новых устройствах, чтобы настроить пользовательские возможности. Для создания списка устройств можно также использовать пример файла CSV, предоставленного по ссылке рядом с **Добавлением** устройств. 

Дополнительные сведения об автопилоте в сценариях партнеров см. в добавлении [устройств к учетной записи клиента.](/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Регистрация устройств с помощью API OEM

Прежде чем завершить регистрацию для клиента, сначала необходимо установить с ним связь. У вас должна быть уникальная ссылка, которая будет предоставляться соответствующим клиентам. Узнайте, [как установить связь OEM.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

После того как вы установили связь, вы можете начать регистрацию устройств для клиентов с помощью группового **тега Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> Имя группы должно **соответствовать** Microsoft365Managed_Autopilot, включая капитализацию и специальные символы. Это позволит вновь зарегистрированным устройствам быть назначены с профилем Microsoft Managed Desktop Autopilot.