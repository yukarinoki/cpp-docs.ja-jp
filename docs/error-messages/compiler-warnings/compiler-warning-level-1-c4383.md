---
title: コンパイラの警告 (レベル 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 61bc3951a7d57a5a4eefb69b5a0c4399df99160a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548799"
---
# <a name="compiler-warning-level-1-c4383"></a>コンパイラの警告 (レベル 1) C4383

'instance_dereference_operator': ユーザー定義の 'operator' 演算子が存在するときに、ハンドルの逆参照の意味を変更できますオペランドに対して明示的に指定する静的関数として、演算子を書き込み

マネージ型に逆参照演算子のインスタンスのユーザー定義の上書きを追加すると、ハンドルのオブジェクトを返す型の逆参照演算子の機能を無効可能性があります。 検討逆参照演算子の静的なユーザー定義を記述します。

詳細については、次を参照してください。[オブジェクト演算子 (^) へのハンドル](../../windows/handle-to-object-operator-hat-cpp-component-extensions.md)と[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)します。

また、インスタンス演算子では、参照されているメタデータを使用して他の言語コンパイラを使用できません。 詳細については、次を参照してください。[ユーザー定義演算子 (C +/cli CLI)](../../dotnet/user-defined-operators-cpp-cli.md)します。

## <a name="example"></a>例

次の例では、C4383 が生成されます。

```
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```