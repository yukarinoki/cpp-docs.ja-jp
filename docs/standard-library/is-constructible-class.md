---
title: is_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f9e3f71a0d8647000f77863ecc9243b069f0521
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955832"
---
# <a name="isconstructible-class"></a>is_constructible クラス

指定した引数型の使用時に型を構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>パラメーター

*T*照会する型。

*Args*のコンス トラクターで一致させる引数型*T*します。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*の引数の型を使用して構築できる*Args*、それ以外の場合は false を保持します。 型*T*を構築できる場合は、変数定義`T t(std::declval<Args>()...);`が整形式。 両方*T*とすべての種類で*Args*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
