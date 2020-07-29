---
title: CAutoPtr クラス
ms.date: 11/04/2016
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
ms.openlocfilehash: 699e62362bc74009e3faed3b4fd66b579c9c4cd3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226660"
---
# <a name="cautoptr-class"></a>CAutoPtr クラス

このクラスは、スマートポインターオブジェクトを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template <typename T>
class CAutoPtr
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[CAutoPtr:: CAutoPtr](#cautoptr)|コンストラクターです。|
|[CAutoPtr:: ~ CAutoPtr](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[CAutoPtr:: Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|
|[CAutoPtr::D etach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|
|[CAutoPtr:: Free](#free)|によってポイントされるオブジェクトを削除するには、このメソッドを呼び出し `CAutoPtr` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|[説明]|
|----------|-----------------|
|[CAutoPtr:: operator T *](#operator_t_star)|キャスト演算子。|
|[CAutoPtr:: operator =](#operator_eq)|代入演算子。|
|[CAutoPtr:: operator->](#operator_ptr)|メンバーへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|[説明]|
|----------|-----------------|
|[CAutoPtr:: m_p](#m_p)|ポインターデータメンバー変数。|

## <a name="remarks"></a>解説

このクラスは、スマートポインターを作成および管理するためのメソッドを提供します。これは、リソースがスコープ外になったときに自動的に解放することによって、メモリリークから保護するために役立ちます。

さらに、 `CAutoPtr` のコピーコンストラクターと代入演算子は、ポインターの所有権を転送し、コピー元ポインターをコピー先ポインターにコピーして、ソースポインターを NULL に設定します。 したがって、2つのオブジェクトが同じポインターを格納することはでき `CAutoPtr` ません。これにより、同じポインターを2回削除する可能性が少なくなります。

`CAutoPtr`では、ポインターのコレクションの作成も簡略化されています。 コレクションクラスを派生させ、デストラクターをオーバーライドするのではなく、オブジェクトのコレクションを作成する方が簡単です `CAutoPtr` 。 コレクションが削除されると、 `CAutoPtr` オブジェクトはスコープ外に移り、自動的に削除されます。

[CHeapPtr](../../atl/reference/cheapptr-class.md)と variant はと同じように動作し `CAutoPtr` ますが、C++ や演算子ではなく、異なるヒープ関数を使用してメモリを割り当てて解放する点が異なり **`new`** **`delete`** ます。 [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)はに似てい `CAutoPtr` ます。唯一の違いは、 **vector new []** と**vector delete []** を使用してメモリを割り当て、解放する点です。

配列またはスマートポインターの一覧が必要な場合は、「 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) and [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 」も参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

## <a name="cautoptrattach"></a><a name="attach"></a>CAutoPtr:: Attach

既存のポインターの所有権を取得するには、このメソッドを呼び出します。

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
オブジェクトは、 `CAutoPtr` このポインターの所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトが `CAutoPtr` ポインターの所有権を取得すると、ポインターと割り当てられたデータがスコープ外になると自動的に削除されます。 [CAutoPtr::D etach](#detach)が呼び出された場合、プログラマは、割り当てられたリソースを解放する必要があります。

デバッグビルドでは、現在、 [CAutoPtr:: m_p](#m_p)データメンバーが既存の値を指している場合、アサーションエラーが発生します。つまり、NULL とは等しくありません。

### <a name="example"></a>例

「 [CAutoPtr の概要](../../atl/reference/cautoptr-class.md)」の例を参照してください。

## <a name="cautoptrcautoptr"></a><a name="cautoptr"></a>CAutoPtr:: CAutoPtr

コンストラクターです。

```cpp
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
既存のポインター。

*TSrc*<br/>
`CAutoPtr`現在のオブジェクトを初期化するために使用される、別ので管理されている型。

### <a name="remarks"></a>解説

オブジェクトは、 `CAutoPtr` 既存のポインターを使用して作成できます。この場合、ポインターの所有権が転送されます。

### <a name="example"></a>例

「 [CAutoPtr の概要](../../atl/reference/cautoptr-class.md)」の例を参照してください。

## <a name="cautoptrcautoptr"></a><a name="dtor"></a>CAutoPtr:: ~ CAutoPtr

デストラクターです。

```cpp
~CAutoPtr() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。 [は、CAutoPtr:: Free](#free)を呼び出します。

## <a name="cautoptrdetach"></a><a name="detach"></a>CAutoPtr::D etach

ポインターの所有権を解放するには、このメソッドを呼び出します。

```cpp
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し、 [CAutoPtr:: m_p](#m_p)データメンバー変数を NULL に設定して、ポインターのコピーを返します。 を呼び出した後 `Detach` 、 `CAutoPtr` オブジェクトが以前に reponsibility を想定していたと考えられる、割り当て済みのリソースを解放するのはプログラマです。

### <a name="example"></a>例

「 [CAutoPtr の概要](../../atl/reference/cautoptr-class.md)」の例を参照してください。

## <a name="cautoptrfree"></a><a name="free"></a>CAutoPtr:: Free

によってポイントされるオブジェクトを削除するには、このメソッドを呼び出し `CAutoPtr` ます。

```cpp
void Free() throw();
```

### <a name="remarks"></a>解説

が指すオブジェクト `CAutoPtr` が解放され、 [CAutoPtr:: m_p](#m_p)データメンバー変数が NULL に設定されます。

## <a name="cautoptrm_p"></a><a name="m_p"></a>CAutoPtr:: m_p

ポインターデータメンバー変数。

```cpp
T* m_p;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr:: operator =

代入演算子。

```cpp
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
ポインター。

*TSrc*<br/>
クラス型。

### <a name="return-value"></a>戻り値

**CAutoPtr \< T > **への参照を返します。

### <a name="remarks"></a>解説

代入演算子は、 `CAutoPtr` 現在のポインターからオブジェクトをデタッチし、その代わりに新しいポインター *p*をアタッチします。

### <a name="example"></a>例

「 [CAutoPtr の概要](../../atl/reference/cautoptr-class.md)」の例を参照してください。

## <a name="cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr:: operator-&gt;

メンバーへのポインター演算子。

```cpp
T* operator->() const throw();
```

### <a name="return-value"></a>戻り値

は、 [CAutoPtr:: m_p](#m_p)データメンバー変数の値を返します。

### <a name="remarks"></a>解説

この演算子を使用すると、オブジェクトが指すクラスのメソッドを呼び出すことが `CAutoPtr` できます。 デバッグビルドでは、が NULL を指している場合、アサーションエラーが発生 `CAutoPtr` します。

### <a name="example"></a>例

「 [CAutoPtr の概要](../../atl/reference/cautoptr-class.md)」の例を参照してください。

## <a name="cautoptroperator-t"></a><a name="operator_t_star"></a>CAutoPtr:: operator T *

キャスト演算子。

```cpp
operator T* () const throw();
```

### <a name="return-value"></a>戻り値

クラステンプレートで定義されているオブジェクトデータ型へのポインターを返します。

### <a name="example"></a>例

「 [CAutoPtr の概要](../../atl/reference/cautoptr-class.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[CHeapPtr クラス](../../atl/reference/cheapptr-class.md)<br/>
[CAutoVectorPtr クラス](../../atl/reference/cautovectorptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
