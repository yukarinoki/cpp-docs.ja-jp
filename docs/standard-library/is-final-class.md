---
description: '詳細情報: is_final クラス'
title: is_final クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_final
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
ms.openlocfilehash: 04660309205689e14200cb5d214ce5dc80efb88f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323742"
---
# <a name="is_final-class"></a>is_final クラス

型が `final` とマークされるクラス型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型 *T* がとマークされたクラス型である場合、型述語のインスタンスは true を保持し `final` ます。それ以外の場合は、false を保持します。 *T* がクラス型の場合は、完全な型である必要があります。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[final 指定子](../cpp/final-specifier.md)
