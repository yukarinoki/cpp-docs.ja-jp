---
title: AsWeak 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: d11f55d57f4053fd6d46b727a8ed91b340d1764b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214176"
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
パラメーター *p*の型へのポインター。

*p*<br/>
型のインスタンス。

*pWeak*<br/>
この操作が完了したときに、パラメーター *p*への弱い参照へのポインター。

## <a name="return-value"></a>戻り値

この操作が成功した場合は S_OK。それ以外の場合は、エラーの原因を示すエラー HRESULT。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>参照

[Microsoft::WRL 名前空間](microsoft-wrl-namespace.md)
