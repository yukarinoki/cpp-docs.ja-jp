---
description: 詳細については、「コンパイラエラー C2512」を参照してください。
title: コンパイラ エラー C2512
ms.date: 02/09/2018
f1_keywords:
- C2512
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
ms.openlocfilehash: 40574ab7fc54ba678729429401ed14fefefe9ebd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212910"
---
# <a name="compiler-error-c2512"></a>コンパイラ エラー C2512

> '*identifier*': 適切な既定のコンストラクターを使用できません

*既定のコンストラクター*(引数を必要としないコンストラクター) は、指定されたクラス、構造体、または共用体では使用できません。 コンパイラは、ユーザー定義のコンストラクターが指定されていない場合にのみ、既定のコンストラクターを提供します。

Void 以外のパラメーターを受け取るコンストラクターを指定し、パラメーターを指定せずにクラスを作成できるようにする場合 (たとえば、配列の要素として)、既定のコンストラクターも指定する必要があります。 既定のコンストラクターには、すべてのパラメーターに既定値を使用したコンストラクターを指定できます。

## <a name="example"></a>例

エラー C2512 の一般的な原因は、引数を受け取るクラスまたは構造体のコンストラクターを定義するときに、引数を指定せずにクラスまたは構造体のインスタンスを宣言しようとしたときです。 たとえば、次の例では、引数を必要とする `struct B` が、引数を受け取らないコンストラクターを宣言して `char *` います。 で `main` は、B のインスタンスが宣言されていますが、引数が指定されていません。 コンパイラは、B の既定のコンストラクターを見つけることができないため、C2512 を生成します。

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

この問題を解決するには、構造体またはクラスの既定のコンストラクター (など)、 `B() {}` またはすべての引数に既定値が設定されているコンストラクター (など) を定義し `B (char * = nullptr) {}` ます。
