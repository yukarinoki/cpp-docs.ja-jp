---
title: InterfaceListHelper 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceListHelper
helpviewer_keywords:
- InterfaceListHelper structure
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
ms.openlocfilehash: 1a7b4c19bbcdd4161e9078274f18f96a48f9e7d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213851"
---
# <a name="interfacelisthelper-structure"></a>InterfaceListHelper 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <
    typename T0,
    typename T1 = Nil,
    typename T2 = Nil,
    typename T3 = Nil,
    typename T4 = Nil,
    typename T5 = Nil,
    typename T6 = Nil,
    typename T7 = Nil,
    typename T8 = Nil,
    typename T9 = Nil
>
struct InterfaceListHelper;

template <typename T0>
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;
```

### <a name="parameters"></a>パラメーター

*T0*<br/>
テンプレートパラメーター0。これは必須です。

*T1*<br/>
既定では、テンプレートパラメーター1が指定されていません。

*T2*<br/>
既定では、テンプレートパラメーター2が指定されていません。3番目のテンプレートパラメーター。

*T3*<br/>
既定では、テンプレートパラメーター3が指定されていません。

*T4*<br/>
既定では、テンプレートパラメーター4が指定されていません。

*T5*<br/>
既定では、テンプレートパラメーター5が指定されていません。

*T6*<br/>
既定では、テンプレートパラメーター6は指定されていません。

*T7*<br/>
既定では、テンプレートパラメーター7が指定されていません。

*T8*<br/>
テンプレートパラメーター8。既定では指定されていません。

*T9*<br/>
テンプレートパラメーター9。既定では指定されていません。

## <a name="remarks"></a>解説

指定されたテンプレートパラメーター引数を再帰的に適用して、`InterfaceList` 型を構築します。

**InterfaceListHelper**テンプレートでは、テンプレートパラメーター *T0*を使用して `InterfaceList` 構造の最初のデータメンバーを定義し、その後、 **InterfaceListHelper**テンプレートを残りのテンプレートパラメーターに再帰的に適用します。 残りのテンプレートパラメーターがない場合、 **InterfaceListHelper**は停止します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|Name|説明|
|----------|-----------------|
|`TypeT`|InterfaceList 型のシノニム。|

## <a name="inheritance-hierarchy"></a>継承階層

`InterfaceListHelper`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
