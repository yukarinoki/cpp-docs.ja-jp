---
title: 致命的なエラー C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: 78edf886f34665f996497abe323a0ea5d3800c2d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204933"
---
# <a name="fatal-error-c1002"></a>致命的なエラー C1002

パス 2 の実行中に、ヒープ領域を使い果たしました。

コンパイラは、2番目のパス中に動的メモリ空間を使い果たしました。これは、シンボルや複雑な式が多すぎるプログラムが原因である可能性があります。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. ソースファイルを複数の小さなファイルに分割します。

1. 式を小さな部分式に分割します。

1. メモリを使用する他のプログラムやドライバーを削除します。
