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
ms.openlocfilehash: 4f6dd6449cf8135ad14486d64cea95d8329e0014
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372618"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
[ComPtr\<T>](comptr-class.md)型、または この型から派生した型は、 で表されるインターフェイスだけではありません。 `ComPtr`

## <a name="remarks"></a>解説

[クラス](comptrref-class.md)の基本クラスを表します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前            | 説明
--------------- | -------------------------------------------------
`InterfaceType` | テンプレート パラメータ*T*の型のシノニム。

### <a name="public-operators"></a>パブリック演算子

名前                                                                       | 説明
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[オペレーター IInspectable**](#operator-iinspectable-star-star) | 現在の[ptr_](#ptr)データ メンバーを`IInspectable`、ポインターからインターフェイスへのポインターにキャストします。
[オペレーター IUnknown**](#operator-iunknown-star-star)         | 現在の[ptr_](#ptr)データ メンバーを`IUnknown`、ポインターからインターフェイスへのポインターにキャストします。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------------------------------
[ベース::ptr_](#ptr) | 現在のテンプレート パラメーターで指定された型へのポインター。

## <a name="inheritance-hierarchy"></a>継承階層

`ComPtrRefBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** client.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>オペレーター I 検査可能オペレーター\* \*

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>解説

現在の[ptr_](#ptr)データ メンバーを`IInspectable`、ポインターからインターフェイスへのポインターにキャストします。

現在`ComPtrRefBase`が`IInspectable`から派生していない場合は、エラーが発生します。

このキャストは、定義されている`__WRL_CLASSIC_COM__`場合にのみ使用できます。

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a>演算子 IUnknown** 演算子

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>解説

現在の[ptr_](#ptr)データ メンバーを`IUnknown`、ポインターからインターフェイスへのポインターにキャストします。

現在`ComPtrRefBase`が`IUnknown`から派生していない場合は、エラーが発生します。

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a>ベース::ptr_

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
T* ptr_;
```

### <a name="remarks"></a>解説

現在のテンプレート パラメーターで指定された型へのポインター。 `ptr_`は保護されたデータ メンバーです。
