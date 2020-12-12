---
description: 詳細については、「リンカツール Error LNK1245」を参照してください。
title: リンカ ツール エラー LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 3903651992f8fb79c3a79e4f2afc9d84e70e8126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193904"
---
# <a name="linker-tools-error-lnk1245"></a>リンカ ツール エラー LNK1245

無効なサブシステム ' subsystem ' が指定されました。/SUBSYSTEM は WINDOWS、WINDOWSCE、または CONSOLE である必要があります

オブジェクトをコンパイルするために[/clr](../../build/reference/clr-common-language-runtime-compilation.md)が使用され、次のいずれかの条件が満たされました。

- カスタムエントリポイント ([/entry](../../build/reference/entry-entry-point-symbol.md)) が定義されました。そのため、リンカーはサブシステムを推論できませんでした。

- /Clr オブジェクトに対して無効な [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) リンカーオプションに値が渡されました。

どちらの場合も、/SUBSYSTEM リンカーオプションに有効な値を指定することが解決策となります。
