---
title: Этапы регистрации устройств для партнеров
description: Как партнеры могут регистрировать устройства, чтобы ими могли управлять компьютеры, управляемые Майкрософт
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071447"
---
# <a name="steps-for-partners-to-register-devices"></a>Этапы регистрации устройств для партнеров


В этом разделе описаны действия, которые необходимо предпринять партнерам для регистрации устройств. Процесс самостоятельной регистрации устройств описан в документе [Register devices in Microsoft Managed Desktop yourself.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Подготовка к регистрации 
Прежде чем завершать регистрацию клиента, необходимо установить с ним связь в [Центре партнеров.](https://partner.microsoft.com/dashboard) Дополнительные сведения [об этом процессе](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) см. в документации по согласию. Любой партнер CSP может добавлять устройства от имени любого клиента, если клиент дает согласие. Вы также можете узнать больше о партнерских отношениях и разрешениях Autopilot в справке [Центра партнеров.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Эта документация только для партнеров и OEM. Процесс самостоятельной регистрации описан в документе [Register devices in Microsoft Managed Desktop yourself.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Регистрация устройств с помощью Центра партнеров

После того как вы установили отношения с клиентами, вы можете использовать Центр партнеров для добавления устройств в Autopilot для любого из клиентов, с которые у вас есть отношения, вы можете сделать следующее:

1. Переход в [Центр партнеров](https://partner.microsoft.com/dashboard)
2. Выберите  "Клиенты" в меню Центра партнеров, а затем выберите клиента, устройствами которого вы хотите управлять.
3. На странице подробностей клиента выберите **"Устройства".**
4. В **области "Применение профилей** к устройствам" выберите **"Добавить устройства".**
5. Введите **Microsoft365Managed_Autopilot** имя группы, а  затем выберите "Обзор", чтобы отправить список клиента (в формате CSV-файла) в Центр партнеров.


> [!IMPORTANT]
> Имя группы должно точно **соответствовать Microsoft365Managed_Autopilot,** включая буквы и специальные символы. Это позволит новым зарегистрированным устройствам быть назначены с помощью профиля Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Вы должны были получить этот CSV-файл с покупкой устройства. Если вы не получили CSV-файл, вы можете создать его самостоятельно, вы следуя шагам в добавлении устройств в [Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) Сценарий Windows PowerShell отличается от сценария, используемого для портала администрирования управляемых компьютеров [(Майкрософт).](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash) Партнерам следует использовать [Get-WindowsAutoPilotInfo для](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) регистрации устройств для настольных устройств, управляемых Майкрософт, в Центре партнеров.

Если при попытке отправить CSV-файл вы получите сообщение об ошибке, проверьте его формат. Убедитесь, что порядок столбцов совпадает с тем, что описано в описании использования профилей [Windows Autopilot](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)на новых устройствах для настройки работы с клиентом при его использовании. Вы также можете использовать пример CSV-файла, предоставленный по ссылке рядом **с** добавлением устройств, чтобы создать список устройств. 

Дополнительные сведения о Autopilot в сценариях партнеров см. в подразделе "Добавление устройств [в учетную запись клиента".](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Регистрация устройств с помощью API OEM

Перед завершением регистрации клиента необходимо установить с ним связь. У вас должна быть уникальная ссылка для соответствующих клиентов. Узнайте, [как установить отношение OEM.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

После того как вы установили отношение, вы можете начать регистрацию устройств для клиентов с помощью группового **тега Microsoft365Managed_Autopilot.**

> [!IMPORTANT]
> Имя группы должно точно **соответствовать Microsoft365Managed_Autopilot,** включая буквы и специальные символы. Это позволит новым зарегистрированным устройствам быть назначены с помощью профиля Microsoft Managed Desktop Autopilot.
