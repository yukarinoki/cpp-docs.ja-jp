---
title: クラス
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
ms.openlocfilehash: 573446256aa89423837ebf73176a73f72054911b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318761"
---
# <a name="cautovectorptr-class"></a>クラス

このクラスは、ベクトル new 演算子と delete 演算子を使用してスマート ポインター オブジェクトを表します。

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

|名前|説明|
|----------|-----------------|
|[C オートベクトルプター::Cオートベクトルプター](#cautovectorptr)|コンストラクターです。|
|[C オートベクトルプター::~Cオートベクトルプター](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[割り当て](#allocate)|によって指されるオブジェクトの配列に必要なメモリを割り当てます`CAutoVectorPtr`。|
|[C オートベクトルプター::アタッチ](#attach)|既存のポインターの所有権を取得します。|
|[Cオートベクトルプター::Dエタッハ](#detach)|ポインターの所有権を解放します。|
|[Cオートベクトルプター::無料](#free)|によって指されているオブジェクトを削除`CAutoVectorPtr`します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[C オートベクトルプター::演算子 T *](#operator_t__star)|キャスト演算子。|
|[=演算子=](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[を指定します m_p。](#m_p)|ポインター データ メンバー変数。|

## <a name="remarks"></a>解説

このクラスは、スマート ポインターを作成および管理するためのメソッドを提供します。 `CAutoVectorPtr``CAutoPtr`は 、C++ の新しい`CAutoVectorPtr`演算子と削除**演算子の**代わりに、[ベクトルの新しい&#91;&#93;](../../standard-library/new-operators.md#op_new_arr)と[ベクトル削除&#91;&#93;](../../standard-library/new-operators.md#op_delete_arr)を**new**使用してメモリを割り当てて解放するという唯一の違いです。 コレクション クラス[が必要な場合は、「CAutoVectorPtr要素トレイト](../../atl/reference/cautovectorptrelementtraits-class.md)」を`CAutoVectorPtr`参照してください。

スマート ポインター クラスの使用例については[、「CAutoPtr」](../../atl/reference/cautoptr-class.md)を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="cautovectorptrallocate"></a><a name="allocate"></a>割り当て

によって指されるオブジェクトの配列に必要なメモリを割り当てます`CAutoVectorPtr`。

```
bool Allocate(size_t nElements) throw();
```

### <a name="parameters"></a>パラメーター

*n要素*<br/>
配列の要素数。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、失敗した場合は false を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは[、CAutoVectorPtr::m_p](#m_p)メンバー変数が現在既存の値を指している場合、アサーション エラーが発生します。つまり、NULL と等しくありません。

## <a name="cautovectorptrattach"></a><a name="attach"></a>C オートベクトルプター::アタッチ

既存のポインターの所有権を取得します。

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
オブジェクト`CAutoVectorPtr`は、このポインターの所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトが`CAutoVectorPtr`ポインターの所有権を取得すると、ポインターと割り当てられたデータがスコープ外に出ると、そのオブジェクトは自動的に削除されます。 [CAutoVectorPtr::Detach](#detach)が呼び出された場合、プログラマは割り当てられたリソースを解放する責任を再び与えられます。

デバッグ ビルドでは[、CAutoVectorPtr::m_p](#m_p)メンバー変数が現在既存の値を指している場合、アサーション エラーが発生します。つまり、NULL と等しくありません。

## <a name="cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>C オートベクトルプター::Cオートベクトルプター

コンストラクターです。

```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
既存のポインター。

### <a name="remarks"></a>解説

オブジェクト`CAutoVectorPtr`は既存のポインターを使用して作成でき、その場合はポインターの所有権を転送します。

## <a name="cautovectorptrcautovectorptr"></a><a name="dtor"></a>C オートベクトルプター::~Cオートベクトルプター

デストラクターです。

```
~CAutoVectorPtr() throw();
```

### <a name="remarks"></a>解説

割り当てられたリソースを解放します。 [を](#free)呼び出します。

## <a name="cautovectorptrdetach"></a><a name="detach"></a>Cオートベクトルプター::Dエタッハ

ポインターの所有権を解放します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し[、CAutoVectorPtr::m_p](#m_p)メンバー変数を NULL に設定し、ポインターのコピーを返します。 を呼`Detach`び出した後、オブジェクトが以前に責任を負った可能性のある割`CAutoVectorPtr`り当てられたリソースを解放するのはプログラマの責任です。

## <a name="cautovectorptrfree"></a><a name="free"></a>Cオートベクトルプター::無料

によって指されているオブジェクトを削除`CAutoVectorPtr`します。

```
void Free() throw();
```

### <a name="remarks"></a>解説

が指すオブジェクト`CAutoVectorPtr`が解放され、メンバー変数[CAutoVectorPtr::m_p](#m_p)が NULL に設定されます。

## <a name="cautovectorptrm_p"></a><a name="m_p"></a>を指定します m_p。

ポインター データ メンバー変数。

```
T* m_p;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="cautovectorptroperator-"></a><a name="operator_eq"></a>=演算子=

代入演算子。

```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
ポインター。

### <a name="return-value"></a>戻り値

**\< CAutoVectorPtr T >** への参照を返します。

### <a name="remarks"></a>解説

代入演算子は、現在の`CAutoVectorPtr`ポインターからオブジェクトをデタッチし、新しいポインター *p*をその場所にアタッチします。

## <a name="cautovectorptroperator-t-"></a><a name="operator_t__star"></a>C オートベクトルプター::演算子 T *

キャスト演算子。

```
operator T*() const throw();
```

### <a name="remarks"></a>解説

クラス テンプレートで定義されているオブジェクト データ型へのポインターを返します。

## <a name="see-also"></a>関連項目

[C オートプター クラス](../../atl/reference/cautoptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
