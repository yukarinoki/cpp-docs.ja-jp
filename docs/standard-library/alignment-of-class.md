---
title: alignment_of Class | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d9ba59d7f1539f690d7b04c70139c263490368
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="alignmentof-class"></a>alignment_of クラス

指定された型のアラインメントを取得します。 この構造体は、[alignof](../cpp/alignof-and-alignas-cpp.md) の観点から実装されています。 単にアラインメント値を照会すればよい場合は、`alignof` を直接使用します。 タグ ディスパッチを行うときのように整数定数が必要な場合は、alignment_of を使用します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

## <a name="remarks"></a>コメント

型クエリは、型 `Ty` のアラインメントの値を保持します。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage クラス](../standard-library/aligned-storage-class.md)<br/>
