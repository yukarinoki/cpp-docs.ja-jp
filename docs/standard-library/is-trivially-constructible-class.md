---
title: is_trivially_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 789839482e623e94172bbd55342d257c2b031614
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109370"
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible クラス

指定した引数型の使用時に型を自明に構築できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

*Args*<br/>
引数の型のコンス トラクターで一致するように*T*します。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*の引数の型を使用して自明に構築できるは*Args*、それ以外の場合は false を保持します。 型*T*が自明に構築できる場合は、変数定義`T t(std::declval<Args>()...);`整形式では、重要な操作を呼び出していない呼ばれます。 両方*T*とすべての種類で*Args*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
