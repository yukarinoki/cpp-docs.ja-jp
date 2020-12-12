---
description: 詳細については、「C++ プログラムの起動と終了」を参照してください。
title: C++ プログラムの起動と終了
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
ms.openlocfilehash: 644be6d4392f8e41b1d1cf7d45b484ed9903d463
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324788"
---
# <a name="c-program-startup-and-termination"></a>C++ プログラムの起動と終了

C++ プログラムは、プログラムの起動時と終了時に C プログラムと同じ操作に加えて、ここで説明する追加の操作を実行します。

対象環境が `main` 関数を呼び出す前、および静的存続期間があるすべてのオブジェクトで指定されている定数初期値が格納された後、プログラムはこのような静的オブジェクトに対する残りのコンストラクターを実行します。 翻訳単位の間で実行順序は指定されていませんが、それでも、これらの静的コンストラクターによる使用のために一部の [iostreams](../standard-library/iostreams-conventions.md) オブジェクトが正しく初期化されるものと想定できます。 このようなコントロール テキスト ストリームは次のとおりです。

- [cin](../standard-library/iostream.md#cin) — 標準入力の場合。

- [cout](../standard-library/iostream.md#cout) — 標準出力の場合。

- [cerr](../standard-library/iostream.md#cerr) — バッファーされない標準エラー出力の場合。

- [clog](../standard-library/iostream.md#clog) — バッファーされる標準エラー出力の場合。

また、プログラムの終了時に、静的オブジェクトに対して呼び出されるデストラクター内で、これらのオブジェクトを使用できます。

C と同様に、`main` からの戻りまたは `exit` の呼び出しでは、`atexit` に登録されているすべての関数が、登録と逆の順序で呼び出されます。 このような登録されている関数からスローされる例外は、`terminate` を呼び出します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
