---
title: 複合ステートメント (ブロック)
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 60d7e88c5ccccac5a1d967a91c8a82dd954d9afc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337339"
---
# <a name="compound-statements-blocks"></a>複合ステートメント (ブロック)

複合文は、中括弧 (**{ }**) で囲まれた 0 個以上のステートメントで構成されます。 複合ステートメントは、ステートメントが想定される場所で使用できます。 複合ステートメントは一般に "ブロック" と呼ばれます。

## <a name="syntax"></a>構文

```
{ [ statement-list ] }
```

## <a name="remarks"></a>解説

次の例では、構文の詳細については **、if**ステートメントの*ステートメント*部分としてコンパウンド[ステートメント](../cpp/if-else-statement-cpp.md)を使用しています。

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
> 宣言はステートメントであるため、宣言は*ステートメント リスト*内のステートメントの 1 つになります。 その結果、複合ステートメント内で宣言されているが、明示的に静的として宣言されていない名前には、ローカルなスコープと (オブジェクトの場合) 有効期間があります。 ローカル[スコープを使用した](../cpp/scope-visual-cpp.md)名前の処理の詳細については、「スコープ」を参照してください。

## <a name="see-also"></a>関連項目

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)
