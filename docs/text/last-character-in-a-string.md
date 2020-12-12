---
description: '詳細情報: 文字列の最後の文字'
title: 文字列の最後の文字
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 10ab90614509508b9667c29ccf166ddaf784a92e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207242"
---
# <a name="last-character-in-a-string"></a>文字列の最後の文字

次のヒントを参考にしてください。

- 多くの場合、末尾のバイト範囲が ASCII 文字セットと重複しています。 任意の制御文字 (32 未満) に対して、バイト単位のスキャンを安全に使用できます。

- 次のコード行について考えてみます。文字列の最後の文字が円記号であるかどうかが確認されている可能性があります。

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   `strlen`は MBCS を認識しないため、マルチバイト文字列の文字数ではなくバイト数を返します。 また、一部のコードページ (932 など) では、' \\ ' (0x5c) は有効なトレイルバイト (は C 文字列) であることに注意して `sz` ください。

   考えられる解決策の1つは、次のようにコードを書き換えることです。

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   このコードでは、MBCS 関数 `_mbsrchr` とを使用し `_mbsinc` ます。 これらの関数は MBCS に対応しているため、' \\ ' 文字と後続バイト ' ' を区別でき \\ ます。 文字列の最後の文字が null (' \ 0 ') の場合、コードはなんらかのアクションを実行します。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)<br/>
[文字の代入](../text/character-assignment.md)
