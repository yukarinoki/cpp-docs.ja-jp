---
description: 詳細については、「__if_not_exists ステートメント」を参照してください。
title: __if_not_exists ステートメント
ms.date: 11/04/2016
f1_keywords:
- __if_not_exists_cpp
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
ms.openlocfilehash: 29f98c2d07858077207c10dfcdd45b9ce51268e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113949"
---
# <a name="__if_not_exists-statement"></a>__if_not_exists ステートメント

ステートメントは、 **`__if_not_exists`** 指定された識別子が存在するかどうかをテストします。 ID が存在しない場合、指定されたステートメント ブロックが実行されます。

## <a name="syntax"></a>構文

```
__if_not_exists ( identifier ) {
statements
};
```

#### <a name="parameters"></a>パラメーター

*identifier*\
存在をテストしたい識別子。

*命令*\
*識別子* が存在しない場合に実行する1つ以上のステートメント。

## <a name="remarks"></a>解説

> [!CAUTION]
> 最も信頼性の高い結果を得るには、 **`__if_not_exists`** 次の制約の下でステートメントを使用します。

- **`__if_not_exists`** テンプレートではなく、単純型のみにステートメントを適用します。

- **`__if_not_exists`** クラスの内部または外部の両方で識別子にステートメントを適用します。 **`__if_not_exists`** ローカル変数にステートメントを適用しないでください。

- ステートメントは、 **`__if_not_exists`** 関数の本体でのみ使用してください。 関数の本体以外では、ステートメントは **`__if_not_exists`** 完全に定義された型のみをテストできます。

- オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。

ステートメントの補数は、 **`__if_not_exists`** [__if_exists](../cpp/if-exists-statement.md) ステートメントです。

## <a name="example"></a>例

の使用方法の例については **`__if_not_exists`** 、「 [__if_exists ステートメント](../cpp/if-exists-statement.md)」を参照してください。

## <a name="see-also"></a>関連項目

[選択ステートメント](../cpp/selection-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[__if_exists ステートメント](../cpp/if-exists-statement.md)
