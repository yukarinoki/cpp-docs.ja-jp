---
description: 詳細については、「コンパイラエラー C2472」を参照してください。
title: コンパイラ エラー C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: a1d4d668c1e7151771a2df85e888384c6c3ea028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164498"
---
# <a name="compiler-error-c2472"></a>コンパイラ エラー C2472

> '*function*' をマネージドコードで生成できません: '*message*';混合イメージを生成するために/clr を使用してコンパイルする

## <a name="remarks"></a>解説

このエラーは、純粋な共通言語ランタイム (CLR) の環境内で、マネージド コードでサポートされていない型を使用すると発生します。 エラーを解決するには、 **/clr** を使用してコンパイルします。

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

## <a name="example"></a>例

次の例では警告 C2472 が生成されます。

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>関連項目

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)
