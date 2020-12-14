---
description: 詳細については、「コンパイラエラー C3672」を参照してください。
title: コンパイラ エラー C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: aea8a03e409e1144985cb7b94dcca94975d58db5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228821"
---
# <a name="compiler-error-c3672"></a>コンパイラ エラー C3672

擬似デストラクター式は、関数呼び出しの一部としてのみ使用できます

デストラクターが正しく呼び出されませんでした。  詳細については、「 [デストラクター](../../cpp/destructors-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3672 が生成されます。

```cpp
// C3672.cpp
template<typename T>
void f(T* pT) {
   &pT->T::~T;   // C3672
   pT->T::~T();   // OK
};

int main() {
   int i;
   f(&i);
}
```
