---
title: 致命的なエラー C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: 0588da99994be547742cc530ba435002a2d73359
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640506"
---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002

パス 2 の実行中に、ヒープ領域を使い果たしました。

コンパイラは、可能性がありますが多すぎるのシンボルまたは複雑な式を使用してプログラムの 2 つ目のパスの中に動的メモリ領域が不足しています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ソース ファイルを複数の小さいファイルに分割します。

1. 式を小さな部分に分割します。

1. その他のプログラムまたはメモリを消費するドライバーを削除します。