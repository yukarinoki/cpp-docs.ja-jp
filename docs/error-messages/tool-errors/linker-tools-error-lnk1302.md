---
description: 詳細については、「リンカツール Error LNK1302」を参照してください。
title: リンカ ツール エラー LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 33e9a406cde7910c7340fdfe256711c47eee45cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193696"
---
# <a name="linker-tools-error-lnk1302"></a>リンカ ツール エラー LNK1302

netmodule のリンクのみをサポートしています。ファイルをリンクできません。 .netmodule

**/LN** を使用してコンパイルされた .netmodule が、ユーザーが MSIL リンクを呼び出そうとしたときにリンカーに渡されました。  C++ モジュールは、 **/clr: safe** を使用してコンパイルされている場合、MSIL リンクに対して有効です。

このエラーを修正するには、 **/clr: safe** を使用してコンパイルして MSIL リンクを有効にするか、 **/clr** または **/clr: pure** .obj ファイルをモジュールではなくリンカーに渡します。

詳細については、「

- [/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)

- [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)
