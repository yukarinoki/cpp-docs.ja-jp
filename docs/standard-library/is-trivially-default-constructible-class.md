---
description: '詳細情報: is_trivially_default_constructible クラス'
title: is_trivially_default_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: 3686dab86b8bf04fe7629b53651988d7ccef161e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118408"
---
# <a name="is_trivially_default_constructible-class"></a>is_trivially_default_constructible クラス

型に自明な既定コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型 *Ty* が自明なコンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

クラス *Ty* の既定のコンストラクターは、次のような場合に自明です。

- 暗黙的に宣言された既定のコンス トラクターである

- クラス *Ty* に仮想関数がありません。

- クラス *Ty* に仮想基底がありません

- *クラスの* すべての直接基底に自明なコンストラクターがある

- クラス型のすべての非静的データ メンバーのクラスに自明なコンストラクターがある

- クラスの型配列のすべての非静的データ メンバーのクラスに自明なコンストラクターがある

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
