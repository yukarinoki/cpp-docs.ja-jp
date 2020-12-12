---
description: '詳細情報: is_trivially_copy_constructible クラス'
title: is_trivially_copy_constructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: c247e81f52ad98e546a840bb38938fe15bc9b302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118525"
---
# <a name="is_trivially_copy_constructible-class"></a>is_trivially_copy_constructible クラス

型に自明なコピー コンストラクターが含まれるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型 *T* が自明なコピーコンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

クラス t のコピーコンストラクターは、暗黙的に宣言されている場合は *単純です。* *クラス t には* 仮想関数も仮想基底もありません。 *クラス t の* すべての直接基底クラスに自明なコピーコンストラクターがあるため、クラス型のすべての非静的データメンバーのクラスに自明なコピーコンストラクターが含まれます。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
