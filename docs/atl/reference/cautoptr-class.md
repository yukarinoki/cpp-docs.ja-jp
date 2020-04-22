---
title: C オートプター クラス
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
ms.openlocfilehash: 2fa6eb26c2e2cd569d74c02d8303768b1aeb4f1c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748275"
---
# <a name="cautoptr-class"></a>C オートプター クラス

このクラスは、スマート ポインター オブジェクトを表します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename T>
class CAutoPtr
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cオートプター::Cオートプター](#cautoptr)|コンストラクターです。|
|[Cオートプター::~Cオートプター](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cオートプター::アタッチ](#attach)|既存のポインターの所有権を取得します。|
|[Cオートプター::Dエタッハ](#detach)|ポインターの所有権を解放します。|
|[Cオートプター::無料](#free)|によって指されているオブジェクトを削除`CAutoPtr`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cオートプター::演算子T*](#operator_t_star)|キャスト演算子。|
|[CAutoPtr::演算子 =](#operator_eq)|代入演算子。|
|[CAutoPtr::演算子 ->](#operator_ptr)|メンバーへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cオートプター::m_p](#m_p)|ポインター データ メンバー変数。|

## <a name="remarks"></a>解説

このクラスは、スマート ポインターを作成および管理するためのメソッドを提供します。

さらに、`CAutoPtr`コピー コンストラクターと代入演算子は、ポインターの所有権を転送し、ソース ポインターをコピー先ポインターにコピーし、ソース ポインターを NULL に設定します。 したがって、2 つの`CAutoPtr`オブジェクトが同じポインターを格納することは不可能であり、これにより、同じポインターを 2 回削除する可能性が減ります。

`CAutoPtr`また、ポインタのコレクションの作成も簡単になります。 コレクション クラスを派生してデストラクターをオーバーライドする代わりに、オブジェクトの`CAutoPtr`コレクションを作成する方法が簡単です。 コレクションが削除されると、`CAutoPtr`オブジェクトはスコープ外になり、自動的に削除されます。

[CHeapPtr](../../atl/reference/cheapptr-class.md)とバリアントは`CAutoPtr`、 と同じように動作しますが、C++**の新しい**演算子と**削除**演算子ではなく、異なるヒープ関数を使用してメモリを割り当てて解放します。 [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)は`CAutoPtr`、**ベクトル new[] とベクトル delete[] を**使用してメモリを割り当てて解放するという唯一の違いと似ています。 **vector delete[]**

スマート ポインターの配列またはリストが必要な場合は[、CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)および[CAutoPtrList](../../atl/reference/cautoptrlist-class.md)も参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

## <a name="cautoptrattach"></a><a name="attach"></a>Cオートプター::アタッチ

既存のポインターの所有権を取得します。

```cpp
void Attach(T* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
オブジェクト`CAutoPtr`は、このポインターの所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトが`CAutoPtr`ポインターの所有権を取得すると、ポインターと割り当てられたデータがスコープ外に出ると、そのオブジェクトは自動的に削除されます。 [CAutoPtr::Detach](#detach)が呼び出されると、プログラマは割り当てられたリソースを解放する責任を再び与えられます。

デバッグ ビルドでは[、CAutoPtr::m_p](#m_p)データ メンバーが現在既存の値を指している場合、アサーション エラーが発生します。つまり、NULL と等しくありません。

### <a name="example"></a>例

[「CAutoPtr](../../atl/reference/cautoptr-class.md)の概要」の例を参照してください。

## <a name="cautoptrcautoptr"></a><a name="cautoptr"></a>Cオートプター::Cオートプター

コンストラクターです。

```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
既存のポインター。

*TSrc*<br/>
現在のオブジェクトを初期化するために`CAutoPtr`使用される別の で管理されている型。

### <a name="remarks"></a>解説

オブジェクト`CAutoPtr`は既存のポインターを使用して作成でき、その場合はポインターの所有権を転送します。

### <a name="example"></a>例

[「CAutoPtr](../../atl/reference/cautoptr-class.md)の概要」の例を参照してください。

## <a name="cautoptrcautoptr"></a><a name="dtor"></a>Cオートプター::~Cオートプター

デストラクターです。

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。 [を](#free)呼び出します。

## <a name="cautoptrdetach"></a><a name="detach"></a>Cオートプター::Dエタッハ

ポインターの所有権を解放します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し[、CAutoPtr::m_p](#m_p)データ メンバー変数を NULL に設定し、ポインターのコピーを返します。 を呼`Detach`び出した後、オブジェクトが以前に対応を想定していた割り当`CAutoPtr`て済みリソースを解放するのはプログラマの必要です。

### <a name="example"></a>例

[「CAutoPtr](../../atl/reference/cautoptr-class.md)の概要」の例を参照してください。

## <a name="cautoptrfree"></a><a name="free"></a>Cオートプター::無料

によって指されているオブジェクトを削除`CAutoPtr`します。

```cpp
void Free() throw();
```

### <a name="remarks"></a>解説

が指すオブジェクト`CAutoPtr`が解放され[、CAutoPtr::m_p](#m_p)データ メンバー変数が NULL に設定されます。

## <a name="cautoptrm_p"></a><a name="m_p"></a>Cオートプター::m_p

ポインター データ メンバー変数。

```
T* m_p;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr::演算子 =

代入演算子。

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>パラメーター

*P*<br/>
ポインター。

*TSrc*<br/>
クラス型。

### <a name="return-value"></a>戻り値

**CAutoPtr\< T >** への参照を返します。

### <a name="remarks"></a>解説

代入演算子は、現在の`CAutoPtr`ポインターからオブジェクトをデタッチし、新しいポインター *p*をその場所にアタッチします。

### <a name="example"></a>例

[「CAutoPtr](../../atl/reference/cautoptr-class.md)の概要」の例を参照してください。

## <a name="cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr::演算子 -&gt;

メンバーへのポインター演算子。

```
T* operator->() const throw();
```

### <a name="return-value"></a>戻り値

データ メンバー変数[CAutoPtr::m_p](#m_p)の値を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトが指すクラスのメソッドを`CAutoPtr`呼び出すために使います。 デバッグ ビルドでは、NULL を指すとアサーション`CAutoPtr`エラーが発生します。

### <a name="example"></a>例

[「CAutoPtr](../../atl/reference/cautoptr-class.md)の概要」の例を参照してください。

## <a name="cautoptroperator-t"></a><a name="operator_t_star"></a>Cオートプター::演算子T*

キャスト演算子。

```
operator T* () const throw();
```

### <a name="return-value"></a>戻り値

クラス テンプレートで定義されているオブジェクト データ型へのポインターを返します。

### <a name="example"></a>例

[「CAutoPtr](../../atl/reference/cautoptr-class.md)の概要」の例を参照してください。

## <a name="see-also"></a>関連項目

[Cヒーププタークラス](../../atl/reference/cheapptr-class.md)<br/>
[クラス](../../atl/reference/cautovectorptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
