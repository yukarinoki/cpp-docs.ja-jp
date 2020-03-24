---
title: __if_not_exists ステートメント
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 7372ac127a7b4dd5c05d58cfecca25f87690b0ae
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178187"
---
# <a name="__if_not_exists-statement"></a>__if_not_exists ステートメント

**__If_not_exists**ステートメントは、指定された識別子が存在するかどうかをテストします。 ID が存在しない場合、指定されたステートメント ブロックが実行されます。

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
|*命令*|*識別子*が存在しない場合に実行する1つ以上のステートメント。|

## <a name="remarks"></a>解説

> [!CAUTION]
>  最も信頼性の高い結果を得るには、次の制約の下で **__if_not_exists**ステートメントを使用します。

- **__If_not_exists**ステートメントは、テンプレートではなく、単純型のみに適用します。

- クラスの内部または外部の両方で識別子に **__if_not_exists**ステートメントを適用します。 **__If_not_exists**ステートメントをローカル変数に適用しないでください。

- **__If_not_exists**ステートメントは、関数の本体でのみ使用してください。 関数の本体以外では、 **__if_not_exists**ステートメントは完全に定義された型のみをテストできます。

- オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。

**__If_not_exists**ステートメントの補数は、 [__if_exists](../cpp/if-exists-statement.md)ステートメントです。

## <a name="example"></a>例

**__If_not_exists**の使用方法の例については、「 [__if_exists ステートメント](../cpp/if-exists-statement.md)」を参照してください。

## <a name="see-also"></a>参照

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[__if_exists ステートメント](../cpp/if-exists-statement.md)
