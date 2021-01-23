---
description: pragmaMicrosoft C/c + + での strict_gs_check ディレクティブの詳細については、こちらを参照してください。
title: strict_gs_check pragma
ms.date: 01/22/2021
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
- pragma, strict_gs_check
no-loc:
- pragma
ms.openlocfilehash: 4a224c42dc30227e5bd9a7142c807f7cebc34614
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713156"
---
# <a name="strict_gs_check-no-locpragma"></a>`strict_gs_check` pragma

これに pragma より、セキュリティチェックが強化されます。

## <a name="syntax"></a>構文

> **`#pragma strict_gs_check(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**\
> **`#pragma strict_gs_check( pop )`**

## <a name="remarks"></a>解説

コンパイラが関数スタックにランダム クッキーを挿入し、スタック ベースのバッファー オーバーランのカテゴリの検出に役立つように指示します。 既定では、 **`/GS`** コンパイラオプションは、すべての関数のクッキーを挿入しません。 詳細については、「 [ `/GS` (バッファーセキュリティチェック)](../build/reference/gs-buffer-security-check.md)」を参照してください。

を使用してをコンパイルし、を **`/GS`** 有効に **`strict_gs_check`** します。

これ pragma は、有害な可能性のあるデータに公開されているコードモジュールで使用します。 **`strict_gs_check`** は積極的であり、 pragma この防御を必要としない関数に適用されますが、結果として得られるアプリケーションのパフォーマンスへの影響を最小限に抑えるように最適化されています。

これを使用する場合でも pragma 、セキュリティで保護されたコードを記述することをお勧めします。 つまり、コードにバッファーオーバーランがないことを確認してください。 **`strict_gs_check`** では、コード内に残っているバッファーオーバーランからアプリケーションを保護できます。

## <a name="example"></a>例

このサンプルでは、配列をローカル配列にコピーするときに、バッファーオーバーランが発生します。 このコードをでコンパイルする場合、 **`/GS`** 配列のデータ型はポインターであるため、スタックにクッキーは挿入されません。 を追加すると、 **`strict_gs_check`** pragma スタック cookie が関数スタックに強制的に追加されます。

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // **_ This buffer is subject to being overrun!! _*_
    void _pReversed[20];

    // Reverse the array into a temporary buffer
    for (size_t j = 0, i = cData; i ; --i, ++j)
        // *** Possible buffer overrun!! ***
            pReversed[j] = pData[i];

    // Copy temporary buffer back into input/output buffer
    for (size_t i = 0; i < cData ; ++i)
        pData[i] = pReversed[i];

    return pData;
}
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)\
[`/GS` (バッファーセキュリティチェック)](../build/reference/gs-buffer-security-check.md)
