---
description: 詳細については、「コンパイラエラー C2474」を参照してください。
title: コンパイラ エラー C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: adbfce63a5a8d97707bfb8e73dfda265f5d5e328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164407"
---
# <a name="compiler-error-c2474"></a>コンパイラ エラー C2474

'keyword' : 隣接するセミコロンがありません。キーワードまたは識別子のどちらかである可能性があります。

コンパイラでセミコロンが検出される必要があったため、ユーザーの意図は認識されませんでした。 このエラーを解決するには、セミコロンを追加します。

## <a name="example"></a>例

次の例では C2474 が生成されます。

```cpp
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```
