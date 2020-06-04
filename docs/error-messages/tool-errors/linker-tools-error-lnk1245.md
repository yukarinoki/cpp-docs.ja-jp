---
title: リンカ ツール エラー LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 19e3f820b5bd7fdd8eac2f7b5a96fb5923ae0b92
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183801"
---
# <a name="linker-tools-error-lnk1245"></a>リンカ ツール エラー LNK1245

無効なサブシステム ' subsystem ' が指定されました。/SUBSYSTEM は WINDOWS、WINDOWSCE、または CONSOLE である必要があります

オブジェクトをコンパイルするために[/clr](../../build/reference/clr-common-language-runtime-compilation.md)が使用され、次のいずれかの条件が満たされました。

- カスタムエントリポイント ([/entry](../../build/reference/entry-entry-point-symbol.md)) が定義されました。そのため、リンカーはサブシステムを推論できませんでした。

- /Clr オブジェクトに対して無効な[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)リンカーオプションに値が渡されました。

どちらの場合も、/SUBSYSTEM リンカーオプションに有効な値を指定することが解決策となります。
