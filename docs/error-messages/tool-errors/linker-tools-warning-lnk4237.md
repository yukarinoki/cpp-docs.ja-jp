---
title: リンカー ツールの警告 LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: aaa26393f1ce76d3e1bc40e5ba4978d1bcdb4fc9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193759"
---
# <a name="linker-tools-warning-lnk4237"></a>リンカー ツールの警告 LNK4237

/SUBSYSTEM: ' dll ' からインポートするときにネイティブに指定されました。/SUBSYSTEM: CONSOLE または/SUBSYSTEM: WINDOWS を使用します。

[/SUBSYSTEM:](../../build/reference/subsystem-specify-subsystem.md)次の1つまたは複数を直接使用する Windows (Win32) アプリケーションをビルドするときに、NATIVE が指定されました。

- kernel32.dll

- gdi32

- user32.dll

- msvcrt.dll\* dll の1つ。

**/SUBSYSTEM: NATIVE**を指定せずに、この警告を解決してください。
