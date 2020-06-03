---
title: appdomain
ms.date: 11/04/2016
f1_keywords:
- appdomain_cpp
helpviewer_keywords:
- appdomain __declspec keyword
- __declspec keyword [C++], appdomain
ms.assetid: 29d843cb-cb6b-4d1b-a48d-d928a877234d
ms.openlocfilehash: 7ac74e8774204b316712a15975f7af3fb8835a9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181487"
---
# <a name="appdomain"></a>appdomain

マネージド アプリケーションの各アプリケーション ドメインは特定のグローバル変数または静的メンバー変数の独自のコピーを持つ必要があることを指定します。 詳細については[、「アプリケーションドメインとビジュアルC++ ](../dotnet/application-domains-and-visual-cpp.md) 」を参照してください。

あらゆるアプリケーション ドメインに appdomain ごとの変数のコピーが存在します。 appdomain 変数のコンストラクターはアセンブリがアプリケーション ドメインに読み込まれるときに実行され、デストラクターはアプリケーション ドメインがアンロードされるときに実行されます。

共通言語ランタイムのプロセス内ですべてのアプリケーション ドメインがグローバル変数を共有する場合は、`__declspec(process)` 修飾子を使用します。 `__declspec(process)` は、既定で[/clr](../build/reference/clr-common-language-runtime-compilation.md)で有効になっています。 **/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

`__declspec(appdomain)` は、 **/clr**コンパイラオプションのいずれかが使用されている場合にのみ有効です。 `__declspec(appdomain)` でマークできるのは、グローバル変数、静的メンバー変数、または静的ローカル変数だけです。 マネージド型の静的メンバーに `__declspec(appdomain)` を適用するとエラーになります。そのようなメンバーは常にこの動作をするためです。

`__declspec(appdomain)` の使用は、[スレッドローカルストレージ (TLS)](../parallel/thread-local-storage-tls.md)の使用に似ています。 スレッドは、アプリケーション ドメインと同様に独自のストレージを持ちます。 `__declspec(appdomain)` を使用すると、このアプリケーションで作成された各アプリケーション ドメインで、グローバル変数が独自のストレージを持つことが保証されます。

プロセスごとの使用と appdomain ごとの変数の組み合わせには制限があります。詳細については、「 [process](../cpp/process.md) 」を参照してください。

たとえば、プログラムの開始時に、すべての process ごとの変数が初期化され、続いて、すべての appdomain ごとの変数が初期化されます。 そのため、process ごとの変数が初期化されるときには、appdomain ごとの変数の値に依存することはできません。 appdomain ごとの変数と process ごとの変数を混在使用 (代入) することは好ましくありません。

特定のアプリケーションドメインで関数を呼び出す方法については、「 [Call_in_appdomain 関数](../dotnet/call-in-appdomain-function.md)」を参照してください。

## <a name="example"></a>例

```cpp
// declspec_appdomain.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

class CGlobal {
public:
   CGlobal(bool bProcess) {
      Counter = 10;
      m_bProcess = bProcess;
      Console::WriteLine("__declspec({0}) CGlobal::CGlobal constructor", m_bProcess ? (String^)"process" : (String^)"appdomain");
   }

   ~CGlobal() {
      Console::WriteLine("__declspec({0}) CGlobal::~CGlobal destructor", m_bProcess ? (String^)"process" : (String^)"appdomain");
   }

   int Counter;

private:
   bool m_bProcess;
};

__declspec(process) CGlobal process_global = CGlobal(true);
__declspec(appdomain) CGlobal appdomain_global = CGlobal(false);

value class Functions {
public:
   static void change() {
      ++appdomain_global.Counter;
   }

   static void display() {
      Console::WriteLine("process_global value in appdomain '{0}': {1}",
         AppDomain::CurrentDomain->FriendlyName,
         process_global.Counter);

      Console::WriteLine("appdomain_global value in appdomain '{0}': {1}",
         AppDomain::CurrentDomain->FriendlyName,
         appdomain_global.Counter);
   }
};

int main() {
   AppDomain^ defaultDomain = AppDomain::CurrentDomain;
   AppDomain^ domain = AppDomain::CreateDomain("Domain 1");
   AppDomain^ domain2 = AppDomain::CreateDomain("Domain 2");
   CrossAppDomainDelegate^ changeDelegate = gcnew CrossAppDomainDelegate(&Functions::change);
   CrossAppDomainDelegate^ displayDelegate = gcnew CrossAppDomainDelegate(&Functions::display);

   // Print the initial values of appdomain_global in all appdomains.
   Console::WriteLine("Initial value");
   defaultDomain->DoCallBack(displayDelegate);
   domain->DoCallBack(displayDelegate);
   domain2->DoCallBack(displayDelegate);

   // Changing the value of appdomain_global in the domain and domain2
   // appdomain_global value in "default" appdomain remain unchanged
   process_global.Counter = 20;
   domain->DoCallBack(changeDelegate);
   domain2->DoCallBack(changeDelegate);
   domain2->DoCallBack(changeDelegate);

   // Print values again
   Console::WriteLine("Changed value");
   defaultDomain->DoCallBack(displayDelegate);
   domain->DoCallBack(displayDelegate);
   domain2->DoCallBack(displayDelegate);

   AppDomain::Unload(domain);
   AppDomain::Unload(domain2);
}
```

```Output
__declspec(process) CGlobal::CGlobal constructor
__declspec(appdomain) CGlobal::CGlobal constructor
Initial value
process_global value in appdomain 'declspec_appdomain.exe': 10
appdomain_global value in appdomain 'declspec_appdomain.exe': 10
__declspec(appdomain) CGlobal::CGlobal constructor
process_global value in appdomain 'Domain 1': 10
appdomain_global value in appdomain 'Domain 1': 10
__declspec(appdomain) CGlobal::CGlobal constructor
process_global value in appdomain 'Domain 2': 10
appdomain_global value in appdomain 'Domain 2': 10
Changed value
process_global value in appdomain 'declspec_appdomain.exe': 20
appdomain_global value in appdomain 'declspec_appdomain.exe': 10
process_global value in appdomain 'Domain 1': 20
appdomain_global value in appdomain 'Domain 1': 11
process_global value in appdomain 'Domain 2': 20
appdomain_global value in appdomain 'Domain 2': 12
__declspec(appdomain) CGlobal::~CGlobal destructor
__declspec(appdomain) CGlobal::~CGlobal destructor
__declspec(appdomain) CGlobal::~CGlobal destructor
__declspec(process) CGlobal::~CGlobal destructor
```

## <a name="see-also"></a>参照

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
