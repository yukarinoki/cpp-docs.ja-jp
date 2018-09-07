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
ms.openlocfilehash: f94390b96770a84b35de67f4d3a38644132d8ce8
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107441"
---
# <a name="isconstructible-class"></a>is_constructible クラス

指定した引数型の使用時に型を構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

*Args*<br/>
引数の型のコンス トラクターで一致するように*T*します。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*の引数の型を使用して構築できる*Args*、それ以外の場合は false を保持します。 型*T*を構築できる場合は、変数定義`T t(std::declval<Args>()...);`が整形式。 両方*T*とすべての種類で*Args*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
