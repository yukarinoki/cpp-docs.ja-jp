---
title: 文字列および I/O の書式設定 (Modern C++)
description: 最新の C++ で利用可能な書式付き文字列 I/O の選択肢。
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: a3fc93b0baf414759eb50c787c4057fb85dcb370
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375772"
---
# <a name="string-and-io-formatting-modern-c"></a>文字列および I/O の書式設定 (Modern C++)

C++ [ \<iostream>](../standard-library/iostream.md)クラス、関数、および演算子は、書式指定された文字列 I/O をサポートします。 たとえば、次のコードは、整数を`cout`16 進数で出力するように設定する方法を示しています。 まず、フォーマット状態がに渡されると、変更されるまでそのまま残るため、現在の状態を`cout`保存して、後でリセットします。 1 行のコードだけに適用されるわけではありません。

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    ios state(nullptr);

    cout << "The answer in decimal is: " << 42 << endl;

    state.copyfmt(cout); // save current formatting
    cout << "In hex: 0x" // now load up a bunch of formatting modifiers
        << hex
        << uppercase
        << setw(8)
        << setfill('0')
        << 42            // the actual value we wanted to print out
        << endl;
    cout.copyfmt(state); // restore previous formatting
}
```

この方法はタイプ セーフで拡張可能ですが、複雑で冗長な方法でもあります。

## <a name="alternative-format-options"></a>代替形式オプション

代わりに、Boost C++`Boost.Format`ライブラリから使用することもできますが、標準ではありませんが、このライブラリは標準ではありません。 Boost のウェブサイトから任意の[ブースト](https://www.boost.org/)ライブラリをダウンロードできます。

いくつかの利点`Boost.Format`は次のとおりです。

- 安全: タイプ セーフで、エラー (指定項目が少なすぎる、または多すぎるなど) の例外をスローします。

- 拡張可能: ストリーム可能なすべての型を処理できます。

- 便利: 標準 POSIX と類似の書式指定文字列。

`Boost.Format` C++ [ \<iostream>](../standard-library/iostream-programming.md)機能を使用して構築されていますが、これは安全で拡張性に優れていますが、パフォーマンスに最適化されていません。 パフォーマンスの最適化が必要な場合は、高速で使いやすい C [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)と[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)を検討してください。 ただし、拡張可能でも、脆弱性からも安全ではありません。 (セキュリティが強化されたバージョンがありますが、わずかながらパフォーマンスが低下します。 詳細については[、「printf_s、_printf_s_l、wprintf_s、_wprintf_s_l、sprintf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md) [_sprintf_s_l、swprintf_s、_swprintf_s_l」](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)を参照してください。

次のコードは、Boost の書式設定機能のいくつかを示します。

```cpp
    string s = str( format("%2% %2% %1%\n") % "world" % "hello" );
    // s contains "hello hello world"

    for( auto i = 0; i < names.size(); ++i )
        cout << format("%1% %2% %|40t|%3%\n") % first[i] % last[i] % tel[i];
    // Georges Benjamin Clemenceau             +33 (0) 123 456 789
    // Jean de Lattre de Tassigny              +33 (0) 987 654 321
```

## <a name="see-also"></a>関連項目

[C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<制限>](../standard-library/limits.md)<br/>
[\<イオマニプ>](../standard-library/iomanip.md)
