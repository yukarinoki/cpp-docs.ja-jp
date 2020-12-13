---
description: '詳細情報: CHeapPtrBase クラス'
title: CHeapPtrBase クラス
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: 6186f68066f4c159c16c458f9f00725478aa98a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141636"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase クラス

このクラスは、いくつかのスマートヒープポインタークラスの基礎を形成します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ヒープに格納されるオブジェクトの種類。

*アロケーター*<br/>
使用するメモリ割り当てクラス。 既定では、CRT ルーチンはメモリの割り当てと解放に使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHeapPtrBase:: AllocateBytes](#allocatebytes)|メモリを割り当てるには、このメソッドを呼び出します。|
|[CHeapPtrBase:: Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|
|[CHeapPtrBase::D etach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|
|[CHeapPtrBase:: Free](#free)|によってポイントされるオブジェクトを削除するには、このメソッドを呼び出し `CHeapPtrBase` ます。|
|[CHeapPtrBase:: ReallocateBytes](#reallocatebytes)|メモリを再割り当てするには、このメソッドを呼び出します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CHeapPtrBase:: operator T *](#operator_t_star)|キャスト演算子。|
|[CHeapPtrBase:: operator &](#operator_amp)|&amp; 演算子。|
|[CHeapPtrBase:: operator->](#operator_ptr)|メンバーへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CHeapPtrBase:: m_pData](#m_pdata)|ポインターデータメンバー変数。|

## <a name="remarks"></a>解説

このクラスは、いくつかのスマートヒープポインタークラスの基礎を形成します。 [CHeapPtr](../../atl/reference/cheapptr-class.md)や[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)などの派生クラスには、独自のコンストラクターと演算子が追加されています。 実装の例については、これらのクラスを参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a> CHeapPtrBase:: AllocateBytes

メモリを割り当てるには、このメソッドを呼び出します。

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
割り当てるメモリのバイト数。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられている場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、 [CHeapPtrBase:: m_pData](#m_pdata) メンバー変数が現在既存の値を指している場合、アサーションエラーが発生します。つまり、NULL とは等しくありません。

## <a name="cheapptrbaseattach"></a><a name="attach"></a> CHeapPtrBase:: Attach

既存のポインターの所有権を取得するには、このメソッドを呼び出します。

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
オブジェクトは、 `CHeapPtrBase` このポインターの所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトが `CHeapPtrBase` ポインターの所有権を取得すると、ポインターと割り当てられたデータがスコープ外になると自動的に削除されます。

デバッグビルドでは、 [CHeapPtrBase:: m_pData](#m_pdata) メンバー変数が現在既存の値を指している場合、アサーションエラーが発生します。つまり、NULL とは等しくありません。

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a> CHeapPtrBase:: ~ CHeapPtrBase

デストラクターです。

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="cheapptrbasedetach"></a><a name="detach"></a> CHeapPtrBase::D etach

ポインターの所有権を解放するには、このメソッドを呼び出します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し、 [CHeapPtrBase:: m_pData](#m_pdata) メンバー変数を NULL に設定して、ポインターのコピーを返します。

## <a name="cheapptrbasefree"></a><a name="free"></a> CHeapPtrBase:: Free

によってポイントされるオブジェクトを削除するには、このメソッドを呼び出し `CHeapPtrBase` ます。

```cpp
void Free() throw();
```

### <a name="remarks"></a>解説

が指すオブジェクト `CHeapPtrBase` が解放され、 [CHeapPtrBase:: m_pData](#m_pdata) メンバー変数が NULL に設定されます。

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a> CHeapPtrBase:: m_pData

ポインターデータメンバー変数。

```
T* m_pData;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a> CHeapPtrBase:: operator &amp;

&amp; 演算子。

```
T** operator&() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが指すオブジェクトのアドレスを返し `CHeapPtrBase` ます。

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a> CHeapPtrBase:: operator-&gt;

メンバーへのポインター演算子。

```
T* operator->() const throw();
```

### <a name="return-value"></a>戻り値

[CHeapPtrBase:: m_pData](#m_pdata)メンバー変数の値を返します。

### <a name="remarks"></a>解説

この演算子を使用すると、オブジェクトが指すクラスのメソッドを呼び出すことが `CHeapPtrBase` できます。 デバッグビルドでは、が NULL を指している場合、アサーションエラーが発生 `CHeapPtrBase` します。

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a> CHeapPtrBase:: operator T *

キャスト演算子。

```
operator T*() const throw();
```

### <a name="remarks"></a>解説

[CHeapPtrBase:: m_pData](#m_pdata)を返します。

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a> CHeapPtrBase:: ReallocateBytes

メモリを再割り当てするには、このメソッドを呼び出します。

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
割り当てるメモリの新しい容量 (バイト単位)。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられている場合は true、それ以外の場合は false を返します。

## <a name="see-also"></a>関連項目

[CHeapPtr クラス](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
