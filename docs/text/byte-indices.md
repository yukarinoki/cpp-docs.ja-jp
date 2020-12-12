---
description: 詳細については、「バイトインデックス」を参照してください。
title: バイト インデックス
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 5ee4b2cb8611893c71f5c6597e619cc73e2848ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187560"
---
# <a name="byte-indices"></a>バイト インデックス

次のヒントを参考にしてください。

- 文字列に対してバイト単位のインデックスを使用すると、ポインター操作によって発生するものと同様の問題が発生します。 次の例では、文字列を円記号でスキャンします。

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   これは、先行バイトではなく、後続バイトにインデックスを作成する可能性があるため、を指していない可能性があり `character` ます。

- 前の問題を解決するには、 [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) 関数を使用します。

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   これは、先頭バイトに正しくインデックスを付けます。したがって、に `character` なります。 関数は、 `_mbclen` 文字のサイズ (1 または2バイト) を決定します。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)<br/>
[文字列の最後の文字](../text/last-character-in-a-string.md)
