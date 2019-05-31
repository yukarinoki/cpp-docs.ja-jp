---
title: 文字列および I/O の書式設定 (Modern C++)
description: 書式設定された文字列 I/O の使用可能な最新の選択肢C++します。
ms.date: 05/30/2019
ms.topic: conceptual
ms.assetid: 3954e8de-a59b-4175-89c9-4ee842ab89ed
ms.openlocfilehash: e22c745798109a2dbef82297c45256593823f806
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450499"
---
# <a name="string-and-io-formatting-modern-c"></a>文字列および I/O の書式設定 (Modern C++)

C++[ \<iostream >](../standard-library/iostream.md)クラス、関数、および演算子は、I/O の書式設定された文字列をサポートします。 たとえば、次のコードが設定する方法を示します`cout`を 16 進数で出力の整数を書式設定します。 形式の状態が 1 回に渡されるためにその後、リセットするために現在の状態を保存、最初に、 `cout`、変更されるまでのままになります。 1 行のコードにだけは適用されません。

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

この方法は、タイプ セーフと拡張性を併せ持つが複雑で冗長ではも。

## <a name="alternative-format-options"></a>代替形式のオプション

代わりに、使用することができます`Boost.Format`、Boost からC++が標準でない場合でも、ライブラリ。 任意の Boost ライブラリをダウンロードすることができます、 [Boost](https://www.boost.org/) web サイト。

いくつかの利点の`Boost.Format`は。

- 安全性:タイプ セーフが多すぎるか少なすぎます項目の仕様などのエラー、例外をスローします。

- 拡張。ストリーム配信できる任意の型に対して機能します。

- 便利です。標準 Posix と類似の書式指定文字列。

`Boost.Format`上に構築されたC++ [ \<iostream >](../standard-library/iostream-programming.md)施設で、安全で拡張可能では、パフォーマンスが最適化されたはありません。 パフォーマンスの最適化を必要とする場合は、C を検討してください[printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)と[sprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)は高速で簡単に使用します。 ただし、これらは、拡張可能なまたは脆弱性から安全はありません。 (セキュリティが強化されたバージョンがありますが、わずかながらパフォーマンスが低下します。 詳細については、次を参照してください。 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)と[sprintf_s、_sprintf_s_l、swprintf_s、_swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md))。

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

[C++ へようこそ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)<br/>
[\<iostream>](../standard-library/iostream.md)<br/>
[\<limits>](../standard-library/limits.md)<br/>
[\<iomanip>](../standard-library/iomanip.md)
