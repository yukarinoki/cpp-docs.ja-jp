---
title: リンカ ツール エラー LNK1302 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc85b37d58e12602c02c2207c1f38bda9344e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045511"
---
# <a name="linker-tools-error-lnk1302"></a>リンカ ツール エラー LNK1302

安全な .netmodule は; をリンクのみをサポートします.netmodule のファイルをリンクできません。

.Netmodule (でコンパイルされた **/LN**) を呼び出す MSIL リンク ユーザーの試行時に、リンカーに渡されました。  C++ モジュールは、MSIL にコンパイルする場合のリンクの有効な **/clr:safe**します。

このエラーを修正するとコンパイル **/clr:safe** MSIL がリンクを有効にまたはパス、 **/clr**または **/clr: 純粋な**モジュールではなく、リンカーを .obj ファイル。

詳細については、次のトピックを参照してください。

- [/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)

- [.netmodule ファイル (リンカー入力)](../../build/reference/netmodule-files-as-linker-input.md)