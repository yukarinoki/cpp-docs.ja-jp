---
title: コンパイラ エラー C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: 36048f3e4b8cc1be3e766f11b5c131513a3365da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436778"
---
# <a name="compiler-error-c3672"></a>コンパイラ エラー C3672

擬似デストラクター式は、関数呼び出しの一部としてのみ使用できます。

デストラクターが正しく呼び出されませんでした。  詳細については、[デストラクター](../../cpp/destructors-cpp.md)を参照してください。

## <a name="example"></a>例

次の例では、C3672 が生成されます。

```
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