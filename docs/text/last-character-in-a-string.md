---
title: 文字列の最後の文字
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 535c2e58edab49e0e2a9dbc3fce9821d5909f1c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456265"
---
# <a name="last-character-in-a-string"></a>文字列の最後の文字

次のヒントを使用します。

- 後続バイトの範囲では、ASCII 文字セットで多くの場合と重複します。 バイト単位のスキャンは、制御文字 (32 未満) を安全に使用できます。

- 文字列の最後の文字が円記号かどうかをチェックしたり、コードの次の行を考慮してください。

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   `strlen`は MBCS を認識しないマルチバイト文字列の文字の数ではなく、バイト数を返します。 コード ページ (932 など)、いくつかのことに注意も、'\\' (0x5c) が有効な末尾バイト (`sz`は C 文字列です)。

   ソリューションの 1 つは、この方法でコードを書き換えるには。

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   このコードは、MBCS の関数を使用して`_mbsrchr`と`_mbsinc`します。 間と区別できるこれらの関数は、MBCS 対応であるため、'\\'文字と後続バイト'\\'。 コードは、文字列の最後の文字が null ('\0') の場合、何らかのアクションを実行します。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングについて](../text/mbcs-programming-tips.md)<br/>
[文字の代入](../text/character-assignment.md)