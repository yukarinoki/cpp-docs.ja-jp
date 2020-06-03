---
title: リンカ ツール エラー LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: 0c531f70f98a017e8b75cceddc684f99d33bc554
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194598"
---
# <a name="linker-tools-error-lnk2027"></a>リンカ ツール エラー LNK2027

未解決のモジュール参照 ' module '

リンカーに渡されたファイルが、 **/assemblyモジュール**で指定されていないか、リンカーに直接渡されていないモジュールに依存しています。

LNK2027 を解決するには、次のいずれかの操作を行います。

- モジュールの依存関係があるファイルをリンカーに渡さないでください。

- **/Assemblymodule**を使用してモジュールを指定します。

- モジュールが安全な .netmodule である場合は、リンカーに直接モジュールを渡します。

詳細については、「 [assemblymodule (アセンブリへの MSIL モジュールの追加)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) 」および「[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。
