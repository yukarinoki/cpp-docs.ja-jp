---
title: リンカ ツール エラー LNK2027 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 022e363af575e29e3085dcaec21257fa7e4ab5f1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116848"
---
# <a name="linker-tools-error-lnk2027"></a>リンカ ツール エラー LNK2027

未解決のモジュール参照 ' module'

リンカーに渡されたファイルで指定されているモジュールに依存関係を持つ **/ASSEMBLYMODULE**もリンカーに直接渡されません。

LNK2027 を解決するには、次のいずれかの操作を行います。

- 処理されないリンカーにモジュールの依存関係を含むファイル。

- 使用して、モジュールの指定 **/ASSEMBLYMODULE**します。

- モジュールが安全な .netmodule の場合は、リンカーに直接モジュールを渡します。

詳細については、次を参照してください。 [/ASSEMBLYMODULE (MSIL モジュールのアセンブリへの追加)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)と[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)します。