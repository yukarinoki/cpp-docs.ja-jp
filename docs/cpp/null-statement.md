---
description: 詳細については、「Null ステートメント」を参照してください。
title: Null ステートメント
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 1aa488da395cf84ae9ef6d78939f1f1e3019c572
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146173"
---
# <a name="null-statement"></a>Null ステートメント

"Null ステートメント" は、 *式* が指定されていない式ステートメントです。 言語の構文でステートメントが必要でも、式の評価が不要な場合に便利です。 1 つのセミコロンで構成されます。

null ステートメントは、イテレーション ステートメントのプレースホルダーや、複合ステートメントまたは関数の最後でラベルを付けるステートメントとしてよく使用されます。

次のコードは、ある文字列を別の文字列にコピーする方法を示しており、null ステートメントが組み込まれています。

```cpp
// null_statement.cpp
char *myStrCpy( char *Dest, const char *Source )
{
    char *DestStart = Dest;

    // Assign value pointed to by Source to
    // Dest until the end-of-string 0 is
    // encountered.
    while( *Dest++ = *Source++ )
        ;   // Null statement.

    return DestStart;
}

int main()
{
}
```

## <a name="see-also"></a>関連項目

[式ステートメント](../cpp/expression-statement.md)
