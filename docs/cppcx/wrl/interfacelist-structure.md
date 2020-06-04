---
title: InterfaceList 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 7fd06f71bc4d8097366dc0e87d7ff92c5a12a790
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213864"
---
# <a name="interfacelist-structure"></a>InterfaceList 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
インターフェイス名。再帰リスト内の最初のインターフェイス。

*U*<br/>
インターフェイス名。再帰リスト内の残りのインターフェイス。

## <a name="remarks"></a>解説

インターフェイスの再帰的リストを作成するために使用します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|Name|説明|
|----------|-----------------|
|`FirstT`|テンプレートパラメーター *T*のシノニム。|
|`RestT`|テンプレートパラメーター *U*のシノニム。|

## <a name="inheritance-hierarchy"></a>継承階層

`InterfaceList`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
