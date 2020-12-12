---
description: 詳細については、「コンパイラエラー C3156」を参照してください。
title: コンパイラエラー C3156
ms.date: 11/04/2016
f1_keywords:
- C3156
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
ms.openlocfilehash: 265e887a7d075267e7a46d47d6bae9621bd83656
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174144"
---
# <a name="compiler-error-c3156"></a>コンパイラエラー C3156

'class' : マネージド型または WinRT 型のローカル定義を持つことができません

関数に、マネージド型または WinRT 型のクラス、構造体、インターフェイスの定義 (宣言) を含めることはできません。

## <a name="example"></a>例

次の例では C3156 が生成されます。

```cpp
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
