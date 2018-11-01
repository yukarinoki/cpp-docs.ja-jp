---
title: コンパイラ エラー C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 181a18dde45c3363f1f77bc0cbbd5b0ffca3e898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608907"
---
# <a name="compiler-error-c3194"></a>コンパイラ エラー C3194

'member': 値型は、代入演算子を含めることはできません

コピー コンス トラクターまたはコピー代入演算子など、コンパイラによって自動起動を必要とする特殊なメンバー関数は値クラス内ではサポートされていません。

## <a name="example"></a>例

次の例では、C3194 が生成されます。

```
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```