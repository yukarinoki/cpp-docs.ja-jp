---
description: '詳細情報: 前置インクリメント演算子と前置デクリメント演算子'
title: 前置インクリメント演算子と前置デクリメント演算子
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, types of
- decrement operators, syntax
- decrement operators
ms.assetid: 9a441bb9-d94a-4b6a-9db2-0d0d76bc480d
ms.openlocfilehash: 49edad72bb0dea25166c1508680c4757c89927f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312502"
---
# <a name="prefix-increment-and-decrement-operators"></a>前置インクリメント演算子と前置デクリメント演算子

単項演算子 (`++` と **--** ) は、インクリメントまたはデクリメント演算子がオペランドの前にある場合、"プレフィックス" インクリメントまたはデクリメント演算子と呼ばれます。 後置インクリメント/デクリメントは、前置インクリメント/デクリメントよりも優先されます。 オペランドは、整数型、浮動小数点型、またはポインター型であり、変更可能な左辺値式 ( **`const`** 属性のない式) である必要があります。 結果は左辺値です。

演算子がオペランドの前にある場合は、オペランドがインクリメントまたはデクリメントされて、新しい値が式の結果になります。

整数または浮動小数点型のオペランドは、整数値 1 ずつインクリメントまたはデクリメントされます。 結果の型は、オペランドの型と同じです。 ポインター型のオペランドは、アドレス指定するオブジェクトのサイズだけインクリメントまたはデクリメントされます。 インクリメントされたポインターは、次のオブジェクトを指します。デクリメントされたポインターは、前のオブジェクトを指します。

## <a name="example"></a>例

この例では、単項プレフィックス デクリメント演算子を示しています。

```
if( line[--i] != '\n' )
    return;
```

この例では、変数 `i` は、`line` への添字として使用される前にデクリメントされます。

## <a name="see-also"></a>関連項目

[C 単項演算子](../c-language/c-unary-operators.md)
