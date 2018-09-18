---
title: コンパイラ エラー C2512 |Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba1fbba98237879927fd82d6535c0c2688c1c304
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036922"
---
# <a name="compiler-error-c2512"></a>コンパイラ エラー C2512

> '*識別子*': 使用可能なない適切な既定コンス トラクター

A*既定のコンス トラクター*引数を必要としないコンス トラクターが指定したクラス、構造体または共用体のご利用いただけません。 コンパイラでは、ユーザー定義のコンス トラクターが指定されていない場合にのみ、既定のコンス トラクターが用意されています。

Void 以外のパラメーターを受け取るコンス トラクターを提供する、パラメーターなしで (たとえば、配列の要素) として作成するのには、クラスを許可する場合は、既定のコンス トラクターを指定する必要もあります。 既定のコンストラクターには、すべてのパラメーターに既定値を使用したコンストラクターを指定できます。

## <a name="example"></a>例

エラー C2512 の一般的な原因は、引数を受け取るクラスまたは構造体コンス トラクターを定義するときに、クラスまたは構造体引数なしのインスタンスを宣言しようとしました。 たとえば、`struct B`以下が必要なコンス トラクターを宣言、`char *`引数が、引数を受け取らないことのないです。 `main`B のインスタンスが宣言されているが、引数が指定されていません。 B. の既定のコンス トラクターが見つからないため、コンパイラは C2512 を生成します

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

など、構造体またはクラスでは、既定のコンス トラクターを定義することでこの問題を解決する`B() {}`、またはコンス トラクターが、既定値を持つすべての引数など`B (char * = nullptr) {}`します。
