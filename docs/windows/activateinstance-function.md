---
title: ActivateInstance 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 65648d62657bf989d4a08660e0fd7724511350c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666298"
---
# <a name="activateinstance-function"></a>ActivateInstance 関数

登録し、指定したクラス ID で定義されている指定された型のインスタンスを取得します。

## <a name="syntax"></a>構文

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
アクティブにする型。

*activatableClassId*<br/>
パラメーターを定義するクラスの ID の名前*T*します。

*インスタンス*<br/>
ときにこの操作が完了したらのインスタンスへの参照を*T*します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、エラーのエラーの原因を示す hresult 値。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**Namespace:** windows::foundation

## <a name="see-also"></a>関連項目

[Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)