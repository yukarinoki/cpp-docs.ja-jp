---
description: '詳細情報: 致命的なエラー C1002'
title: 致命的なエラー C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: edd4ffbd6ce4c8a7f70640619d8dc52775dd0195
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262712"
---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002

パス 2 の実行中に、ヒープ領域を使い果たしました。

コンパイラは、2番目のパス中に動的メモリ空間を使い果たしました。これは、シンボルや複雑な式が多すぎるプログラムが原因である可能性があります。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ソースファイルを複数の小さなファイルに分割します。

1. 式を小さな部分式に分割します。

1. メモリを使用する他のプログラムやドライバーを削除します。
