---
title: AsWeak 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: 1332aa140a8298590ad83158e0ec1b75035c4e92
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785242"
---
# <a name="asweak-function"></a>AsWeak 関数

指定されたインスタンスへの弱い参照を取得します。

## <a name="syntax"></a>構文

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
パラメーターの型へのポインター *p*します。

*p*<br/>
型のインスタンス。

*pWeak*<br/>
ときにこの操作が完了すると、パラメーターへの弱い参照へのポインター *p*します。

## <a name="return-value"></a>戻り値

この操作に成功した場合は S_OK、それ以外の場合、エラーのエラーの原因を示す hresult 値。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::wrl

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)