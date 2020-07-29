---
title: コンパイラの警告 (レベル 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: 66e782c2fbb9c39c6a189de496cd0dcb4f1f4991
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218079"
---
# <a name="compiler-warning-level-4-c4559"></a>コンパイラの警告 (レベル 4) C4559

> '*function*': 再定義します。関数は __declspec (*修飾子*) を取得します。

## <a name="remarks"></a>解説

関数が再定義または再宣言され、2番目の定義または宣言が **`__declspec`** 修飾子 (*修飾子*) を追加しました。 これは、情報提供の警告です。 この警告を修正するには、定義の1つを削除します。

## <a name="example"></a>例

次の例では、C4559 が生成されます。

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```
