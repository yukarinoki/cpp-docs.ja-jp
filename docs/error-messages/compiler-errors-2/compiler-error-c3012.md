---
description: 詳細については、「コンパイラエラー C3012」を参照してください。
title: コンパイラ エラー C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: fff986a984acb62f770d02ff2b7b08c40e8511e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286008"
---
# <a name="compiler-error-c3012"></a>コンパイラ エラー C3012

> '*組み込み*': 組み込み関数は、並列領域内で直接使用することはできません

[コンパイラ組み込み関数](../../intrinsics/compiler-intrinsics.md) は、 `omp parallel` 領域では使用できません。 この問題を解決するには、組み込みをリージョン外に移動するか、組み込みの同等ではないものに置き換えます。

## <a name="example"></a>例

次の例では、C3012 を生成し、その修正方法の1つを示しています。

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
