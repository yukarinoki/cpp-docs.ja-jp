---
title: リンカ ツール エラー LNK1223 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1223
dev_langs:
- C++
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e50d29af6ac563fadd3a52e5b1d3d15201289083
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298653"
---
# <a name="linker-tools-error-lnk1223"></a>リンカ ツール エラー LNK1223
ファイルが無効かまたは壊れています: ファイルに無効な .pdata のコントリビューションが含まれています。  
  
 pdata を使用する RISC プラットフォームにおいては、コンパイラによって出力された .pdata セクションのエントリが並べ替えられていない場合に、このエラーが発生します。  
  
 この問題を解決するには、なしでコンパイルしてください[/GL (プログラム全体の最適化)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md)有効にします。 また、このエラーは、関数本体が空である場合にも発生することがあります。