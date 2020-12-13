---
description: 詳細については、「コンパイラエラー C2461」を参照してください。
title: コンパイラ エラー C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: 788c8e475bd38b829ca8426137569a5d8a083f18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341829"
---
# <a name="compiler-error-c2461"></a>コンパイラ エラー C2461

> '*class*': コンストラクターの構文に仮パラメーターがありません。

クラスのコンストラクターに、仮引数が指定されていません。 コンストラクターの宣言では、仮パラメーターリストを指定する必要があります。 一覧は空にすることができます。

この問題を解決するには、 *class*::**クラス* の宣言の後にかっこのペアを追加します。

## <a name="example"></a>例

次の例は、C2461 を修正する方法を示しています。

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```
