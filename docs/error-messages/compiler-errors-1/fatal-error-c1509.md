---
title: 致命的なエラー C1509 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 837ab5b7cf76b724726c6c52fbfe974d4da6ca85
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033135"
---
# <a name="fatal-error-c1509"></a>致命的なエラー C1509

コンパイラの制限: 関数 'function' の例外ハンドラが多すぎます。 関数を簡略化します。

コードは、例外ハンドラーの状態 (32,768 状態) での内部制限値を超えています。

最も一般的な原因は、関数がクラスのユーザー定義変数および算術演算子の複雑な式が含まれています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 一時変数に共通部分式を割り当てることで式を簡略化します。

1. 関数を小さな関数に分割します。