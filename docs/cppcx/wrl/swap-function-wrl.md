---
description: '詳細情報: Swap 関数 (WRL)'
title: Swap 関数 (WRL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Swap
ms.assetid: ed134a08-ceb7-4279-aa02-a183c3a426ea
ms.openlocfilehash: e81c9e332c6c6a69f475f53132689dc99fffdfee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186195"
---
# <a name="swap-function-wrl"></a>Swap 関数 (WRL)

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
WRL_NOTHROW inline void Swap(
   _Inout_ T& left,
   _Inout_ T& right
);
```

### <a name="parameters"></a>パラメーター

*左側*<br/>
最初の引数。

*そうです*<br/>
2 番目の引数。

## <a name="return-value"></a>戻り値

## <a name="remarks"></a>解説

指定した2つの引数の値を交換します。

## <a name="requirements"></a>要件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
