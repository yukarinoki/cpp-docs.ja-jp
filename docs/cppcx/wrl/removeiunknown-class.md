---
description: 詳細については、「RemoveIUnknown クラス」を参照してください。
title: RemoveIUnknown クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: 0ef00ee9859a27252550aaeec6fb9b4f9ef2d5b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278728"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
クラス。

## <a name="remarks"></a>解説

は、ベースの型に相当する型を作成し `IUnknown` ますが、非仮想 `QueryInterface` の、 `AddRef` 、および `Release` メンバー関数を持ちます。

既定では、COM メソッドは、仮想メソッド、メソッド、およびメソッドを提供し `QueryInterface` `AddRef` `Release` ます。 ただし、では、 `ComPtr` 仮想メソッドのオーバーヘッドを必要としません。 `RemoveIUnknown` プライベート、非仮想、、、およびの各メソッドを提供することによって、オーバーヘッドを回避し `QueryInterface` `AddRef` `Release` ます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`ReturnType`|テンプレートパラメーター *T* と等価で、非仮想メンバーを持つ型のシノニム `IUnknown` 。|

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`RemoveIUnknown`

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
