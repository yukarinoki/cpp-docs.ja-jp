---
title: AsWeak 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dea10165e920c6b0bbd3856fc04e9ec9661e60c4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571335"
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

*T*  
パラメーターの型へのポインター *p*します。

*p*  
型のインスタンス。

*pWeak*  
ときにこの操作が完了すると、パラメーターへの弱い参照へのポインター *p*します。

## <a name="return-value"></a>戻り値

この操作に成功した場合は S_OK、それ以外の場合、エラーのエラーの原因を示す hresult 値。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)