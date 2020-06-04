---
title: コンパイラの警告 (レベル 1) C4342
ms.date: 11/04/2016
f1_keywords:
- C4342
helpviewer_keywords:
- C4342
ms.assetid: 47d4d5ab-069f-4cdc-98c3-10d649577a37
ms.openlocfilehash: 8ac00d3d57f8cf7d6c85f3106dbe9b8c3cb9adf0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162921"
---
# <a name="compiler-warning-level-1-c4342"></a>コンパイラの警告 (レベル 1) C4342

動作変更: '*function*' が呼び出されましたが、メンバー演算子が前のバージョンで呼び出されました

Visual Studio 2002 よりC++前のバージョンの visual Studio では、メンバーが呼び出されましたが、この動作は変更されており、コンパイラは名前空間のスコープ内で最適な一致を検出するようになりました。

メンバー演算子が見つかった場合、コンパイラは以前は名前空間スコープ演算子を考慮していませんでした。 名前空間のスコープでより適切な一致がある場合、現在のコンパイラはそれを正しく呼び出しますが、以前のコンパイラはそれを考慮しません。

現在のバージョンにコードを正常に移植した後は、この警告を無効にする必要があります。  コンパイラは誤検知を与える可能性があります。この警告は、動作の変更がないコードに対して生成されます。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

次の例では、C4342 が生成されます。

```cpp
// C4342.cpp
// compile with: /EHsc /W1
#include <fstream>
#pragma warning(default: 4342)
using namespace std;
struct X : public ofstream {
   X();
};

X::X() {
   open( "ofs_bug_ev.txt." );
   if ( is_open() ) {
      *this << "Text" << "<-should be text" << endl;   // C4342
      *this << ' ' << "<-should be space symbol" << endl;   // C4342
   }
}

int main() {
   X b;
   b << "Text" << "<-should be text" << endl;
   b << ' ' << "<-should be space symbol" << endl;
}
```
