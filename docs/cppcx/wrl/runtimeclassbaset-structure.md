---
description: '詳細については、次を参照してください: RuntimeClassBaseT 構造体'
title: RuntimeClassBaseT 構造体
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 48f03a5d54eba455b60646ed47c48e228f07863e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135292"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 構造体

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>パラメーター

*RuntimeClassTypeT*<br/>
1つ以上の [RuntimeClassType](runtimeclasstype-enumeration.md) 列挙子を指定するフラグのフィールドです。

## <a name="remarks"></a>解説

操作にヘルパーメソッド `QueryInterface` を提供し、インターフェイス id を取得します。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                         | 説明
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaseT:: AsIID](#asiid)                           | 指定したインターフェイス ID へのポインターを取得します。
[RuntimeClassBaseT:: GetImplementedIIDS](#getimplementediids) | 指定した型によって実装されているインターフェイス Id の配列を取得します。

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassBaseT`

## <a name="requirements"></a>要件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a> RuntimeClassBaseT:: AsIID

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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
パラメーター *riid* によって指定されたインターフェイス ID を実装する型。

*実装*<br/>
テンプレートパラメーター *T* によって指定された型の変数。

*riid*<br/>
取得するインターフェイス ID。

*ppvObject*<br/>
この操作が成功した場合は、パラメーター *riid* によって指定されたインターフェイスへのポインターへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーを説明する HRESULT です。

### <a name="remarks"></a>解説

指定したインターフェイス ID へのポインターを取得します。

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a> RuntimeClassBaseT:: GetImplementedIIDS

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

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
*Implements* パラメーターの型。

*実装*<br/>
パラメーター *T* によって指定された型へのポインター。

*iidCount*<br/>
取得するインターフェイス Id の最大数。

*iid が*<br/>
この操作が正常に完了した場合は、型 *T* によって実装されたインターフェイス id の配列。

### <a name="return-value"></a>戻り値

成功した場合は S_OK。それ以外の場合は、エラーを説明する HRESULT です。

### <a name="remarks"></a>解説

指定した型によって実装されているインターフェイス Id の配列を取得します。
