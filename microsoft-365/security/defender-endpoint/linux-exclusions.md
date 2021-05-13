---
title: Настройка и проверка исключений для Microsoft Defender для конечной точки на Linux
description: Предоставление и проверка исключений для Microsoft Defender для конечной точки на Linux. Исключения могут быть установлены для файлов, папок и процессов.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, exclusions, scans, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346418"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Настройка и проверка исключений для Microsoft Defender для конечной точки на Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Область применения:**

- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Хотите испытать Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

В этой статье данная статья содержит сведения о том, как определить исключения, применимые к проверкам по запросу, а также защиту и мониторинг в режиме реального времени.

> [!IMPORTANT]
> Исключения, описанные в этой статье, не применяются к другим возможностям Defender для конечной точки Linux, включая обнаружение и нейтрализация атак на конечные точки (EDR). Файлы, исключаемые с помощью методов, описанных в этой статье, по-прежнему могут вызывать EDR оповещения и другие обнаружения.

Вы можете исключить определенные файлы, папки, процессы и открытые процессом файлы из Defender для конечной точки на проверках Linux.

Исключения могут быть полезны, чтобы избежать неправильных обнаружений в файлах или программном обеспечении, уникальных или настраиваемых для вашей организации. Они также могут быть полезны для смягчения проблем с производительностью, вызванных Defender для конечной точки в Linux.

> [!WARNING]
> Определение исключений снижает защиту, предложенную Defender для конечной точки на Linux. Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.

## <a name="supported-exclusion-types"></a>Поддерживаемые типы исключений

В таблице ниже показаны типы исключений, поддерживаемые Defender для конечной точки в Linux.

Исключения | Определение | Примеры
---|---|---
Расширение файла | Все файлы с расширением в любом месте на устройстве | `.test`
File | Определенный файл, определенный по полному пути | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Folder | Все файлы в указанной папке (повторно) | `/var/log/`<br/>`/var/*/`
Процесс | Определенный процесс (указанный полным путем или именем файла) и все файлы, открытые в нем. | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> Для успешного исключения из нее должны быть жесткие ссылки, а не символические. Вы можете проверить, является ли путь символической ссылкой при `file <path-name>` запуске.

Исключения файлов, папок и процессов поддерживают следующие подкарды:

Подстановочный знак | Описание | Пример | Совпадения | Не совпадает
---|---|---|---|---
\* |    Совпадает с любым числом символов, в том числе без них (обратите внимание, что при данной подмастерье используется внутри пути, она заменит только одну папку) | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Соответствует любому отдельному символу | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>Настройка списка исключений

### <a name="from-the-management-console"></a>Из консоли управления

Дополнительные сведения о настройке исключений из Puppet, Ansible или другой консоли управления см. в статью Настройка предпочтений [для Defender для конечной](linux-preferences.md)точки в Linux.

### <a name="from-the-command-line"></a>Из командной строки

Запустите следующую команду, чтобы увидеть доступные переключатели для управления исключениями:

```bash
mdatp exclusion
```

> [!TIP]
> При настройке исключений с помощью поддиагров заключим параметр в двойные кавычка, чтобы предотвратить globbing.

Примеры:

- Добавление исключения для расширения файла:

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- Добавление исключения для файла:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- Добавление исключения для папки:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- Добавьте исключение для папки с подстройки в ней:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Это позволит исключить только пути на уровне *ниже /var/,* но не папки, которые более глубоко вложены; например, */var/this-subfolder/but-not-this-subfolder*.
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > Это исключит все пути, родитель которых */var/*; например, */var/this-subfolder/and-this-subfolder-as-well*.

    ```Output
    Folder exclusion configured successfully
    ```

- Добавление исключения для процесса:

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Проверка списков исключений в тестовом файле EICAR

Вы можете проверить, работают ли списки исключений, `curl` скачав тестовый файл.

В следующем фрагменте Bash замените файл, соответствующий `test.txt` правилам исключения. Например, если вы исключили `.testing` расширение, замените `test.txt` `test.testing` . Если вы тестируете путь, убедитесь, что вы запустите команду в этом пути.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Если Defender for Endpoint на Linux сообщает о вредоносных программах, то правило не работает. Если нет отчета о вредоносных программах, а загруженный файл существует, то исключение работает. Вы можете открыть файл, чтобы подтвердить, что содержимое является таким же, как описано на веб-сайте [тестового файла EICAR](http://2016.eicar.org/86-0-Intended-use.html).

Если у вас нет доступа к Интернету, вы можете создать собственный тестовый файл EICAR. Напишите строку EICAR в новый текстовый файл со следующей командой Bash:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

Вы также можете скопировать строку в пустой текстовый файл и попытаться сохранить ее с именем файла или в папке, вы пытаетсяе исключить.

## <a name="allow-threats"></a>Разрешить угрозы

Помимо исключения определенного контента из проверки можно также настроить продукт, чтобы не обнаруживать некоторые классы угроз (определенных именем угрозы). Вы должны соблюдать осторожность при использовании этой функции, так как она может оставить устройство незащищенным.

Чтобы добавить имя угрозы в разрешенный список, выполните следующую команду:

```bash
mdatp threat allowed add --name [threat-name]
```

Имя угрозы, связанное с обнаружением на устройстве, можно получить с помощью следующей команды:

```bash
mdatp threat list
```

Например, чтобы добавить (имя угрозы, связанное с обнаружением EICAR) в разрешенный `EICAR-Test-File (not a virus)` список, выполните следующую команду:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
