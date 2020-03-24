---
title: CloakedIid 構造体
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 1cc9e79384bbf4aae44199c2f35331e3afd8fd8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214111"
---
# <a name="cloakediid-structure"></a>CloakedIid 構造体

指定したインターフェイスに IID の一覧でアクセスできない `RuntimeClass`、`Implements`、および `ChainInterfaces` テンプレートを示します。

## <a name="syntax"></a>構文

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
非表示 (クローク) されているインターフェイス。

## <a name="remarks"></a>解説

**CloakedIid**の使用方法の例を次に示します。 `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`CloakedIid`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
