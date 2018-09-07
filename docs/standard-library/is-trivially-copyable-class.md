---
title: is_trivially_copyable クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1577f067b398a53ab4f91847f890beaa96f0639f
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102812"
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable クラス

型が自明にコピー可能な型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*は普通にコピー可能型、それ以外の場合は false を保持します。 自明にコピー可能な型とは、自明でないコピー操作、移動操作、デストラクターが含まれない型のことです。 通常、ビット単位のコピーとして実装可能なコピー操作は自明であるとみなされます。 組み込みの型と自明にコピー可能な型の配列は、両方とも自明にコピー可能です。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
