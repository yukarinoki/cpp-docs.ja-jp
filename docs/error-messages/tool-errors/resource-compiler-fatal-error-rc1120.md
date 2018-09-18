---
title: リソース コンパイラの致命的なエラー RC1120 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f28e381d4eac0bfd1f010ef3919452635a1b96
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057003"
---
# <a name="resource-compiler-fatal-error-rc1120"></a>リソース コンパイラの致命的なエラー RC1120

メモリ不足に必要なバイト数です。

リソース コンパイラは、ストレージ、ヒープに格納されたアイテムの不足になりました。 通常、これは、シンボルが多すぎる場合の結果です。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. Windows のスワップ ファイルの領域を増やします。 スワップ ファイルの領域を増やす方法の詳細については、Windows のヘルプ内の仮想メモリを参照してください。

1. 不要インクルード ファイル、特に不要な`#define`s と関数のプロトタイプ。

1. 2 つ以上のファイルに、現在のファイルに分割し、個別にコンパイルします。

1. 他のプログラムや、システムでは、大量のメモリを消費する可能性がありますで実行されているドライバーを削除します。