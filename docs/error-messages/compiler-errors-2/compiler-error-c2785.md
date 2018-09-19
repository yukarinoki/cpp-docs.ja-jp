---
title: コンパイラ エラー C2785 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfae8a58d9c42c9ddc3ef7779fc86f7157ba41b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080858"
---
# <a name="compiler-error-c2785"></a>コンパイラ エラー C2785

'declaration1' と 'declaration2' 異なる戻り値の型があります。

関数テンプレートの特殊化の戻り値の型は、プライマリ関数テンプレートの戻り値の型によって異なります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 一貫性を保つのための関数テンプレートのすべての特殊化を確認します。

## <a name="example"></a>例

次の例では、C2785 が生成されます。

```
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```