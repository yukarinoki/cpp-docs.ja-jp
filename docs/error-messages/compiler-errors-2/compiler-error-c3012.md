---
title: コンパイラ エラー C3012 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99bdac5ffb75978479ae7ef420a48b3d1b2f8e64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46063672"
---
# <a name="compiler-error-c3012"></a>コンパイラ エラー C3012

> '*組み込み*': 組み込み関数は、並行領域内で直接許可されていません

A[コンパイラ組み込み](../../intrinsics/compiler-intrinsics.md)で関数が許可されていません、`omp parallel`リージョン。 この問題を修正するには、組み込み関数をリージョンの外に移動または非組み込みと同等に置き換えます。

## <a name="example"></a>例

次の例では、C3012 を生成し、その修正方法を示しています。

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```