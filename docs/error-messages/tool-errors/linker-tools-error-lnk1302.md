---
title: リンカ ツール エラー LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: 8323fa234851ce3ba12083adb74d5ee0fba0ac69
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194929"
---
# <a name="linker-tools-error-lnk1302"></a>リンカ ツール エラー LNK1302

netmodule のリンクのみをサポートしています。ファイルをリンクできません。 .netmodule

**/LN**を使用してコンパイルされた .netmodule が、ユーザーが MSIL リンクを呼び出そうとしたときにリンカーに渡されました。  モジュールC++は、 **/clr: safe**を使用してコンパイルされている場合、MSIL リンクに対して有効です。

このエラーを修正するには、 **/clr: safe**を使用してコンパイルして MSIL リンクを有効にするか、 **/clr**または **/clr: pure** .obj ファイルをモジュールではなくリンカーに渡します。

詳細については、「

- [/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)

- [.netmodule ファイル (リンカー入力)](../../build/reference/netmodule-files-as-linker-input.md)
