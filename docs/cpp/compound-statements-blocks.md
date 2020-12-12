---
description: '詳細情報: 複合ステートメント (ブロック)'
title: 複合ステートメント (ブロック)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 7defb11a30466949d5a9ca5e86ca1e865fbfe4fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318014"
---
# <a name="compound-statements-blocks"></a>複合ステートメント (ブロック)

複合ステートメントは、中かっこ (**{}**) で囲まれた0個以上のステートメントで構成されます。 複合ステートメントは、ステートメントが想定される場所で使用できます。 複合ステートメントは一般に "ブロック" と呼ばれます。

## <a name="syntax"></a>構文

```
{ [ statement-list ] }
```

## <a name="remarks"></a>解説

次の例では、ステートメントの *ステートメント* 部分として複合ステートメントを使用し **`if`** ます (構文の詳細について [は、if ステートメント](../cpp/if-else-statement-cpp.md) を参照してください)。

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
> 宣言はステートメントであるため、宣言は、 *ステートメントリスト* 内のステートメントの1つにすることができます。 その結果、複合ステートメント内で宣言されているが、明示的に静的として宣言されていない名前には、ローカルなスコープと (オブジェクトの場合) 有効期間があります。 ローカルスコープでの名前の扱いの詳細については、「 [スコープ](../cpp/scope-visual-cpp.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
