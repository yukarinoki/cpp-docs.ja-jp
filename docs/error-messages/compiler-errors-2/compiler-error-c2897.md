---
description: 詳細については、「コンパイラエラー C2897」を参照してください。
title: コンパイラ エラー C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: b1a1f66987aa4bbd01fdf12f88f8933e3436938a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270876"
---
# <a name="compiler-error-c2897"></a>コンパイラ エラー C2897

デストラクターまたはファイナライザーを関数テンプレートにすることはできません

デストラクターまたはファイナライザーはオーバーロードできないので、デストラクターをテンプレートとして宣言する (デストラクターのセットを定義する) ことはできません。

## <a name="examples"></a>例

次の例では、C2897 が生成されます。

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

次の例では、C2897 が生成されます。

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```
