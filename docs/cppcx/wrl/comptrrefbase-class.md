---
title: ComPtrRefBase クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: df4e2aa1ce650fd5b1f04baf2f7c4cd2fb4cff93
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423646"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[Comptr\<t >](comptr-class.md)型、またはその派生型であり、`ComPtr`によって表されるインターフェイスだけではありません。

## <a name="remarks"></a>解説

[Comptrref](comptrref-class.md)クラスの基本クラスを表します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック Typedef

Name            | Description
--------------- | -------------------------------------------------
`InterfaceType` | テンプレートパラメーター *T*の型のシノニム。

### <a name="public-operators"></a>パブリック演算子

Name                                                                       | Description
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase:: operator IInspectable * *](#operator-iinspectable-star-star) | 現在の[ptr_](#ptr)データメンバーを `IInspectable` インターフェイスへのポインターへのポインターにキャストします。
[ComPtrRefBase:: operator IUnknown * *](#operator-iunknown-star-star)         | 現在の[ptr_](#ptr)データメンバーを `IUnknown` インターフェイスへのポインターへのポインターにキャストします。

### <a name="protected-data-members"></a>保護されるデータ メンバー

Name                        | Description
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::p tr_](#ptr) | 現在のテンプレートパラメーターによって指定された型へのポインター。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtrRefBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="operator-iinspectable-star-star"></a>ComPtrRefBase:: operator IInspectable\*\* 演算子

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>解説

現在の[ptr_](#ptr)データメンバーを `IInspectable` インターフェイスへのポインターへのポインターにキャストします。

現在の `ComPtrRefBase` が `IInspectable`から派生していない場合は、エラーが生成されます。

このキャストは、`__WRL_CLASSIC_COM__` が定義されている場合にのみ使用できます。

## <a name="operator-iunknown-star-star"></a>ComPtrRefBase:: operator IUnknown * * 演算子

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>解説

現在の[ptr_](#ptr)データメンバーを `IUnknown` インターフェイスへのポインターへのポインターにキャストします。

現在の `ComPtrRefBase` が `IUnknown`から派生していない場合は、エラーが生成されます。

## <a name="ptr"></a>ComPtrRefBase::p tr_

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
T* ptr_;
```

### <a name="remarks"></a>解説

現在のテンプレートパラメーターによって指定された型へのポインター。 `ptr_` は、保護されたデータメンバーです。
