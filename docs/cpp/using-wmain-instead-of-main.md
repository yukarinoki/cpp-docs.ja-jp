---
title: main に代わる wmain の使用
ms.date: 11/04/2016
f1_keywords:
- wmain
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
ms.openlocfilehash: f47d7219a54b197ec59f109cf08879774b48e6f7
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857217"
---
# <a name="using-wmain-instead-of-main"></a>main に代わる wmain の使用

**Microsoft 固有の仕様**

Unicode プログラミングモデルでは、`main` 関数のワイド文字バージョンを定義できます。 Unicode 仕様に準拠した移植可能なコードを記述する場合は、`main` ではなく**wmain**を使用します。

**Wmain**に対して仮パラメーターを宣言するには、`main`に似た形式を使用します。 さらに、ワイド文字の引数と、必要であればワイド文字環境ポインターもプログラムに渡すことができます。 **Wmain**の*argv*および*envp*パラメーターの型は `wchar_t*`です。

プログラムで `main` 関数を使用する場合、マルチバイト文字環境は、プログラムの起動時にオペレーティングシステムによって作成されます。 環境のワイド文字コピーは、必要な場合にのみ作成されます (たとえば、 [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)または[_wputenv](../c-runtime-library/reference/putenv-wputenv.md)関数の呼び出しによって作成されます)。 `_wputenv` を最初に呼び出すとき、または MBCS 環境が既に存在する場合に `_wgetenv` を最初に呼び出すとき、対応するワイド文字列環境が作成され、その後は作成されたワイド文字列環境が `_wenviron` グローバル変数 (`_environ` グローバル変数のワイド文字バージョン) によって参照されます。 この時点までで、2 つの環境のコピー (MBCS および Unicode) が同時に存在していることになるわけですが、両方ともプログラムが消滅するまでオペレーティング システムによって保持されます。

同様に、プログラムが**wmain**関数を使用する場合、MBCS (ASCII) 環境は `_putenv` または `getenv`の最初の呼び出し時に作成され、`_environ` のグローバル変数によってポイントされます。

MBCS 環境の詳細については、「*ランタイムライブラリリファレンス*」の「 [1 バイト文字セットとマルチバイト文字セット](../c-runtime-library/single-byte-and-multibyte-character-sets.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[main: プログラムの起動](../cpp/main-program-startup.md)