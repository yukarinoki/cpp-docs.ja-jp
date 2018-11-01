---
title: 致命的なエラー C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 0bfd0c03378b1a9c616a014ac96153b3ab04af9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569202"
---
# <a name="fatal-error-c1054"></a>致命的なエラー C1054

コンパイラの制限: 初期化子の入れ子レベルが深すぎます

コードは、初期化子 (初期化されている型の組み合わせによっては 10 ~ 15 レベル) では、入れ子の上限を超えています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 入れ子の削減に初期化されているデータ型を簡略化します。

1. 宣言の後に別のステートメントで変数を初期化します。