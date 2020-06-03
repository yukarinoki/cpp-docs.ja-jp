---
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
ms.openlocfilehash: 06a9f73e00d541b0e5bcbe20c57befe4a67c5132
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375718"
---
# <a name="runtimeclassbaset-structure"></a>RuntimeClassBaseT 構造体

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>パラメーター

*クラスタイプT*<br/>
1 つ以上の[ランタイムクラスタイプ](runtimeclasstype-enumeration.md)列挙子を指定するフラグのフィールド。

## <a name="remarks"></a>解説

操作とインターフェイス`QueryInterface`ID を取得するためのヘルパー メソッドを提供します。

## <a name="members"></a>メンバー

### <a name="protected-methods"></a>プロテクト メソッド

名前                                                         | 説明
------------------------------------------------------------ | -----------------------------------------------------------------------------
[クラスベース::AsIID](#asiid)                           | 指定したインターフェイス ID へのポインターを取得します。
[クラスベース::取得実装IIDS](#getimplementediids) | 指定した型によって実装されるインターフェイス ID の配列を取得します。

## <a name="inheritance-hierarchy"></a>継承階層

`RuntimeClassBaseT`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a>クラスベース::AsIID

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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
パラメータ*riid*で指定されたインターフェイス ID を実装する型。

*実装*<br/>
テンプレート パラメータ*T*で指定された型の変数。

*riid*<br/>
取得するインターフェイス ID。

*オブジェクト*<br/>
この操作が成功した場合は、パラメータ*riid*で指定されたインターフェイスへのポインタを指します。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、エラーを説明する HRESULT。

### <a name="remarks"></a>解説

指定したインターフェイス ID へのポインターを取得します。

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a>クラスベース::取得実装IIDS

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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
*実装*パラメーターの型。

*実装*<br/>
パラメーター *T*で指定された型へのポインター。

*iidカウント*<br/>
取得するインターフェイス ID の最大数。

*Iid*<br/>
この操作が正常に完了すると、型 T によって実装されたインターフェイス ID の配列が*表示*されます。

### <a name="return-value"></a>戻り値

成功した場合はS_OK。それ以外の場合は、エラーを説明する HRESULT。

### <a name="remarks"></a>解説

指定した型によって実装されるインターフェイス ID の配列を取得します。
