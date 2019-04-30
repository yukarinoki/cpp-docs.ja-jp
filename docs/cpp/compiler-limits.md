---
title: コンパイラの制限
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, limits for language constructs
ms.assetid: f1fa59c6-55b4-414b-80c5-3df72952160d
ms.openlocfilehash: a0c6041d326982dc9807355733cf714dcfa62ca8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399162"
---
# <a name="compiler-limits"></a>コンパイラの制限

C++ 標準は、さまざまな言語構成体の制限を勧告しています。 以下は、Visual C++ コンパイラが推奨される制限を実装しない場合のリストです。 最初の数字は ISO C++ 11 標準 (INCITS/ISO/IEC 14882-2011[2012], Annex B) で規定されている制限であり、2 番目の数字は Visual C++ で実装されている制限です。

- 複合ステートメント、イテレーション制御構造、および選択制御構造の入れ子レベルC++標準。256, visualC++コンパイラ: 入れ子になっているステートメントが一般的に 100 から 110 の間の組み合わせによって異なります。

- 1 つのマクロ定義でパラメーターC++標準。256, visualC++コンパイラ。127.

- -1 つのマクロの呼び出しで引数C++標準。256, visualC++コンパイラ 127。

- 文字数では、リテラルまたはワイド文字列リテラルを文字列 (連結) - 後C++標準。65536、visualC++コンパイラ。NULL 終端文字も含めて、65535 の 1 バイト文字と NULL ターミネータを含めた 32767 の 2 バイト文字。

- 入れ子になったクラス、構造体、共用体の定義を 1 つのレベル`struct-declaration-list`-C++標準。256, visualC++コンパイラ。16.

- メンバー初期化子のコンス トラクターの定義 -C++標準。6144、visualC++コンパイラ: 最低 6144 します。

- スコープの 1 つの識別子の修飾C++標準。256, visualC++コンパイラ。127.

- 入れ子になった**extern**仕様 -C++標準。1024、visualC++コンパイラ。9 (カウントせず、暗黙的な**extern**グローバル スコープ、または 10 の暗黙的なをカウントする場合、仕様**extern**グローバル スコープ内の指定

- -テンプレート宣言内のテンプレート引数C++標準。1024、visualC++コンパイラ。2046.

## <a name="see-also"></a>関連項目

[非標準動作](../cpp/nonstandard-behavior.md)