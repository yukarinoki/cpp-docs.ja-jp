---
title: コンパイラ エラー C3539 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3539
dev_langs:
- C++
helpviewer_keywords:
- C3539
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b2f78b69e00290dcc283e3fc340d25a4a071776
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091882"
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