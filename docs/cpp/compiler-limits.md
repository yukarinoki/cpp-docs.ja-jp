---
description: '詳細情報: コンパイラの制限'
title: コンパイラの制限
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: 7471b6e161f6e1f1466fdc27266249cefc17f7ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318157"
---
# <a name="compiler-limits"></a>コンパイラの制限

C++ 標準は、さまざまな言語構成体の制限を勧告しています。 Microsoft C++ コンパイラが推奨される制限を実装していない場合の一覧を次に示します。 最初の数値は、ISO C++ 11 標準 (その/ISO/IEC 14882-2011 [2012]、付属 B) で規定されている制限であり、2番目の数値は Microsoft C++ コンパイラによって実装される制限です。

- 複合ステートメント、イテレーション制御構造、および選択制御構造の入れ子レベル-C++ 標準: 256、Microsoft C++ コンパイラ: は、入れ子になっているステートメントの組み合わせに依存しますが、通常は100と110の間にあります。

- 1つのマクロ定義内のパラメーター-C++ 標準: 256、Microsoft C++ コンパイラ: 127。

- 1つのマクロ呼び出しの引数-C++ 標準: 256、Microsoft C++ コンパイラ127。

- 文字列リテラルまたはワイド文字列リテラルの文字 (連結後)-C++ 標準: 65536、Microsoft C++ コンパイラ: 65535 1 バイト文字 (NULL 終端文字を含む)、および NULL 終端文字を含む、32767の2バイト文字。

- 1つの C++ 標準での入れ子になったクラス、構造体、または共用体の定義のレベル `struct-declaration-list` : 256、Microsoft C++ コンパイラ:16。

- コンストラクターの定義におけるメンバー初期化子-C++ 標準: 6144、Microsoft C++ コンパイラ: 6144 以降。

- 1つの識別子のスコープ要件-C++ 標準: 256、Microsoft C++ コンパイラ: 127。

- 入れ子になった **`extern`** 仕様-C++ 標準: 1024、Microsoft c++ コンパイラ: 9 (グローバルスコープの暗黙的な指定をカウントしません。 **`extern`** または、 **`extern`** グローバルスコープの暗黙的な指定をカウントする場合は 10)。

- テンプレート宣言内のテンプレート引数-C++ 標準: 1024、Microsoft C++ コンパイラ: 2046。

## <a name="see-also"></a>関連項目

[非標準動作](../cpp/nonstandard-behavior.md)
