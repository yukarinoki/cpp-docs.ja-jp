---
title: __if_not_exists ステートメント
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: d7d172df584200ccc508b281147abf3fa7774952
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629113"
---
# <a name="ifnotexists-statement"></a>__if_not_exists ステートメント

**_ _If_not_exists**ステートメントは、指定した識別子が存在するかどうかをテストします。 ID が存在しない場合、指定されたステートメント ブロックが実行されます。

## <a name="syntax"></a>構文

```
__if_not_exists ( identifier ) { 
statements
};
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*identifier*|存在をテストしたい識別子。|
|*ステートメント*|1 つ以上の場合に実行されるステートメント*識別子*存在しません。|

## <a name="remarks"></a>Remarks

> [!CAUTION]
>  最も信頼性の高い結果を実現するために使用して、 **_ _if_not_exists**次の制約の下のステートメント。

- 適用、 **_ _if_not_exists**テンプレートではなく、唯一の単純型のステートメント。

- 適用、 **_ _if_not_exists**ステートメントの内部または外部クラスの識別子。 適用されません、 **_ _if_not_exists**ローカル変数にステートメント。

- 使用して、 **_ _if_not_exists**関数の本体でのみステートメント。 関数の本文の外側、 **_ _if_not_exists**ステートメントは、型を完全に定義のみをテストできます。

- オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。

補完する、 **_ _if_not_exists**ステートメントは、 [_ _if_exists](../cpp/if-exists-statement.md)ステートメント。

## <a name="example"></a>例

使用する方法の例については **_ _if_not_exists**を参照してください[_ _if_exists ステートメント](../cpp/if-exists-statement.md)します。

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[__if_exists ステートメント](../cpp/if-exists-statement.md)