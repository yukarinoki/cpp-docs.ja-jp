---
title: EnableIf 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: 44c6293b56e9e03c23d0d8cebf2a112e6fcf3664
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214033"
---
# <a name="enableif-structure"></a>EnableIf 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
型。

*b*<br/>
ブール式です。

## <a name="remarks"></a>解説

最初のテンプレートパラメーターが**true**と評価された場合に、2番目のテンプレートパラメーターによって指定された型のデータメンバーを定義します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|Name|説明|
|----------|-----------------|
|`type`|テンプレートパラメーター *b*が**true**と評価された場合、部分的特殊化は `T`型である `type` データメンバーを定義します。|

## <a name="inheritance-hierarchy"></a>継承階層

`EnableIf`

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>参照

[Microsoft::WRL::Details 名前空間](microsoft-wrl-details-namespace.md)
