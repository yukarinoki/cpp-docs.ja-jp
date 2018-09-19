---
title: コンパイラの警告 (レベル 4) C4571 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4571
dev_langs:
- C++
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1291466ffd9071929194ffbe7795addfec62eb27
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088320"
---
# <a name="compiler-warning-level-4-c4571"></a>コンパイラの警告 (レベル 4) C4571

情報: catch (...) セマンティクスが Visual C 7.1; から変更構造化例外 (SEH) はキャッチされません。

コンパイルすると、catch (...) ブロックごと C4571 が生成される **/EHs**します。

コンパイルするときに **/EHs**、catch (...) ブロックでは、構造化例外 (null ポインターの例では、0 による除算) 以外、catch (...) ブロックが唯一の落とし穴明示的にスローされた C++ 例外をキャッチできません。  詳細については、「[例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。

既定では、この警告はオフに設定されています。  この警告でコンパイルするときに確実に有効にする **/EHs** catch (...) ブロックは構造化例外をキャッチしません。  詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

C4571 を解決するには、次の方法のいずれかで

- 使用してコンパイル **/EHa**構造化例外をキャッチする、catch (...) ブロックが必要な場合。

- 構造化例外をキャッチ、catch (...) ブロックされないようにするには、catch (...) ブロックを使用する場合は、C4571 を有効にしないでください。  構造化例外処理キーワードを使用して構造化例外をキャッチすることもできます (**_ _try**、 **_ _except**、および **_ _finally**)。  ただし、コンパイル時に **/EHs**デストラクターは SEH 例外が発生したときではなく、C++ 例外がスローされたときにのみ呼び出すことです。

- 特定の C++ 例外の catch ブロックと catch (...) ブロックを置き換えるし、構造化例外処理に関する C++ の例外処理を必要に応じて、追加 (**_ _try**、 **_ _except**、および **__finally**)。  参照してください[構造化例外処理 (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)詳細についてはします。

参照してください[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C4571 が生成されます。

```
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```