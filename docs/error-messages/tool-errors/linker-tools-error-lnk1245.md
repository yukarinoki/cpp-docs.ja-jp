---
title: リンカ ツール エラー LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 4cf9a6c4356872b727a10a360396e51e38928b29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505483"
---
# <a name="linker-tools-error-lnk1245"></a>リンカ ツール エラー LNK1245

無効なサブシステム 'サブシステム' が指定されます。/WINDOWS、WINDOWSCE、またはコンソール サブシステムがある必要があります。

[/clr](../../build/reference/clr-common-language-runtime-compilation.md)オブジェクトをコンパイルするために使用された、次の条件のいずれかの条件が true だったとします。

- カスタム エントリ ポイントが定義されている ([/ENTRY](../../build/reference/entry-entry-point-symbol.md)) ようなリンカーのサブシステムを推測できませんでした。

- 値が渡された、 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) /clr オブジェクトに対して有効でないリンカー オプション。

どちらの場合は、解像度は、/SUBSYSTEM リンカー オプションに有効な値を指定します。