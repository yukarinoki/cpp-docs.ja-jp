---
title: is_move_constructible クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f9c0b381cfbf32327eef4b29a9dbe23f1d991f1
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108773"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible クラス

型に移動コンストラクターが存在するかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
評価される型

## <a name="remarks"></a>Remarks

型の場合に true に評価される型の述語*T*移動操作を使用して構築できます。 この述語は `is_constructible<T, T&&>` と同じです。

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
