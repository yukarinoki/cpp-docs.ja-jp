---
description: 詳細については、「Math Error M6201」を参照してください。
title: 数値演算エラー M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 03588b7eed580b95cb263f6e4d71f5a793f4d392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244317"
---
# <a name="math-error-m6201"></a>数値演算エラー M6201

' function ': _DOMAIN エラー

指定された関数の引数が、その関数の有効な入力値のドメイン外にありました。

## <a name="example"></a>例

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

このエラーは、関数 `_matherr` 名、引数、およびエラーの種類を使用して関数を呼び出します。 関数を書き直して、 `_matherr` 特定の実行時の浮動小数点演算エラーの処理をカスタマイズすることができます。
