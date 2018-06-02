---
title: コンパイラの警告 (レベル 3) C4398 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4398
dev_langs:
- C++
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c38ade6b75242fdd5144481e3415e914cb6773c5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704615"
---
# <a name="compiler-warning-level-3-c4398"></a>コンパイラの警告 (レベル 3) C4398

> '*変数*': プロセスごとのグローバル オブジェクトは複数の appdomain と共に動作しない可能性があります __declspec(appdomain) を使用してください。

## <a name="remarks"></a>コメント

仮想関数と[_ _clrcall](../../cpp/clrcall.md)の作成をネイティブ型に規則を呼び出すと、アプリケーション ドメインの vtable ごとです。 複数のアプリケーション ドメインで使用する場合は、このような変数が適切に修正されない場合があります。

この警告を解決するには、変数を明示的にマークすることによって`__declspec(appdomain)`です。 Visual Studio 2017 より前に、の Visual Studio のバージョンは、この警告を解決でコンパイルすると **/clr: 純粋な**、これにより、appdomain ごとのグローバル変数既定値です。 **/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 では廃止され、Visual Studio 2017 でサポートされていません。

詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[アプリケーション ドメインと Visual c](../../dotnet/application-domains-and-visual-cpp.md)です。

## <a name="example"></a>例

次の例では、C4398 を生成します。

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```