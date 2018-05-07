---
title: コンパイラの警告 (レベル 4) C4471 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4471
dev_langs:
- C++
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a530cee3c3fcfec8566d46b116fcc4e71760ed11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4471"></a>コンパイラの警告 (レベル 4) C4471
'*列挙*': 対象範囲外の列挙の事前宣言が基になる型 (int が想定されます) を持つ必要があります  
  
対象範囲外の列挙の事前宣言を基になる型の指定子がありませんでした。 既定では、Visual C が前提としています`int`は列挙型の基になる型です。 これにより、別の種類で使用される場合列挙型の定義、たとえば、別の明示的な型が指定されている場合、または別の種類が暗黙的に初期化子によって設定されている場合、問題が発生することができます。 移植性の問題があります。他のコンパイラと仮定しないで`int`列挙体の基になる型です。  
  
この警告はオフです。 既定では、します。/Wall または/w を使用することができます*N*コマンド ラインで有効にするにまたは #pragma 4471[警告](../../preprocessor/warning.md)をソース ファイルにします。  
  
場合によっては、この警告は偽です。 列挙の事前宣言は、定義の後に表示されたら、この警告が発生します。 たとえば、このコードはありませんが、でも C4471 をしまう可能性があります。  
  
```cpp  
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```  
  
## <a name="example"></a>例  
一般に、事前宣言ではなくスコープを持たない列挙型の完全定義を使用するも安全です。 それを参照するソース ファイルに含めるし、ヘッダー ファイルで定義を配置することができます。 これは、c++ 98 以降に記述されたコードでは動作します。 このソリューションの移植性と保守を容易に行うことをお勧めします。  
  
```cpp  
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```  
  
## <a name="example"></a>例  
C++ 11 では、対象範囲外の列挙型にし、その前方宣言に、明示的な型を追加できます。 このソリューションは、複雑なヘッダー包含ロジック事前宣言ではなく、定義の使用を防止する場合にのみお勧めします。 このソリューションは、保守の問題につながることができます: 列挙型の定義に使用される基になる型を変更すると、すべての一致する、前方宣言を変更することも必要がありますまたはサイレント エラーは、コードにある場合があります。 事前宣言は、この問題を最小限に抑えるヘッダー ファイルに配置できます。  
  
```cpp  
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```  
  
```cpp  
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```  
  
列挙型の明示的な型を指定する場合をお勧めするも警告を有効にする[C4369](compiler-warning-level-1-C4369.md)既定でオンになっています。 列挙アイテムが明示的に指定された型とは異なる型に必要な場合を識別します。
  
## <a name="example"></a>例  
スコープの列挙型の c++ 11 で新機能を使用するコードを変更することができます。 スコープ列挙型を使用するには、定義と、列挙型を使用する任意のクライアント コードの両方を変更してください。 使用するスコープ列挙型、名前空間の汚染に関する問題があればように定義された列挙型項目の名前は、列挙型のスコープに限定することをお勧めします。 スコープ列挙型の別の機能では、そのメンバーを暗黙的にもう 1 つ整数型または列挙型、軽度のバグの原因となることができますに変換できません。

```cpp  
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```  
  
```cpp  
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```  
  
