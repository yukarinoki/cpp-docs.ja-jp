---
title: 致命的なエラー C1002 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f08255484b11f9f5d87fb67ac8ac7b401d4f6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044146"
---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002

パス 2 の実行中に、ヒープ領域を使い果たしました。

コンパイラは、可能性がありますが多すぎるのシンボルまたは複雑な式を使用してプログラムの 2 つ目のパスの中に動的メモリ領域が不足しています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ソース ファイルを複数の小さいファイルに分割します。

1. 式を小さな部分に分割します。

1. その他のプログラムまたはメモリを消費するドライバーを削除します。