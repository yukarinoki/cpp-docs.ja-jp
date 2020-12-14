---
description: 詳細については、「リンカツール Error LNK2027」を参照してください。
title: リンカ ツール エラー LNK2027
ms.date: 11/04/2016
f1_keywords:
- LNK2027
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
ms.openlocfilehash: 006ca3b0c9d0ef85f118db9b562e8228c7cad238
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275764"
---
# <a name="linker-tools-error-lnk2027"></a>リンカ ツール エラー LNK2027

未解決のモジュール参照 ' module '

リンカーに渡されたファイルが、 **/assemblyモジュール** で指定されていないか、リンカーに直接渡されていないモジュールに依存しています。

LNK2027 を解決するには、次のいずれかの操作を行います。

- モジュールの依存関係があるファイルをリンカーに渡さないでください。

- **/Assemblymodule** を使用してモジュールを指定します。

- モジュールが安全な .netmodule である場合は、リンカーに直接モジュールを渡します。

詳細については、「 [assemblymodule (アセンブリへの MSIL モジュールの追加)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) 」および「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。
