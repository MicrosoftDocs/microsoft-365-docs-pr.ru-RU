---
title: Как Exchange Online защищает секреты вашей электронной почты
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Помимо центра Office 365, который предоставляет сведения о безопасности, конфиденциальности и соответствия требованиям для Microsoft 365, вы можете узнать, как Корпорация Майкрософт помогает защищать секреты, хранимые в центрах обработки данных. Мы используем технологию под названием Диспетчер распределенных ключей (DKM).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906965"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Как Exchange Online защищает секреты вашей электронной почты

В этой статье описывается, как корпорация Майкрософт защищает вашу электронную почту в своих центрах обработки данных.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Как мы защищаем секретные сведения, предоставленные вами?

Помимо центра Office 365, который предоставляет сведения о [безопасности,](./get-started-with-service-trust-portal.md)конфиденциальности и соответствия требованиям для Office 365, вы можете узнать, как Корпорация Майкрософт помогает защищать секреты, которые вы предоставляете в центрах обработки данных. Мы используем технологию под названием Диспетчер распределенных ключей (DKM).
  
[Диспетчер распределенных ключей](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) — это клиентская функциональность, которая использует набор секретных ключей для шифрования и расшифровки информации. Только члены определенной группы безопасности в доменных службах Active Directory могут получать доступ к этим ключам для расшифровки данных, зашифрованных DKM. В Exchange Online только некоторые учетные записи служб, под которыми выполняются процессы Exchange, входят в эту группу безопасности. В рамках стандартной процедуры в центре обработки данных ни один человек не получает учетные данные, включенные в эту группу безопасности, и поэтому ни один человек не получает доступ к ключам, которые могут расшифровать эти секреты.
  
Для отладки, устранения неполадок и аудита администратор центра обработки данных должен запросить повышенные права доступа для получения временных учетных данных, которые входят в группу безопасности. Для этого процесса требуется несколько уровней юридического утверждения. Если доступ предоставлен, все действия заносятся в журнал и проходят аудиторскую проверку. Кроме того, доступ предоставляется только в течение заданного интервала, после чего он автоматически отключается.
  
Для дополнительной защиты технология DKM использует автоматический откат и архивацию ключей. Это также гарантирует, что вы сможете получить доступ к старому контенту, не используя все время один и тот же ключ.

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Где Exchange Online использует DKM?

Microsoft использует [диспетчер распределенных ключей](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) для шифрования секретов в Exchange Online центрах обработки данных. Например:
  
- Учетные данные для подключенных учетных записей электронной почты. Подключенные учетные записи — это сторонние учетные записи, такие как Hotmail, Yahoo! и Gmail.

- Ключ клиента. Если вы используете шифрование [службы с ключом](customer-key-overview.md)клиента, вы будете использовать [Хранилище ключей Azure для](/azure/key-vault/key-vault-whatis) защиты секретов.

## <a name="related-topics"></a>Статьи по теме

[Шифрование в Office 365](encryption.md)
  
[Технические сведения о шифровании](technical-reference-details-about-encryption.md)
  
[Обеспечение безопасности в Центре &amp; соответствия требованиям безопасности](./service-assurance.md)
