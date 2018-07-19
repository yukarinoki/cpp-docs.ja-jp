---
title: リンカ ツール エラー LNK1302 |Microsoft ドキュメント
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
ms.openlocfilehash: 6aa84a411f91303c84acb44e2e6c0ab3d975e19f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299420"
---
# <a name="linker-tools-error-lnk1302"></a>リンカ ツール エラー LNK1302
安全な .netmodule; のリンクのみをサポートします。ファイル .netmodule にリンクすることができません。  
  
 .Netmodule (でコンパイルされた **/LN**) が、ユーザーで MSIL のリンクを起動するために、リンカーに渡されました。  C++ モジュールと MSIL にコンパイルする場合のリンクに対して有効では、 **/clr:safe**です。  
  
 このエラーを修正するコンパイル時に **/clr:safe** MSIL リンクすると、有効にするにまたはパス、 **/clr**または **/clr: 純粋な**モジュールの代わりにリンカーを .obj ファイル。  
  
 詳細については、次のトピックを参照してください。  
  
-   [/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)  
  
-   [.netmodule ファイル (リンカー入力)](../../build/reference/netmodule-files-as-linker-input.md)