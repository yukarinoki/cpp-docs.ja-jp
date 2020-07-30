---
title: CAutoVectorPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
ms.openlocfilehash: 65d37396b02d2c11c758915b201eef09cf1935b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226647"
---
# <a name="cautovectorptr-class"></a>CAutoVectorPtr クラス

このクラスは、vector new および delete 演算子を使用したスマートポインターオブジェクトを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename T>
class CAutoVectorPtr
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|コンストラクターです。|
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CAutoVectorPtr:: Allocate](#allocate)|が指すオブジェクトの配列に必要なメモリを割り当てるには、このメソッドを呼び出し `CAutoVectorPtr` ます。|
|[CAutoVectorPtr:: Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|
|[CAutoVectorPtr::D etach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|
|[CAutoVectorPtr:: Free](#free)|によってポイントされるオブジェクトを削除するには、このメソッドを呼び出し `CAutoVectorPtr` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|[説明]|
|----------|-----------------|
|[CAutoVectorPtr:: operator T *](#operator_t__star)|キャスト演算子。|
|[CAutoVectorPtr:: operator =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|[説明]|
|----------|-----------------|
|[CAutoVectorPtr:: m_p](#m_p)|ポインターデータメンバー変数。|

## <a name="remarks"></a>解説

このクラスは、スマートポインターを作成および管理するためのメソッドを提供します。これは、リソースがスコープ外になったときに自動的に解放することによって、メモリリークから保護するために役立ちます。 `CAutoVectorPtr`はと似ていますが `CAutoPtr` 、 `CAutoVectorPtr` [vector new&#91;&#93;](../../standard-library/new-operators.md#op_new_arr)と[vector delete&#91;&#93;](../../standard-library/new-operators.md#op_delete_arr)を使用する唯一の違いは、C++ および演算子ではなく、メモリの割り当てと解放を行うことです **`new`** **`delete`** 。 のコレクションクラスが必要な場合は、「 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 」を参照してください `CAutoVectorPtr` 。

スマートポインタークラスの使用例については、「 [CAutoPtr](../../atl/reference/cautoptr-class.md) 」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>CAutoVectorPtr:: Allocate

が指すオブジェクトの配列に必要なメモリを割り当てるには、このメソッドを呼び出し `CAutoVectorPtr` ます。

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>パラメーター

*nElements*<br/>
配列の要素数。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 [CAutoVectorPtr:: m_p](#m_p)メンバー変数が現在既存の値を指している場合、アサーションエラーが発生します。つまり、NULL とは等しくありません。

## <a name="cautovectorptrattach"></a><a name="attach"></a>CAutoVectorPtr:: Attach

既存のポインターの所有権を取得するには、このメソッドを呼び出します。

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
オブジェクトは、 `CAutoVectorPtr` このポインターの所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトが `CAutoVectorPtr` ポインターの所有権を取得すると、ポインターと割り当てられたデータがスコープ外になると自動的に削除されます。 [CAutoVectorPtr::D Etach](#detach)が呼び出された場合、プログラマは、割り当てられたリソースを解放する必要があります。

デバッグビルドでは、 [CAutoVectorPtr:: m_p](#m_p)メンバー変数が現在既存の値を指している場合、アサーションエラーが発生します。つまり、NULL とは等しくありません。

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr

コンストラクターです。

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
既存のポインター。

### <a name="remarks"></a>解説

オブジェクトは、 `CAutoVectorPtr` 既存のポインターを使用して作成できます。この場合、ポインターの所有権が転送されます。

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>CAutoVectorPtr:: ~ CAutoVectorPtr

デストラクターです。

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。 [CAutoVectorPtr:: Free](#free)を呼び出します。

## <a name="cautovectorptrdetach"></a><a name="detach"></a>CAutoVectorPtr::D etach

ポインターの所有権を解放するには、このメソッドを呼び出します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し、 [CAutoVectorPtr:: m_p](#m_p)メンバー変数を NULL に設定して、ポインターのコピーを返します。 を呼び出した後 `Detach` 、 `CAutoVectorPtr` オブジェクトが以前に責任を想定していた可能性のある割り当て済みリソースを解放するのはプログラマの責任です。

## <a name="cautovectorptrfree"></a><a name="free"></a>CAutoVectorPtr:: Free

によってポイントされるオブジェクトを削除するには、このメソッドを呼び出し `CAutoVectorPtr` ます。

```cpp
void Free() throw();
```

### <a name="remarks"></a>解説

が指すオブジェクト `CAutoVectorPtr` が解放され、 [CAutoVectorPtr:: m_p](#m_p)メンバー変数が NULL に設定されます。

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>CAutoVectorPtr:: m_p

ポインターデータメンバー変数。

```
T* m_p;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>CAutoVectorPtr:: operator =

代入演算子。

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
ポインター。

### <a name="return-value"></a>戻り値

**CAutoVectorPtr \< T > **への参照を返します。

### <a name="remarks"></a>解説

代入演算子は、 `CAutoVectorPtr` 現在のポインターからオブジェクトをデタッチし、その代わりに新しいポインター *p*をアタッチします。

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>CAutoVectorPtr:: operator T *

キャスト演算子。

```
operator T*() const throw();
```

### <a name="remarks"></a>解説

クラステンプレートで定義されているオブジェクトデータ型へのポインターを返します。

## <a name="see-also"></a>関連項目

[CAutoPtr クラス](../../atl/reference/cautoptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
