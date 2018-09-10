---
title: is_nothrow_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0726839baadf5265d604f231615f1add069ccfcb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106528"
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible クラス

指定された引数型の使用時に型を構築できるかどうか、およびスローしないと判明しているかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

*Args*<br/>
引数の型のコンス トラクターで一致するように*T*します。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*の引数の型を使用して構築できる*Args*、コンス トラクターがコンパイラによってスローしないと判明あり、それ以外の場合は false を保持します。 型*T*を構築できる場合は、変数定義`T t(std::declval<Args>()...);`が整形式。 両方*T*とすべての種類で*Args*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
