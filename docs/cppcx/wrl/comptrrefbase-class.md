---
description: '詳細情報: ComPtrRefBase クラス'
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
ms.openlocfilehash: 4dce58e8292092084916c24153d543f2a45856fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273138"
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
によって表されるインターフェイスだけでなく、 [Comptr \<T> ](comptr-class.md)型またはそれから派生した型 `ComPtr` 。

## <a name="remarks"></a>解説

[Comptrref](comptrref-class.md)クラスの基本クラスを表します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前            | 説明
--------------- | -------------------------------------------------
`InterfaceType` | テンプレートパラメーター *T* の型のシノニム。

### <a name="public-operators"></a>パブリック演算子

名前                                                                       | 説明
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase:: operator IInspectable * *](#operator-iinspectable-star-star) | 現在の [ptr_](#ptr) データメンバーをインターフェイスへのポインターへのポインターにキャストし `IInspectable` ます。
[ComPtrRefBase:: operator IUnknown * *](#operator-iunknown-star-star)         | 現在の [ptr_](#ptr) データメンバーをインターフェイスへのポインターへのポインターにキャストし `IUnknown` ます。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::p tr_](#ptr) | 現在のテンプレートパラメーターによって指定された型へのポインター。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtrRefBase`

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft:: WRL::D etails

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>ComPtrRefBase:: operator IInspectable \* \* 演算子

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>解説

現在の [ptr_](#ptr) データメンバーをインターフェイスへのポインターへのポインターにキャストし `IInspectable` ます。

現在のがから派生していない場合、エラーが生成され `ComPtrRefBase` `IInspectable` ます。

このキャストは、が定義されている場合にのみ使用でき `__WRL_CLASSIC_COM__` ます。

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a> ComPtrRefBase:: operator IUnknown * * 演算子

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>解説

現在の [ptr_](#ptr) データメンバーをインターフェイスへのポインターへのポインターにキャストし `IUnknown` ます。

現在のがから派生していない場合、エラーが生成され `ComPtrRefBase` `IUnknown` ます。

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a> ComPtrRefBase::p tr_

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
T* ptr_;
```

### <a name="remarks"></a>解説

現在のテンプレートパラメーターによって指定された型へのポインター。 `ptr_` 保護されるデータメンバーを示します。
