---
description: '詳細情報: コンパイラの警告 (レベル 3) C4398'
title: コンパイラの警告 (レベル 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: ea88f81e44fe0520cd096e1904c49a306863496a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160429"
---
# <a name="compiler-warning-level-3-c4398"></a>コンパイラの警告 (レベル 3) C4398

> '*variable*': プロセスごとのグローバルオブジェクトは、複数の appdomain で正しく機能しない可能性があります。__declspec (appdomain) の使用を検討する

## <a name="remarks"></a>解説

ネイティブ型で [__clrcall](../../cpp/clrcall.md) 呼び出し規約を持つ仮想関数は、アプリケーションドメイン vtable ごとにを作成します。 このような変数は、複数のアプリケーションドメインで使用されている場合、正しく修正されない可能性があります。

この警告は、変数を明示的にマークすることによって解決でき `__declspec(appdomain)` ます。 Visual Studio 2017 より前のバージョンの Visual Studio では、 **/clr: pure** を指定してコンパイルすることで、この警告を解決できます。これにより、既定で appdomain ごとにグローバル変数が作成されます。 **/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

詳細については、「 [appdomain](../../cpp/appdomain.md) と [アプリケーションドメイン」および「Visual C++](../../dotnet/application-domains-and-visual-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4398 が生成されます。

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```
