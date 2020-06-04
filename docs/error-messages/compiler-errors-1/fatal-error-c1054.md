---
title: 致命的なエラー C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: d094d0892d43a5f9894f03538f72e59b57bad6db
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204465"
---
# <a name="fatal-error-c1054"></a>致命的なエラー C1054

コンパイラの制限: 初期化子の入れ子のレベルが深すぎます。

このコードは初期化子の入れ子の制限を超えています (初期化される型の組み合わせによっては10-15 レベル)。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. 入れ子を減らすために、初期化されるデータ型を簡略化します。

1. 宣言の後に、個別のステートメントで変数を初期化します。
