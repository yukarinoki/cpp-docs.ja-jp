---
description: '詳細情報: alignment_of クラス'
title: alignment_of クラス
ms.date: 12/11/2019
f1_keywords:
- type_traits/std::alignment_of
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
ms.openlocfilehash: 7e1eeafb259b71f24cb272c079cdb485bb8e1b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163653"
---
# <a name="alignment_of-class"></a>alignment_of クラス

指定された型のアラインメントを取得します。 この構造体は、の観点から実装されて [`alignof`](../cpp/alignment-cpp-declarations.md) います。 **`alignof`** 単にアラインメント値を照会する必要がある場合は、を直接使用します。 `alignment_of`タグディスパッチを行うときなど、整数定数が必要な場合は、を使用します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型クエリは、型 *Ty* のアラインメントの値を保持します。

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[`<type_traits>`](type-traits.md)\
[`aligned_storage` 講義](aligned-storage-class.md)
