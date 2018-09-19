---
title: リソース コンパイラの致命的なエラー RW1025 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW1025
dev_langs:
- C++
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bf7bdeed320c004ffb75fa1d25d9b89147b0c13
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117401"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>リソース コンパイラの致命的なエラー RW1025

ここまでのヒープのメモリ不足

領域が多すぎるをしている可能性がありますのあるメモリに常駐するソフトウェアを確認します。 あるメモリの量を確認するには、CHKDSK プログラムを使用します。

大規模なリソース ファイルを作成する場合は、リソース スクリプトを 2 つのファイルに分割します。 2 つの .res ファイルを作成した後に、それらを結合するのに MS-DOS のコマンドラインを使用します。

```
copy first.res /b + second.res /b full.res
```