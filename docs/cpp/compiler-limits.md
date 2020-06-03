---
title: コンパイラの制限
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 9e61cae1638c87f03b6fa775552408961bde6859
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189581"
---
# <a name="compiler-limits"></a>コンパイラの制限

C++ 標準は、さまざまな言語構成体の制限を勧告しています。 Microsoft C++コンパイラが推奨される制限を実装していない場合の一覧を次に示します。 最初の数値は、ISO C++ 11 標準 (その/ISO/IEC 14882-2011 [2012]、付属 B) で規定されている制限であり、2番目の数値は Microsoft C++コンパイラによって実装される制限です。

- 複合ステートメント、イテレーション制御構造、および選択制御構造の入れ子レベル- C++標準: 256、Microsoft C++コンパイラ: は、入れ子になっているステートメントの組み合わせに依存しますが、通常は100と110の間にあります。

- 1つのマクロ定義内C++のパラメーター-standard: C++ 256、Microsoft コンパイラ: 127。

- 1つのマクロ呼び出しのC++引数-standard: 256 C++ 、Microsoft コンパイラ127。

- 文字列リテラルまたはワイド文字列リテラルの文字 (連結後)- C++ standard: 65536、Microsoft C++コンパイラ: 65535 1 バイト文字 (null 終端文字を含む)、および null 終端文字を含む、32767の2バイト文字。

- 1つの `struct-declaration-list` での入れ子になったクラス、構造体、 C++または共用体のC++定義のレベル-標準: 256、Microsoft コンパイラ:16。

- コンストラクターの定義でのメンバー初期化C++子-standard: 6144 C++ 、Microsoft コンパイラ: 6144 以降。

- 1つの識別子のスコープC++修飾-標準: 256 C++ 、Microsoft コンパイラ: 127。

- 入れ子**extern**になったC++ extern 仕様-Standard: C++ 1024、Microsoft コンパイラ: 9 (グローバルスコープで暗黙的な**extern**仕様をカウントしない、またはグローバルスコープで暗黙の**extern**仕様をカウントする場合は 10)。

- テンプレート宣言内のテンプレート引数- C++ standard: 1024、Microsoft C++コンパイラ: 2046。

## <a name="see-also"></a>参照

[非標準動作](../cpp/nonstandard-behavior.md)
