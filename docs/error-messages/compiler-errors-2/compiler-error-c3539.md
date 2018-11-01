---
title: コンパイラ エラー C3539
ms.date: 11/04/2016
f1_keywords:
- C3539
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
ms.openlocfilehash: 7cba9e0271d16420c5cfe4adbed2c7121d139d8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523922"
---
# <a name="compiler-error-c3539"></a>コンパイラ エラー C3539

'type': テンプレート引数は 'auto' を含む型をすることはできません

指定されたテンプレート引数の型の使用状況を含めることはできません、`auto`キーワード。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. テンプレート引数を指定して、`auto`キーワード。

## <a name="example"></a>例

次の例では、C3539 を生成します。

```
// C3539.cpp
// Compile with /Zc:auto
template<class T> class C{};
int main()
{
   C<auto> c;   // C3539
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)