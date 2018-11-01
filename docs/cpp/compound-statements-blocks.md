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
ms.openlocfilehash: 6aef2a0b5716ab501fabe80f0dda15080abe3ff5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591790"
---
# <a name="compound-statements-blocks"></a>複合ステートメント (ブロック)

複合ステートメントは、中かっこで囲まれた 0 個以上のステートメントで構成されています (**{}**)。 複合ステートメントは、ステートメントが想定される場所で使用できます。 複合ステートメントは一般に "ブロック" と呼ばれます。

## <a name="syntax"></a>構文

```
{ [ statement-list ] }
```

## <a name="remarks"></a>Remarks

次の例として複合ステートメントを使用して、*ステートメント*の一部、**場合**ステートメント (を参照してください[if ステートメント](../cpp/if-else-statement-cpp.md)構文の詳細について)。

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
>  宣言が内のステートメントのいずれかを指定できます、宣言ステートメントであるため、*ステートメント リスト*します。 その結果、複合ステートメント内で宣言されているが、明示的に静的として宣言されていない名前には、ローカルなスコープと (オブジェクトの場合) 有効期間があります。 参照してください[スコープ](../cpp/scope-visual-cpp.md)詳細については、ローカル スコープの名前を処理します。

## <a name="see-also"></a>関連項目

[C++ ステートメントの概要](../cpp/overview-of-cpp-statements.md)