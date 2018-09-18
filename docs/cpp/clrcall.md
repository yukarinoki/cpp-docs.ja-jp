---
title: _ _clrcall |Microsoft Docs
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
ms.openlocfilehash: 9631ac9beb0e6263ac1cf7e60e11e498aa4c7667
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019758"
---
# <a name="clrcall"></a>__clrcall

**Microsoft 固有の仕様**

関数がマネージド コードからのみ呼び出されることを指定します。  使用 **_ _clrcall**のマネージ コードからのみ呼び出されるすべての仮想関数。 ただし、この呼び出し規則は、ネイティブ コードから呼び出される関数には使用できません。

使用 **_ _clrcall**仮想マネージ関数をマネージ関数からまたはマネージ関数ポインターを通じてマネージ関数から呼び出すときにパフォーマンスを向上させる。

エントリ ポイントはコンパイラが生成した個別の関数です。 関数にネイティブ エントリ ポイントとマネージド エントリ ポイントがある場合、そのいずれかが、関数実装を持つ実際の関数になります。 もう一方の関数は実際の関数に呼び出す別の関数 (サンク) で、共通言語ランタイムに PInvoke を実行させます。 関数としてマークするときに **_ _clrcall**関数の実装が MSIL にする必要があり、ネイティブ エントリ ポイント関数が生成されないことを示します。

場合は、ネイティブ関数のアドレスを作成する際 **_ _clrcall**が指定されていない、コンパイラはネイティブ エントリ ポイントを使用します。 **_ _clrcall**関数が管理されからの移行を経由する必要があるがネイティブに管理対象があることを示します。 その場合、コンパイラはマネージド エントリ ポイントを使用します。

ときに`/clr`(いない`/clr:pure`または`/clr:safe`) は使用と **_ _clrcall**は、ネイティブ エントリ ポイント関数のアドレスを返しますを使用しない関数のアドレスを常に取得します。 ときに **_ _clrcall**が使用すると、ネイティブ エントリ ポイント関数は作成されず、いないエントリ ポイント サンク関数のマネージ関数のアドレスを取得するようにします。 詳細については、次を参照してください。[ダブル サンキング](../dotnet/double-thunking-cpp.md)します。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)すべての関数と関数ポインターがあることを意味 **_ _clrcall** 以外のものとしてマークするコンパイル単位内の関数が許可されず、コンパイラと **_ _clrcall**します。 ときに **/clr: 純粋な**を使用する **_ _clrcall**関数ポインターと外部宣言でのみ指定できます。

直接呼び出すことができます **_ _clrcall**関数を使用してコンパイルされた既存の C++ コードから **/clr**限り、その関数がある MSIL を実装します。 **_ _clrcall**でこれらの関数がコンパイルされた場合でも、関数をインライン asm を持ち CPU 固有の組み込み関数を呼び出すから直接関数を呼び出すことができません`/clr`します。

**_ _clrcall**関数ポインターが作成されたアプリケーション ドメインで使用するもののみです。  渡すのではなく **_ _clrcall**アプリケーション ドメイン間で関数ポインターを使用して<xref:System.CrossAppDomainDelegate>します。 詳細については、次を参照してください。[アプリケーション ドメインと Visual c](../dotnet/application-domains-and-visual-cpp.md)します。

## <a name="example"></a>例

関数を宣言するときに注意して **_ _clrcall**、必要なときにコードが生成されます。 関数が呼び出された場合などです。

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

次のサンプルでは、関数ポインターがマネージド コードからのみ呼び出されるように、関数ポインターを定義する方法を示します。 これにより、コンパイラはマネージド関数を直接呼び出し、ネイティブ エントリ ポイント (ダブル サンクの問題) を避けることができます。

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

[引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
