---
description: '詳細情報: 致命的なエラー C1509'
title: 致命的なエラー C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: dc2483ae96f599912b3ba6d1594257fec81ac251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276349"
---
# <a name="fatal-error-c1509"></a>致命的なエラー C1509

コンパイラの制限: 関数 ' function ' の例外ハンドラーの状態が多すぎます。 関数の簡略化

このコードは、例外ハンドラーの状態 (32768 状態) の内部制限を超えています。

最も一般的な原因は、関数にユーザー定義のクラス変数と算術演算子の複雑な式が含まれていることです。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 一時変数に共通の部分式を割り当てることにより、式を簡略化します。

1. 関数を小さな関数に分割します。
