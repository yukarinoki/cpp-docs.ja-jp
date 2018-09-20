---
title: Runtimeclassbaset::asiid メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7092153e49fdb40fc32fb1cbee5bc2376080ff4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391879"
---
# <a name="runtimeclassbasetasiid-method"></a>RuntimeClassBaseT::AsIID メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
パラメーターで指定されたインターフェイス ID を実装する型*riid*します。

*実装*<br/>
テンプレート パラメーターで指定された型の変数*T*します。

*riid*<br/>
取得するインターフェイス ID。

*ppvObject*<br/>
ポインター-に-、- へのポインター、インターフェイスがパラメーターで指定されたこの操作が成功した場合は、 *riid*します。

## <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、エラーを示す HRESULT。

## <a name="remarks"></a>Remarks

指定したインターフェイス ID へのポインターを取得します。

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[RuntimeClassBaseT 構造体](../windows/runtimeclassbaset-structure.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)