---
title: __if_not_exists ステートメント
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 1118f9fcca525b2b2d5869fb507ee974d2b0d28f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374141"
---
# <a name="__if_not_exists-statement"></a>__if_not_exists ステートメント

**__if_not_exists**ステートメントは、指定された識別子が存在するかどうかをテストします。 ID が存在しない場合、指定されたステートメント ブロックが実行されます。

## <a name="syntax"></a>構文

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*識別子*|存在をテストしたい識別子。|
|*ステートメント*|*識別子*が存在しない場合に実行する 1 つ以上のステートメント。|

## <a name="remarks"></a>解説

> [!CAUTION]
> 最も信頼性の高い結果を得るには、次の制約の下で **__if_not_exists**ステートメントを使用します。

- **__if_not_exists**ステートメントは、テンプレートではなく単純型にのみ適用します。

- クラスの内部または外部の識別子に **__if_not_exists**ステートメントを適用します。 **__if_not_exists**ステートメントをローカル変数に適用しないでください。

- **__if_not_exists**ステートメントは、関数の本体でのみ使用してください。 関数の本体の外側では **、__if_not_exists**ステートメントは完全に定義された型のみをテストできます。

- オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。

**__if_not_exists**ステートメントの補数は[、__if_exists](../cpp/if-exists-statement.md)ステートメントです。

## <a name="example"></a>例

**__if_not_existsの**使用方法の例については[、「__if_exists ステートメント](../cpp/if-exists-statement.md)」を参照してください。

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[__if_exists声明](../cpp/if-exists-statement.md)
