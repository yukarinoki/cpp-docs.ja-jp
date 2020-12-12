---
description: 詳細については、「コンパイラエラー C2286」を参照してください。
title: コンパイラ エラー C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 89c8b69c42188d448fad0cd08287773d7a713d08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298462"
---
# <a name="compiler-error-c2286"></a>コンパイラ エラー C2286

' identifier ' 表現のメンバーへのポインターは既に ' 継承 ' に設定されています。宣言は無視されます

クラスには、2つの異なるメンバーに対する pointer-to-member 表現が存在します。

詳細については、「 [継承キーワード](../../cpp/inheritance-keywords.md)」を参照してください。

## <a name="example"></a>例

次の例では C2286 が生成されます。

```cpp
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
