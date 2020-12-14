---
description: '詳細情報: is_trivial クラス'
title: is_trivial クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivial
helpviewer_keywords:
- is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
ms.openlocfilehash: 56e5a3c915893b88228f4a40307d2c1e3c32555d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247658"
---
# <a name="is_trivial-class"></a>is_trivial クラス

型が単純型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivial;
```

### <a name="parameters"></a>パラメーター

*\T*\
照会する型。

## <a name="remarks"></a>解説

型 *T* が自明な型である場合、型の述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 単純型は、スカラー型、普通にコピー可能なクラス型、これらの型の配列と、これらの型の cv-qualified バージョンです。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)
