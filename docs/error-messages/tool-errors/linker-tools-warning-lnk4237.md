---
title: リンカー ツールの警告 LNK4237 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4237
dev_langs:
- C++
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 479bd4ff8a4f48da679c9e17ec100668de84d089
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113709"
---
# <a name="linker-tools-warning-lnk4237"></a>リンカー ツールの警告 LNK4237

中に/subsystem:native が 'dll' からインポートする場合の指定/SUBSYSTEM:CONSOLE か/SUBSYSTEM:WINDOWS を使用します。

[中に/subsystem:native が](../../build/reference/subsystem-specify-subsystem.md)構築 (Win32) windows アプリケーションを直接使用している場合、次の 1 つ以上指定されました。

- kernel32.dll

- gdi32.dll

- user32.dll

- 1 つ、msvcrt の\*dll。

指定しないでこの警告を解決する**中に/subsystem:native が**します。