---
description: '詳細情報: is_nothrow_destructible クラス'
title: is_nothrow_destructible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_nothrow_destructible
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
ms.openlocfilehash: 017cc6de7ce5c618fcc3f47540efd34b5fdc40a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323619"
---
# <a name="is_nothrow_destructible-class"></a>is_nothrow_destructible クラス

型が破棄可能で、デストラクタ―がスローしないとコンパイラに判明しているかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_nothrow_destructible;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型 *T* が破棄可能な型の場合、型の述語のインスタンスは true を保持し、デストラクターはコンパイラがスローしないことを認識します。 それ以外の場合、false を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
