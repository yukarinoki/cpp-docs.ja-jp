---
description: 詳細については、「リンカーツールの警告 LNK4237」を参照してください。
title: リンカー ツールの警告 LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 9f8af2d6f0fa2d1153af749e327e95b863ed6914
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259995"
---
# <a name="linker-tools-warning-lnk4237"></a>リンカー ツールの警告 LNK4237

/SUBSYSTEM: ' dll ' からインポートするときにネイティブに指定されました。/SUBSYSTEM: CONSOLE または/SUBSYSTEM: WINDOWS を使用します。

[/SUBSYSTEM:](../../build/reference/subsystem-specify-subsystem.md) 次の1つまたは複数を直接使用する Windows (Win32) アプリケーションをビルドするときに、NATIVE が指定されました。

- kernel32.dll

- gdi32.dll

- user32.dll

- msvcrt.dll dll の1つ \* 。

**/SUBSYSTEM: NATIVE** を指定せずに、この警告を解決してください。
