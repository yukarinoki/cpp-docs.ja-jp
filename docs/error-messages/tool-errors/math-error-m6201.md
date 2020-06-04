---
title: 数値演算エラー M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 0b1cd0d3fcd86a2174b19da41176dd97f547a295
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193707"
---
# <a name="math-error-m6201"></a>数値演算エラー M6201

' function ': _DOMAIN エラー

指定された関数の引数が、その関数の有効な入力値のドメイン外にありました。

## <a name="example"></a>例

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

このエラーは、関数名、引数、およびエラーの種類を使用して `_matherr` 関数を呼び出します。 `_matherr` 関数を書き直して、特定の実行時の浮動小数点演算エラーの処理をカスタマイズすることができます。
