---
title: リンカ ツール エラー LNK1223 |Microsoft Docs
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
ms.openlocfilehash: 8639919c74559829367108b36d62594e2a83a91a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067991"
---
# <a name="linker-tools-error-lnk1223"></a>リンカ ツール エラー LNK1223

ファイルが無効かまたは壊れています: ファイルに無効な .pdata のコントリビューションが含まれています。

pdata を使用する RISC プラットフォームにおいては、コンパイラによって出力された .pdata セクションのエントリが並べ替えられていない場合に、このエラーが発生します。

この問題を解決するには、なしでコンパイルしてください[/GL (Whole Program Optimization)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md)を有効にします。 また、このエラーは、関数本体が空である場合にも発生することがあります。