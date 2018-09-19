---
title: 致命的なエラー C1054 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 439019b1f510127ae54e77d445d59e86be09a49b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101970"
---
# <a name="fatal-error-c1054"></a>致命的なエラー C1054

コンパイラの制限: 初期化子の入れ子レベルが深すぎます

コードは、初期化子 (初期化されている型の組み合わせによっては 10 ~ 15 レベル) では、入れ子の上限を超えています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 入れ子の削減に初期化されているデータ型を簡略化します。

1. 宣言の後に別のステートメントで変数を初期化します。