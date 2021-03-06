---
title: Настройка исключений для антивирусная программа в Microsoft Defender сканирования
description: Вы можете исключить проверку файлов (в том числе файлов, измененных указанными процессами) и папок антивирусная программа в Microsoft Defender. Проверка исключений с помощью PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275124"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Настройка и проверка исключений для антивирусная программа в Microsoft Defender сканирования

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Некоторые файлы, папки, процессы и открытые процессом файлы можно исключить из антивирусная программа в Microsoft Defender сканирования. Такие исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и постоянному контролю и защите в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md) Исключения для файлов, открытых процессом, применяются только к защите в режиме реального времени.

## <a name="configure-and-validate-exclusions"></a>Настройка и проверка исключений

Для настройки и проверки исключений см. следующие ниже.

- [Настройка и проверка исключений на основе имени файла, расширения и расположения папки.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) Можно исключить файлы из антивирусная программа в Microsoft Defender в зависимости от их расширения, имени файла или расположения.

- [Настройка и проверка исключений для файлов, открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) Вы можете исключить файлы из сканов, открытых определенным процессом.

## <a name="recommendations-for-defining-exclusions"></a>Рекомендации для определения исключений

> [!IMPORTANT]
> антивирусная программа в Microsoft Defender включает множество автоматических исключений, основанных на известных действиях операционной системы и типичных файлах управления, например используемых в управлении предприятиями, управлении базами данных и других корпоративных сценариях и ситуациях.  
> 
> Определение исключений снижает защиту, предложенную антивирусная программа в Microsoft Defender. Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.

При определении исключений следует помнить о следующих моментах:  

- Исключения технически являются пробелом в защите. Всегда учитывайте смягчение при определении исключений. Другие меры по смягчению последствий могут быть так же просты, как убедиться, что исключенное расположение имеет соответствующие списки управления доступом (ACLs), политику аудита, обрабатывается с помощью обновления программного обеспечения и т.д.

- Периодически просматривайте исключения. Перепроверка и повторное выполнение смягчения последствий в рамках процесса проверки.

- В идеале избегайте определения исключений, которые должны быть активными. Например, не исключайте что-то только потому, что вы думаете, что это может быть проблемой в будущем. Используйте исключения только для определенных проблем, например, связанных с производительностью или совместимостью приложений, которые могут смягчить исключения.

- Аудит изменений списка исключений. Администратор службы безопасности должен сохранять достаточно контекста вокруг того, почему было добавлено определенное исключение. Вы должны иметь возможность дать ответ с конкретными рассуждениями о том, почему определенный путь был исключен.

## <a name="related-articles"></a>Связанные статьи

- [антивирусная программа в Microsoft Defender исключений на Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Распространенные ошибки, которых следует избегать при определении исключений](common-exclusion-mistakes-microsoft-defender-antivirus.md)
