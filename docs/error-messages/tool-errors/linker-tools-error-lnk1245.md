---
title: リンカ ツール エラー LNK1245 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef7bace5cec937399d7a2ed440e21b9b751f4141
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041793"
---
# <a name="linker-tools-error-lnk1245"></a>リンカ ツール エラー LNK1245

無効なサブシステム 'サブシステム' が指定されます。/WINDOWS、WINDOWSCE、またはコンソール サブシステムがある必要があります。

[/clr](../../build/reference/clr-common-language-runtime-compilation.md)オブジェクトをコンパイルするために使用された、次の条件のいずれかの条件が true だったとします。

- カスタム エントリ ポイントが定義されている ([/ENTRY](../../build/reference/entry-entry-point-symbol.md)) ようなリンカーのサブシステムを推測できませんでした。

- 値が渡された、 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) /clr オブジェクトに対して有効でないリンカー オプション。

どちらの場合は、解像度は、/SUBSYSTEM リンカー オプションに有効な値を指定します。