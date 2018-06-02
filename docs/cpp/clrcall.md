---
title: _ _clrcall |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __clrcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __clrcall keyword [C++]
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4012eac44f376ccdeeb57227e562c672f6ba7ffe
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704582"
---
# <a name="clrcall"></a>__clrcall

**Microsoft 固有の仕様**

関数がマネージ コードからのみ呼び出されることを指定します。  マネージ コードからのみ呼び出されるすべての仮想関数では `__clrcall` を使用します。 ただし、この呼び出し規則は、ネイティブ コードから呼び出される関数には使用できません。

マネージ関数から仮想マネージ関数を呼び出す場合、またはマネージ関数からポインターを使用してマネージ関数を呼び出す場合は、`__clrcall` を使用してパフォーマンスを向上させます。

エントリ ポイントはコンパイラが生成した個別の関数です。 関数にネイティブ エントリ ポイントとマネージ エントリ ポイントがある場合、そのいずれかが、関数実装を持つ実際の関数になります。 もう一方の関数は実際の関数に呼び出す別の関数 (サンク) で、共通言語ランタイムに PInvoke を実行させます。 関数を `__clrcall` としてマークすると、関数の実装が MSIL である必要があり、ネイティブ エントリ ポイント関数が生成されないことを示します。

`__clrcall` が指定されていない場合にネイティブ関数のアドレスを取得すると、コンパイラはネイティブ エントリ ポイントを使用します。 `__clrcall` は、関数が管理され、マネージ コードからネイティブへの遷移を行う必要がないことを示します。 その場合、コンパイラはマネージ エントリ ポイントを使用します。

ときに **/clr** (いない **/clr: 純粋な**または **/clr:safe**) を使用し、`__clrcall`はネイティブ エントリのアドレスを返す関数のアドレスを常に実行を使用しません。関数をポイントします。 `__clrcall` を使用すると、ネイティブ エントリ ポイント関数が作成されないため、エントリ ポイント サンク関数ではなくマネージ関数のアドレスを取得します。 詳細については、次を参照してください。[ダブル サンキング](../dotnet/double-thunking-cpp.md)です。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションが Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)すべての関数と関数ポインターがあることを意味`__clrcall`、コンパイラとしてマークするもの以外のコンパイル単位内で関数を許可しないと`__clrcall`です。 ときに **/clr: 純粋な**を使用する`__clrcall`関数ポインターと外部宣言でのみ指定することができます。

直接呼び出すことができます`__clrcall`関数を使用してコンパイルされた既存の C++ コードから **/clr**その関数が MSIL を実装します。 `__clrcall` これらの関数がコンパイルされる場合でも、関数をインライン asm を持ち、たとえば、CPU 固有の組み込みを呼び出してから直接関数を呼び出すことができません **/clr**です。

`__clrcall` 関数ポインターだけが、作成されたアプリケーション ドメインで使用されるようになっています。  アプリケーション ドメインを越えて `__clrcall` 関数ポインターを渡すのではなく、<xref:System.CrossAppDomainDelegate> を使用します。 詳細については、次を参照してください。[アプリケーション ドメインと Visual c](../dotnet/application-domains-and-visual-cpp.md)です。

## <a name="example"></a>例

関数が `__clrcall` で宣言されている場合、必要に応じて (関数が呼び出された場合など) コードが生成されることに注意してください。

```cpp
// clrcall2.cpp
// compile with: /clr
using namespace System;
int __clrcall Func1() {
   Console::WriteLine("in Func1");
   return 0;
}

// Func1 hasn't been used at this point (code has not been generated),
// so runtime returns the adddress of a stub to the function
int (__clrcall *pf)() = &Func1;

// code calls the function, code generated at difference address
int i = pf();   // comment this line and comparison will pass

int main() {
   if (&Func1 == pf)
      Console::WriteLine("&Func1 == pf, comparison succeeds");
   else
      Console::WriteLine("&Func1 != pf, comparison fails");

   // even though comparison fails, stub and function call are correct
   pf();
   Func1();
}
```

```Output
in Func1
&Func1 != pf, comparison fails
in Func1
in Func1
```

## <a name="example"></a>例

次のサンプルでは、関数ポインターが管理されたコードからのみ呼び出されるように、関数ポインターを定義する方法を示します。 これにより、コンパイラはマネージ関数を直接呼び出し、ネイティブ エントリ ポイント (ダブル サンクの問題) を避けることができます。

```cpp
// clrcall3.cpp
// compile with: /clr
void Test() {
   System::Console::WriteLine("in Test");
}

int main() {
   void (*pTest)() = &Test;
   (*pTest)();

   void (__clrcall *pTest2)() = &Test;
   (*pTest2)();
}
```

## <a name="see-also"></a>関連項目

- [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)
- [キーワード](../cpp/keywords-cpp.md)
