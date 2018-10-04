---
title: RuntimeClassBaseT 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c46e89dc11f4c6fe216cfd61c3222a9c52d9e45
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789138"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>パラメーター

*RuntimeClassTypeT*<br/>
1 つまたは複数を指定するフラグのフィールド[RuntimeClassType](../windows/runtimeclasstype-enumeration.md)列挙子。

## <a name="remarks"></a>Remarks

ヘルパー メソッドを提供します`QueryInterface`操作とのインターフェイス Id を取得します。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                         | 説明
------------------------------------------------------------ | -----------------------------------------------------------------------------
[Runtimeclassbaset::asiid](#asiid)                           | 指定したインターフェイス ID へのポインターを取得します。
[Runtimeclassbaset::getimplementediids](#getimplementediids) | インターフェイスの指定された型で実装されている Id の配列を取得します。

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassBaseT`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="asiid"></a>Runtimeclassbaset::asiid

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

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

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、エラーを示す HRESULT。

### <a name="remarks"></a>Remarks

指定したインターフェイス ID へのポインターを取得します。

## <a name="getimplementediids"></a>Runtimeclassbaset::getimplementediids

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
種類、*実装*パラメーター。

*実装*<br/>
パラメーターで指定された型へのポインター *T*します。

*iidCount*<br/>
取得するインターフェイス Id の最大数。

*iid*<br/>
この操作があるインターフェイスの型によって実装された Id の配列では正常に完了する場合*T*します。

### <a name="return-value"></a>戻り値

成功した場合は s_ok を返します。それ以外の場合、エラーを示す HRESULT。

### <a name="remarks"></a>Remarks

インターフェイスの指定された型で実装されている Id の配列を取得します。
