---
description: 詳細については、「コンパイラエラー C3194」を参照してください。
title: コンパイラエラー C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 7513b9d4964b6eb0024c3b51480f188243bf2637
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174040"
---
# <a name="compiler-error-c3194"></a>コンパイラエラー C3194

' member ': 値型に代入演算子を指定することはできません

コピーコンストラクターやコピー代入演算子など、コンパイラによる自動呼び出しを必要とする特殊なメンバー関数は、値クラス内ではサポートされていません。

## <a name="example"></a>例

次の例では、C3194 が生成されます。

```cpp
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```
