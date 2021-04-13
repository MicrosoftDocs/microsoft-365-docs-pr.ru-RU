---
title: Настройка исключений для проверки av Microsoft Defender
description: Вы можете исключить проверку файлов (в том числе файлов, измененных указанными процессами) и папок с помощью microsoft Defender AV. Проверка исключений с помощью PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691506"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Настройка и проверка исключений для проверки антивирусных программ Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**

- [Microsoft Defender для конечной точки](/microsoft-365/security/defender-endpoint/)

Некоторые файлы, папки, процессы и файлы, открытые процессом, можно исключить из антивирусных сканов Microsoft Defender. Такие исключения применяются к [запланированным](scheduled-catch-up-scans-microsoft-defender-antivirus.md) [проверкам,](run-scan-microsoft-defender-antivirus.md)проверкам по запросу и постоянному контролю и защите в [режиме реального времени.](configure-real-time-protection-microsoft-defender-antivirus.md) Исключения для файлов, открытых процессом, применяются только к защите в режиме реального времени.

## <a name="configure-and-validate-exclusions"></a>Настройка и проверка исключений

Для настройки и проверки исключений см. следующие ниже.

- [Настройка и проверка исключений на основе имени файла, расширения и расположения папки.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) Это позволяет исключить файлы из антивирусных сканов Microsoft Defender в зависимости от их расширения, имени файла или расположения.

- [Настройка и проверка исключений для файлов, открытых процессами.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) Это позволяет исключить файлы из сканов, открытых определенным процессом.

## <a name="recommendations-for-defining-exclusions"></a>Рекомендации по определению исключений

Определение исключений снижает защиту, предложенную антивирусом Microsoft Defender. Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.

Ниже приводится список рекомендаций, которые следует иметь в виду при определении исключений:  

- Исключения технически являются пробелом в защите— всегда следует учитывать дополнительные меры по смягчению последствий при определении исключений. Дополнительные меры по смягчению последствий могут быть так же простыми, как обеспечение того, чтобы исключенное расположение было надлежащим списком управления доступом (ACLs), политикой аудита, обрабатывалось с помощью программного обеспечения, соответствующего данным, и т.д.

- Периодически просматривайте исключения. Переосмотрите и повторно ввести меры по смягчению последствий в рамках процесса проверки.

- В идеале не следует определять упреждающие исключения. Например, не исключайте что-то только потому, что вы думаете, что это может быть проблемой в будущем. Используйте исключения только для определенных проблем, в основном в области производительности, а иногда и для совместимости приложений, которые могут смягчать исключения.

- Аудит изменений списка исключений. Администратор службы безопасности должен сохранять достаточно контекста вокруг того, почему было добавлено определенное исключение. Вы должны иметь возможность дать ответ с конкретными рассуждениями о том, почему определенный путь был исключен.

## <a name="related-articles"></a>Статьи по теме

- [Исключения антивируса Microsoft Defender на Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Распространенные ошибки, которые следует избегать при определении исключений](common-exclusion-mistakes-microsoft-defender-antivirus.md)