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
ms.openlocfilehash: d1109e769352d412df8348822e05b66063159ee8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214228"
---
# <a name="activateinstance-function"></a>ActivateInstance 関数

指定したクラス ID で定義されている、指定した型のインスタンスを登録して取得します。

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
パラメーター *T*を定義するクラス ID の名前。

*インスタンス (instance)*<br/>
この操作が完了したときに、 *T*のインスタンスへの参照。

## <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーの原因を示すエラー HRESULT。

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Windows:: Foundation

## <a name="see-also"></a>参照

[Windows::Foundation 名前空間](windows-foundation-namespace.md)
