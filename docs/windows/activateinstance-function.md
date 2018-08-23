---
title: ActivateInstance 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2ac6d8722bcdfed06ae97508b0ca7e5bb8ea00a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601453"
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

*T*  
アクティブにする型。

*activatableClassId*  
パラメーターを定義するクラスの ID の名前*T*します。

*インスタンス*  
ときにこの操作が完了したらのインスタンスへの参照を*T*します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、エラーのエラーの原因を示す hresult 値。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**Namespace:** windows::foundation

## <a name="see-also"></a>関連項目

[Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)