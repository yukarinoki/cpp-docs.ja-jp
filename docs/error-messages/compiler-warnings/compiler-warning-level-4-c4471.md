---
title: コンパイラの警告 (レベル 4) C4471
ms.date: 04/24/2017
f1_keywords:
- C4471
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
ms.openlocfilehash: 5b8c3ef419a4c6eaf9a674827cd5545a1f1b2bfe
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685503"
---
# <a name="compiler-warning-level-4-c4471"></a>コンパイラの警告 (レベル 4) C4471

'*enumeration*': 対象範囲外の列挙の事前宣言には基になる型 (int と仮定) を指定する必要があります

対象範囲外の列挙の事前宣言が見つかりましたが、基になる型に指定子がありません。 既定では、Visual C++ **`int`** は列挙体の基になる型であると見なされます。 別の明示的な型が指定されている場合や、初期化子によって別の型が暗黙的に設定されている場合など、列挙定義で別の型が使用されていると、問題が発生する可能性があります。 また、移植性の問題がある場合もあります。他のコンパイラは **`int`** 、が列挙型の基になる型であると想定していません。

既定では、この警告はオフになっています。/Wall または/w*N*4471 を使用してコマンドラインで有効にすることも、ソースファイルで #pragma [警告](../../preprocessor/warning.md) を使用することもできます。

## <a name="examples"></a>例

場合によっては、この警告は誤って通知されます。 列挙型の事前宣言が定義の後にある場合、この警告が発生することがあります。 たとえば、C4471 が発生する可能性がある場合でも、次のコードは有効です。

```cpp
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```

一般に、事前宣言ではなく、対象範囲外の列挙に完全定義を使用するのが安全です。 定義をヘッダーファイルに配置し、それを参照するソースファイルに含めることができます。 これは、C++ 98 以降用に記述されたコードで機能します。 このソリューションは、移植性と保守性を確保するためにお勧めします。

```cpp
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```

C++ 11 では、対象範囲外の列挙型と事前宣言に明示的な型を追加できます。 このソリューションは、高度なヘッダー包含ロジックで事前宣言ではなく定義を使用できない場合にのみお勧めします。 このソリューションでは、メンテナンスの問題が発生する可能性があります。列挙の定義に使用される基になる型を変更する場合は、すべての事前宣言を変更して一致させるか、コード内にサイレントエラーが発生することがあります。 この問題を最小限に抑えるために、事前宣言をヘッダーファイルに含めることができます。

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

列挙型に明示的な型を指定する場合は、既定でオンになっている warning [C4369](compiler-warning-level-1-C4369.md)も有効にすることをお勧めします。 これは、列挙項目が明示的に指定された型とは異なる型を必要とするケースを識別します。

コードを変更して、C++ 11 の新機能であるスコープを持つ列挙型を使用することができます。 定義と列挙型を使用するクライアントコードは両方とも、スコープを持つ列挙型を使用するように変更する必要があります。 定義済みの列挙項目の名前が列挙型のスコープに限定されるため、名前空間の汚染に関する問題がある場合は、スコープを持つ列挙型を使用することをお勧めします。 スコープを持つ列挙型のもう1つの機能は、そのメンバーを暗黙的に別の整数型または列挙型に変換できないことです。これは、微妙なバグの原因になる可能性があります。

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
