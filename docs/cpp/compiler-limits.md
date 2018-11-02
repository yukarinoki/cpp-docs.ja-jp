---
title: コンパイラの制限
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: a0c6041d326982dc9807355733cf714dcfa62ca8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600331"
---
# <a name="compiler-limits"></a>コンパイラの制限

C++ 標準は、さまざまな言語構成体の制限を勧告しています。 以下は、Visual C++ コンパイラが推奨される制限を実装しない場合のリストです。 最初の数字は ISO C++ 11 標準 (INCITS/ISO/IEC 14882-2011[2012], Annex B) で規定されている制限であり、2 番目の数字は Visual C++ で実装されている制限です。

- 入れ子のレベルの複合ステートメント、イテレーション制御構造、および選択制御構造の C++ 標準: 256、Visual C コンパイラ: 入れ子になっているステートメントが一般的に 100 から 110 の間の組み合わせによって異なります。

- パラメーターの 1 つのマクロ定義の C++ 標準: 256、Visual C コンパイラ: 127。

- 引数の 1 つのマクロ呼び出しの C++ 標準: 256、Visual C コンパイラ 127。

- 文字の文字文字列リテラルまたはワイド文字列リテラル (連結後)、C++ 標準: 65536、Visual C コンパイラ: NULL 終端文字も含めて、65535 の 1 バイト文字と NULL ターミネータを含めた 32767 の 2 バイト文字。

- 入れ子になったクラス、構造体、共用体の定義を 1 つのレベル`struct-declaration-list`-C++ 標準: 256、Visual C コンパイラ: 16。

- メンバー初期化子のコンス トラクターの定義では、C++ 標準: 6144、Visual C コンパイラ: 最低 6144 します。

- スコープ修飾の 1 つの識別子の C++ 標準: 256、Visual C コンパイラ: 127。

- 入れ子になった**extern**仕様の C++ 標準: 1024、Visual C コンパイラ: 9 (暗黙をカウントせず**extern**グローバル スコープ、または 10 の暗黙的なをカウントする場合、仕様**extern**グローバル スコープ内の指定.

- C++ 標準のテンプレート宣言内のテンプレート引数: 1024、Visual C コンパイラ: 2046 です。

## <a name="see-also"></a>関連項目

[非標準動作](../cpp/nonstandard-behavior.md)