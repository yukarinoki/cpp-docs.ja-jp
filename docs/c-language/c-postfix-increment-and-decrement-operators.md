---
title: C 後置インクリメント演算子と後置デクリメント演算子
ms.date: 11/04/2016
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
ms.openlocfilehash: 8c2e3ba50ce3e768b377a588cd3e82ad29df79ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325576"
---
# <a name="c-postfix-increment-and-decrement-operators"></a>C 後置インクリメント演算子と後置デクリメント演算子

後置インクリメントと後置デクリメントのオペランドは、スカラー型の変更可能な左辺値です。

## <a name="syntax"></a>構文

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

後置インクリメントまたは後置デクリメントの演算結果は、オペランドの値になります。 結果が得られた後で、オペランドの値がインクリメント (またはデクリメント) されます。 次のコードは、後置インクリメント演算子を示しています。

```
if( var++ > 0 )
    *p++ = *q++;
```

この例では、変数 `var` は 0 と比較されてからインクリメントされます。 `var` がインクリメントされる前に正である場合は、次のステートメントが実行されます。 まず、`q` でポイントされるオブジェクトの値が `p` でポイントされるオブジェクトに代入されます。 次に、`q` と `p` がインクリメントされます。

## <a name="see-also"></a>関連項目

[後置インクリメント演算子と後置デクリメント演算子: ++ および --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)
