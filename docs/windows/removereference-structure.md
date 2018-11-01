---
title: RemoveReference 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
ms.openlocfilehash: fcb4d132198fff8dd6e2d55011f0c3a174b73f40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613695"
---
# <a name="removereference-structure"></a>RemoveReference 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<class T>
struct RemoveReference;

template<class T>
struct RemoveReference<T&>;

template<class T>
struct RemoveReference<T&&>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
クラス。

## <a name="remarks"></a>Remarks

指定されたクラス テンプレートのパラメーターから参照または右辺値参照の特徴を取り除きます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`Type`|クラス テンプレート パラメーターのシノニム。|

## <a name="inheritance-hierarchy"></a>継承階層

`RemoveReference`

## <a name="requirements"></a>必要条件

**ヘッダー:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)