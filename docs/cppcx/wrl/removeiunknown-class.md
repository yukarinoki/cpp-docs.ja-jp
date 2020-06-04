---
title: RemoveIUnknown クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: cfcdefbb8d7cd12d2ebf99710f595fdd2fc16f76
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213617"
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

`IUnknown`ベースの型と等価な型を作成しますが、非仮想 `QueryInterface`、`AddRef`、および `Release` のメンバー関数があります。

既定では、COM メソッドは、仮想 `QueryInterface`、`AddRef`、および `Release` メソッドを提供します。 ただし、`ComPtr` では、仮想メソッドのオーバーヘッドを必要としません。 `RemoveIUnknown` は、プライベート、非仮想 `QueryInterface`、`AddRef`、および `Release` の各メソッドを提供することによって、オーバーヘッドを解消します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|Name|説明|
|----------|-----------------|
|`ReturnType`|テンプレートパラメーター *T*と等価であるが、非仮想 `IUnknown` メンバーを持つ型のシノニム。|

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`RemoveIUnknown`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
