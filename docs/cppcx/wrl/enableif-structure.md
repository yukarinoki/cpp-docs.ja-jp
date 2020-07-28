---
title: EnableIf 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: f43166920f3582ab681b67d2c89563dcf78ff0f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220497"
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

最初のテンプレートパラメーターがに評価される場合、2番目のテンプレートパラメーターによって指定された型のデータメンバーを定義し **`true`** ます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|テンプレートパラメーター *b*がと評価 **`true`** された場合、部分的特殊化はデータメンバー `type` を型として定義し `T` ます。|

## <a name="inheritance-hierarchy"></a>継承階層

`EnableIf`

## <a name="requirements"></a>必要条件

**ヘッダー:** 内部 .h

**名前空間:** Microsoft:: WRL::D etails

## <a name="see-also"></a>関連項目

[Microsoft:: WRL::D etails 名前空間](microsoft-wrl-details-namespace.md)
