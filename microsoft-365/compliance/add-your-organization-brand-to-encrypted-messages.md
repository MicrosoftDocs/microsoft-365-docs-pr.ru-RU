---
title: Добавление бренда организации в зашифрованные сообщения
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Узнайте, как глобальные администраторы Office 365 могут применять брендинг организации к зашифрованным сообщениям электронной почты & содержимого портала шифрования.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394717"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="16724-103">Добавление бренда организации в microsoft 365 для зашифрованных сообщений шифрования бизнес-сообщений</span><span class="sxs-lookup"><span data-stu-id="16724-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="16724-104">Вы можете применить брендинг компании, чтобы настроить внешний вид сообщений электронной почты организации и портала шифрования.</span><span class="sxs-lookup"><span data-stu-id="16724-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="16724-105">Чтобы начать работу, необходимо применить глобальные разрешения администратора к своей учетной записи или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="16724-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="16724-106">После получения этих разрешений используйте Get-OMEConfiguration и Set-OMEConfiguration Windows PowerShell для настройки этих частей зашифрованных сообщений электронной почты:</span><span class="sxs-lookup"><span data-stu-id="16724-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="16724-107">Вводный текст</span><span class="sxs-lookup"><span data-stu-id="16724-107">Introductory text</span></span>

- <span data-ttu-id="16724-108">Disclaimer text</span><span class="sxs-lookup"><span data-stu-id="16724-108">Disclaimer text</span></span>

- <span data-ttu-id="16724-109">URL-адрес для заявления о конфиденциальности вашей организации</span><span class="sxs-lookup"><span data-stu-id="16724-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="16724-110">Текст на портале OME</span><span class="sxs-lookup"><span data-stu-id="16724-110">Text in the OME portal</span></span>

- <span data-ttu-id="16724-111">Логотип, который отображается в сообщении электронной почты и портале OME, или же использовать логотип вообще</span><span class="sxs-lookup"><span data-stu-id="16724-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="16724-112">Цвет фона в сообщении электронной почты и портале OME</span><span class="sxs-lookup"><span data-stu-id="16724-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="16724-113">Кроме того, в любое время вы можете восстановить интерфейс по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16724-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="16724-114">Для создания нескольких шаблонов зашифрованных сообщений, исходя из организации, используйте шифрование расширенных сообщений Office 365.</span><span class="sxs-lookup"><span data-stu-id="16724-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="16724-115">Эти шаблоны используются для управления частями интерфейса конечного пользователя.</span><span class="sxs-lookup"><span data-stu-id="16724-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="16724-116">Например, укажите, могут ли получатели использовать учетные записи Google, Yahoo и Microsoft для входов на портал шифрования.</span><span class="sxs-lookup"><span data-stu-id="16724-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="16724-117">Используйте шаблоны для выполнения нескольких случаев использования, таких как:</span><span class="sxs-lookup"><span data-stu-id="16724-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="16724-118">Отдельные отделы, такие как Финансы, Продажи и так далее.</span><span class="sxs-lookup"><span data-stu-id="16724-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="16724-119">Различные продукты</span><span class="sxs-lookup"><span data-stu-id="16724-119">Different products</span></span>

- <span data-ttu-id="16724-120">Различные географические регионы или страны</span><span class="sxs-lookup"><span data-stu-id="16724-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="16724-121">Хотите ли вы разрешить отмену электронных писем</span><span class="sxs-lookup"><span data-stu-id="16724-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="16724-122">Хотите ли вы, чтобы срок действия электронной почты, отправленной внешним получателям, истекал по истечении определенного числа дней.</span><span class="sxs-lookup"><span data-stu-id="16724-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="16724-123">После создания шаблонов можно применить их к зашифрованным электронным письмам с помощью правил потока почты Exchange.</span><span class="sxs-lookup"><span data-stu-id="16724-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="16724-124">Если у вас есть шифрование расширенных сообщений Office 365, с помощью этих шаблонов можно отоискить любую электронную почту, которую вы завяли.</span><span class="sxs-lookup"><span data-stu-id="16724-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="16724-125">Работа с шаблонами брендинга OME</span><span class="sxs-lookup"><span data-stu-id="16724-125">Work with OME branding templates</span></span>

<span data-ttu-id="16724-126">Вы можете изменить несколько функций в шаблоне брендинга.</span><span class="sxs-lookup"><span data-stu-id="16724-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="16724-127">Шаблон по умолчанию можно изменить, но не удалить.</span><span class="sxs-lookup"><span data-stu-id="16724-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="16724-128">Если у вас есть расширенный шифрование сообщений, вы также можете создавать, изменять и удалять настраиваемые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="16724-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="16724-129">Используйте Windows PowerShell для работы с одним шаблоном брендинга одновременно.</span><span class="sxs-lookup"><span data-stu-id="16724-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="16724-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) — изменение шаблона брендинга по умолчанию или созданного вами пользовательского шаблона брендинга.</span><span class="sxs-lookup"><span data-stu-id="16724-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="16724-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) — создание нового шаблона фирменности, только для предварительного шифрования сообщений.</span><span class="sxs-lookup"><span data-stu-id="16724-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="16724-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) — удалите настраиваемый шаблон брендинга, только расширенный шифрование сообщений.</span><span class="sxs-lookup"><span data-stu-id="16724-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="16724-133">Вы не можете удалить шаблон брендинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16724-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="16724-134">Изменение шаблона брендинга OME</span><span class="sxs-lookup"><span data-stu-id="16724-134">Modify an OME branding template</span></span>

<span data-ttu-id="16724-135">Используйте Windows PowerShell для изменения одного шаблона брендинга одновременно.</span><span class="sxs-lookup"><span data-stu-id="16724-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="16724-136">Если у вас есть расширенный шифрование сообщений, вы также можете создавать, изменять и удалять настраиваемые шаблоны.</span><span class="sxs-lookup"><span data-stu-id="16724-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="16724-137">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="16724-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="16724-138">Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16724-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="16724-139">Используйте Set-OMEConfiguration, как описано в [set-OMEConfiguration,](/powershell/module/exchange/Set-OMEConfiguration) или используйте следующие графические и таблицы для руководства.</span><span class="sxs-lookup"><span data-stu-id="16724-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Настраиваемые части электронной почты](../media/ome-template-breakout.png)

|<span data-ttu-id="16724-141">**Настройка этой функции шифрования**</span><span class="sxs-lookup"><span data-stu-id="16724-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="16724-142">**Используйте эти команды**</span><span class="sxs-lookup"><span data-stu-id="16724-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16724-143">Цвет фона</span><span class="sxs-lookup"><span data-stu-id="16724-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="16724-144">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="16724-145">Дополнительные сведения о цветах фона см. в разделе [Фоновые](#background-color-reference) цвета в этой статье.</span><span class="sxs-lookup"><span data-stu-id="16724-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="16724-146">Логотип</span><span class="sxs-lookup"><span data-stu-id="16724-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="16724-147">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="16724-148">Поддерживаемые форматы файлов: PNG, JPG, BMP, TIFF</span><span class="sxs-lookup"><span data-stu-id="16724-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="16724-149">Оптимальный размер файла эмблемы: менее 40 КБ</span><span class="sxs-lookup"><span data-stu-id="16724-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="16724-150">Оптимальный размер изображения логотипа: 170x70 пикселей.</span><span class="sxs-lookup"><span data-stu-id="16724-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="16724-151">Если ваше изображение превышает эти размеры, служба повторно размеры вашего логотипа для отображения на портале.</span><span class="sxs-lookup"><span data-stu-id="16724-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="16724-152">Служба не изменит сам графический файл.</span><span class="sxs-lookup"><span data-stu-id="16724-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="16724-153">Для получения наилучших результатов используйте оптимальный размер.</span><span class="sxs-lookup"><span data-stu-id="16724-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="16724-154">Текст рядом с именем и адресом электронной почты отправитель</span><span class="sxs-lookup"><span data-stu-id="16724-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="16724-155">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="16724-156">Текст, который отображается на кнопке "Чтение сообщения"</span><span class="sxs-lookup"><span data-stu-id="16724-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="16724-157">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="16724-158">Текст, который отображается ниже кнопки "Чтение сообщения"</span><span class="sxs-lookup"><span data-stu-id="16724-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="16724-159">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="16724-160">URL-адрес ссылки "Заявление о конфиденциальности"</span><span class="sxs-lookup"><span data-stu-id="16724-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="16724-161">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="16724-162">Заявление об отказе в зашифрованном сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="16724-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="16724-163">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="16724-164">Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="16724-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="16724-165">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="16724-166">Включить или отключить проверку подлинности с помощью разового кода прохода для этого настраиваемого шаблона</span><span class="sxs-lookup"><span data-stu-id="16724-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="16724-167">**Примеры.**</span><span class="sxs-lookup"><span data-stu-id="16724-167">**Examples:**</span></span> <br/><span data-ttu-id="16724-168">Включить одновековые коды паролей для этого настраиваемого шаблона</span><span class="sxs-lookup"><span data-stu-id="16724-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="16724-169">Отключение одновекового пароля для этого настраиваемого шаблона</span><span class="sxs-lookup"><span data-stu-id="16724-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="16724-170">Чтобы включить или отключить проверку подлинности с помощью удостоверений Microsoft, Google или Yahoo для этого пользовательского шаблона</span><span class="sxs-lookup"><span data-stu-id="16724-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="16724-171">**Примеры.**</span><span class="sxs-lookup"><span data-stu-id="16724-171">**Examples:**</span></span> <br/><span data-ttu-id="16724-172">Чтобы включить социальные ID для этого пользовательского шаблона</span><span class="sxs-lookup"><span data-stu-id="16724-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="16724-173">Отключение социальных ID для этого пользовательского шаблона</span><span class="sxs-lookup"><span data-stu-id="16724-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="16724-174">Создание шаблона брендинга OME (предварительное шифрование сообщений)</span><span class="sxs-lookup"><span data-stu-id="16724-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="16724-175">Если у вас есть шифрование расширенных сообщений Office 365, вы можете создать настраиваемые шаблоны брендинга для организации с помощью комлета [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="16724-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="16724-176">После создания шаблона вы измените шаблон с помощью Set-OMEConfiguration, как описано в шаблоне модифицировать шаблон [брендинга OME.](#modify-an-ome-branding-template)</span><span class="sxs-lookup"><span data-stu-id="16724-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="16724-177">Можно создать несколько шаблонов.</span><span class="sxs-lookup"><span data-stu-id="16724-177">You can create multiple templates.</span></span>

<span data-ttu-id="16724-178">Создание нового пользовательского шаблона брендинга:</span><span class="sxs-lookup"><span data-stu-id="16724-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="16724-179">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="16724-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="16724-180">Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16724-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="16724-181">Для создания нового шаблона используйте комлет [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="16724-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="16724-182">Пример.</span><span class="sxs-lookup"><span data-stu-id="16724-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="16724-183">Возврат шаблона брендинга по умолчанию к исходным значениям</span><span class="sxs-lookup"><span data-stu-id="16724-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="16724-184">Чтобы удалить все изменения из шаблона по умолчанию, включая настройки бренда и т. ч., выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="16724-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="16724-185">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="16724-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="16724-186">Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16724-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="16724-187">Используйте **комлет Set-OMEConfiguration,** как описано в [Set-OMEConfiguration.](/powershell/module/exchange/Set-OMEConfiguration)</span><span class="sxs-lookup"><span data-stu-id="16724-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="16724-188">Чтобы удалить фирменные настройки организации из значений DisclaimerText, EmailText и PortalText, установите значение пустой `""` строки.</span><span class="sxs-lookup"><span data-stu-id="16724-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="16724-189">Для всех значений изображений, таких как Logo, установите значение  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="16724-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="16724-190">В следующей таблице описываются параметры настройки шифрования по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16724-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="16724-191">Сброс функции шифрования к тексту и изображению по умолчанию</span><span class="sxs-lookup"><span data-stu-id="16724-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="16724-192">Используйте эти команды</span><span class="sxs-lookup"><span data-stu-id="16724-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="16724-193">Текст по умолчанию, который поставляется с зашифрованными сообщениями электронной почты.</span><span class="sxs-lookup"><span data-stu-id="16724-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="16724-194">Текст по умолчанию, отображающийся над инструкциями по просмотру зашифрованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="16724-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="16724-195">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="16724-196">Заявление об отказе в зашифрованном сообщении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="16724-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="16724-197">**Пример:**</span><span class="sxs-lookup"><span data-stu-id="16724-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="16724-198">Текст, отображающийся в верхней части портала просмотра зашифрованных сообщений.</span><span class="sxs-lookup"><span data-stu-id="16724-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="16724-199">**Пример, возвращающийся к умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="16724-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="16724-200">Логотип</span><span class="sxs-lookup"><span data-stu-id="16724-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="16724-201">**Пример, возвращающийся к умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="16724-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="16724-202">Цвет фона</span><span class="sxs-lookup"><span data-stu-id="16724-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="16724-203">**Пример, возвращающийся к умолчанию:**</span><span class="sxs-lookup"><span data-stu-id="16724-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="16724-204">Удаление пользовательского шаблона брендинга (предварительное шифрование сообщений)</span><span class="sxs-lookup"><span data-stu-id="16724-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="16724-205">Вы можете удалить или удалить только шаблоны брендинга, которые вы сделали.</span><span class="sxs-lookup"><span data-stu-id="16724-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="16724-206">Вы не можете удалить шаблон брендинга по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16724-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="16724-207">Чтобы удалить настраиваемый шаблон брендинга:</span><span class="sxs-lookup"><span data-stu-id="16724-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="16724-208">С помощью учетной записи для работы или учебного заведения с глобальными разрешениями администратора в организации запустите сеанс Windows PowerShell и подключите его к Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="16724-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="16724-209">Инструкции см. в статье [Подключение к Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16724-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="16724-210">Используйте **комлет Remove-OMEConfiguration** следующим образом:</span><span class="sxs-lookup"><span data-stu-id="16724-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="16724-211">Пример.</span><span class="sxs-lookup"><span data-stu-id="16724-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="16724-212">Дополнительные сведения см. [в дополнительных сведениях Remove-OMEConfiguration.](/powershell/module/exchange/remove-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="16724-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="16724-213">Создайте правило потока почты Exchange, которое применяет настраиваемый брендинг к зашифрованным электронным письмам</span><span class="sxs-lookup"><span data-stu-id="16724-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="16724-214">После изменения шаблона по умолчанию или создания новых шаблонов брендинга можно создать правила потока почты Exchange для применения настраиваемой фирменности на основе определенных условий.</span><span class="sxs-lookup"><span data-stu-id="16724-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="16724-215">Такое правило будет применять настраиваемый брендинг в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="16724-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="16724-216">Если электронная почта была зашифрована вручную конечным пользователем с помощью Outlook или Outlook в Интернете, Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="16724-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="16724-217">Если электронная почта была автоматически зашифрована правилом потока почты Exchange или политикой предотвращения потери данных</span><span class="sxs-lookup"><span data-stu-id="16724-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="16724-218">Сведения о создании правила потока почты Exchange, применяемой для шифрования, см. в статью Определение правил потока почты для шифрования сообщений электронной почты [в Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="16724-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="16724-219">В веб-браузере, используя учетную запись для работы или школы, которая получила разрешения глобального администратора, вопишитесь в [Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span><span class="sxs-lookup"><span data-stu-id="16724-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="16724-220">Выберите **плитку администрирования.**</span><span class="sxs-lookup"><span data-stu-id="16724-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="16724-221">В центре администрирования Microsoft 365 выберите **центры администрирования** \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="16724-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="16724-222">В EAC перейдите к **правилам потока** \> **почты** и выберите **новый** ![ значок Создание нового ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **правила**.</span><span class="sxs-lookup"><span data-stu-id="16724-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="16724-223">Дополнительные сведения об использовании EAC см. в центре [администрирования Exchange в Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="16724-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="16724-224">В **Name** введите имя правила, например Branding для отдела продаж.</span><span class="sxs-lookup"><span data-stu-id="16724-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="16724-225">В **Примени** это правило, если выберите условие, которое отправителю находится внутри организации, и другие условия, которые вам нужны из списка доступных условий. </span><span class="sxs-lookup"><span data-stu-id="16724-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="16724-226">Например, может потребоваться применить определенный шаблон брендинга для:</span><span class="sxs-lookup"><span data-stu-id="16724-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="16724-227">Все зашифрованные сообщения электронной почты, отправленные от сотрудников финансового отдела</span><span class="sxs-lookup"><span data-stu-id="16724-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="16724-228">Зашифрованные сообщения электронной почты, отправленные с определенным ключевым словом, таким как "Внешний" или "Партнер"</span><span class="sxs-lookup"><span data-stu-id="16724-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="16724-229">Зашифрованные сообщения электронной почты, отправленные в определенный домен</span><span class="sxs-lookup"><span data-stu-id="16724-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="16724-230">Далее **выберите** **Изменение** безопасности сообщений \> **Применение настраиваемой фирменности для сообщений OME.**</span><span class="sxs-lookup"><span data-stu-id="16724-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="16724-231">Далее из выпадаемой страницы выберите шаблон брендинга.</span><span class="sxs-lookup"><span data-stu-id="16724-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="16724-232">(Необязательный) Вы можете настроить правило потока почты, чтобы применить шифрование и настраиваемый брендинг.</span><span class="sxs-lookup"><span data-stu-id="16724-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="16724-233">Из **этого выберите** **Изменение** безопасности сообщений, а затем выберите Применение шифрования сообщений Office **365 и защиты прав.**</span><span class="sxs-lookup"><span data-stu-id="16724-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="16724-234">Выберите шаблон RMS из списка, выберите **Сохранить**, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="16724-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="16724-235">Список шаблонов включает шаблоны и параметры по умолчанию, а также созданные пользовательские шаблоны.</span><span class="sxs-lookup"><span data-stu-id="16724-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="16724-236">Если список пуст, убедитесь, что вы настроили шифрование сообщений Office 365 с новыми возможностями.</span><span class="sxs-lookup"><span data-stu-id="16724-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="16724-237">Инструкции см. в инструкции Настройка новых возможностей шифрования сообщений [Office 365.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="16724-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="16724-238">Сведения о шаблонах по умолчанию см. в меню Настройка и управление шаблонами [для Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates)</span><span class="sxs-lookup"><span data-stu-id="16724-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="16724-239">Сведения о параметре **"Не переададку"** см. в варианте [Не переададка электронной почты.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="16724-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="16724-240">Сведения о только **варианте шифрования** см. в [параметре Шифровать только для электронных писем.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="16724-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="16724-241">Выберите **действие добавить,** если нужно указать другое действие.</span><span class="sxs-lookup"><span data-stu-id="16724-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="16724-242">Справочная ссылка цвета фона</span><span class="sxs-lookup"><span data-stu-id="16724-242">Background color reference</span></span>

<span data-ttu-id="16724-243">Имена цветов, которые можно использовать для фонового цвета, ограничены.</span><span class="sxs-lookup"><span data-stu-id="16724-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="16724-244">Вместо цветного имени можно использовать значение кода hex (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="16724-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="16724-245">Вы можете использовать значение кода hex, соответствующее цвету имени, или вы можете использовать пользовательское значение кода hex.</span><span class="sxs-lookup"><span data-stu-id="16724-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="16724-246">Обязательно заключив значение кода hex в кавычках (например, `"#f0f8ff"` ).</span><span class="sxs-lookup"><span data-stu-id="16724-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="16724-247">Доступные имена фоновых цветов и соответствующие значения кода гекса описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="16724-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="16724-248">**Название цвета**</span><span class="sxs-lookup"><span data-stu-id="16724-248">**Color name**</span></span>|<span data-ttu-id="16724-249">**Цветовой код**</span><span class="sxs-lookup"><span data-stu-id="16724-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="16724-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="16724-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="16724-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="16724-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="16724-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="16724-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="16724-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="16724-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="16724-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="16724-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="16724-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="16724-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="16724-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="16724-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="16724-257">#000000</span><span class="sxs-lookup"><span data-stu-id="16724-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="16724-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="16724-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="16724-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="16724-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="16724-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="16724-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="16724-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="16724-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="16724-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="16724-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="16724-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="16724-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="16724-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="16724-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="16724-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="16724-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="16724-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="16724-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="16724-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="16724-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="16724-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="16724-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="16724-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="16724-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="16724-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="16724-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="16724-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="16724-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="16724-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="16724-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="16724-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="16724-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="16724-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="16724-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="16724-275">#006400</span><span class="sxs-lookup"><span data-stu-id="16724-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="16724-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="16724-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="16724-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="16724-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="16724-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="16724-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="16724-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="16724-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="16724-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="16724-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="16724-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="16724-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="16724-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="16724-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="16724-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="16724-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="16724-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="16724-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="16724-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="16724-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="16724-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="16724-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="16724-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="16724-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="16724-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="16724-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="16724-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="16724-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="16724-290">#696969</span><span class="sxs-lookup"><span data-stu-id="16724-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="16724-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="16724-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="16724-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="16724-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="16724-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="16724-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="16724-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="16724-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="16724-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="16724-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="16724-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="16724-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="16724-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="16724-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="16724-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="16724-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="16724-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="16724-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="16724-300">#808080</span><span class="sxs-lookup"><span data-stu-id="16724-300">#808080</span></span>|
|`green`|<span data-ttu-id="16724-301">#008000</span><span class="sxs-lookup"><span data-stu-id="16724-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="16724-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="16724-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="16724-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="16724-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="16724-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="16724-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="16724-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="16724-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="16724-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="16724-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="16724-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="16724-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="16724-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="16724-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="16724-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="16724-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="16724-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="16724-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="16724-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="16724-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="16724-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="16724-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="16724-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="16724-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="16724-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="16724-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="16724-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="16724-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="16724-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="16724-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="16724-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="16724-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="16724-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="16724-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="16724-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="16724-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="16724-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="16724-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="16724-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="16724-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="16724-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="16724-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="16724-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="16724-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="16724-324">#778899</span><span class="sxs-lookup"><span data-stu-id="16724-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="16724-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="16724-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="16724-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="16724-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="16724-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="16724-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="16724-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="16724-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="16724-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="16724-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="16724-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="16724-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="16724-331">#800000</span><span class="sxs-lookup"><span data-stu-id="16724-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="16724-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="16724-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="16724-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="16724-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="16724-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="16724-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="16724-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="16724-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="16724-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="16724-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="16724-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="16724-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="16724-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="16724-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="16724-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="16724-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="16724-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="16724-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="16724-341">#191970</span><span class="sxs-lookup"><span data-stu-id="16724-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="16724-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="16724-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="16724-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="16724-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="16724-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="16724-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="16724-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="16724-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="16724-346">#000080</span><span class="sxs-lookup"><span data-stu-id="16724-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="16724-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="16724-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="16724-348">#808000</span><span class="sxs-lookup"><span data-stu-id="16724-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="16724-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="16724-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="16724-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="16724-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="16724-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="16724-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="16724-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="16724-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="16724-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="16724-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="16724-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="16724-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="16724-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="16724-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="16724-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="16724-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="16724-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="16724-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="16724-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="16724-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="16724-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="16724-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="16724-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="16724-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="16724-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="16724-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="16724-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="16724-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="16724-363">#800080</span><span class="sxs-lookup"><span data-stu-id="16724-363">#800080</span></span>|
|`red`|<span data-ttu-id="16724-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="16724-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="16724-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="16724-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="16724-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="16724-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="16724-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="16724-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="16724-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="16724-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="16724-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="16724-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="16724-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="16724-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="16724-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="16724-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="16724-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="16724-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="16724-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="16724-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="16724-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="16724-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="16724-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="16724-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="16724-376">#708090</span><span class="sxs-lookup"><span data-stu-id="16724-376">#708090</span></span>|
|`snow`|<span data-ttu-id="16724-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="16724-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="16724-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="16724-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="16724-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="16724-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="16724-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="16724-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="16724-381">#008080</span><span class="sxs-lookup"><span data-stu-id="16724-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="16724-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="16724-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="16724-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="16724-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="16724-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="16724-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="16724-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="16724-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="16724-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="16724-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="16724-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="16724-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="16724-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="16724-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="16724-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="16724-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="16724-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="16724-390">#9acd32</span></span>|