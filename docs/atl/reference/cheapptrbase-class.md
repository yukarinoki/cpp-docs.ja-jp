---
title: クラス
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
ms.openlocfilehash: e247b4f488411ffdcde5d1d9016436c9c36fe793
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747684"
---
# <a name="cheapptrbase-class"></a>クラス

このクラスは、いくつかのスマート ヒープ ポインター クラスの基礎を形成します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ヒープに格納されるオブジェクト型。

*アロケーター*<br/>
使用するメモリ割り当てクラス。 デフォルトでは、CRT ルーチンは、メモリの割り当てと解放に使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ヒーププターベース::~Cヒーププターベース](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[バイト数の割り当て](#allocatebytes)|メモリを割り当てるには、このメソッドを呼び出します。|
|[Cヒーププターベース::アタッチ](#attach)|既存のポインターの所有権を取得します。|
|[クヒーププターベース::Dエタッハ](#detach)|ポインターの所有権を解放します。|
|[ヒーププターベース::無料](#free)|によって指されているオブジェクトを削除`CHeapPtrBase`します。|
|[バイトの再割り当て](#reallocatebytes)|メモリを再割り当てします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cヒーププターベース::演算子 T*](#operator_t_star)|キャスト演算子。|
|[cヒーププターベース::演算子&](#operator_amp)|&amp; 演算子。|
|[クヒーププターベース::演算子 ->](#operator_ptr)|メンバーへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ヒーププターベース::m_pData](#m_pdata)|ポインター データ メンバー変数。|

## <a name="remarks"></a>解説

このクラスは、いくつかのスマート ヒープ ポインター クラスの基礎を形成します。 派生クラスは、[たとえば CHeapPtr や CComHeapPtr](../../atl/reference/cheapptr-class.md)に独自のコンストラクターと演算子を追加します。 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) 実装例については、これらのクラスを参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a>バイト数の割り当て

メモリを割り当てるには、このメソッドを呼び出します。

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
割り当てるメモリのバイト数。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは[、CHeapPtrBase::m_pData](#m_pdata)メンバー変数が現在既存の値を指している場合、アサーション エラーが発生します。つまり、NULL と等しくありません。

## <a name="cheapptrbaseattach"></a><a name="attach"></a>Cヒーププターベース::アタッチ

既存のポインターの所有権を取得します。

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>パラメーター

*Pdata*<br/>
オブジェクト`CHeapPtrBase`は、このポインターの所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトが`CHeapPtrBase`ポインターの所有権を取得すると、ポインターと割り当てられたデータがスコープ外に出ると、そのオブジェクトは自動的に削除されます。

デバッグ ビルドでは[、CHeapPtrBase::m_pData](#m_pdata)メンバー変数が現在既存の値を指している場合、アサーション エラーが発生します。つまり、NULL と等しくありません。

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a>ヒーププターベース::~Cヒーププターベース

デストラクターです。

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="cheapptrbasedetach"></a><a name="detach"></a>クヒーププターベース::Dエタッハ

ポインターの所有権を解放します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し[、CHeapPtrBase::m_pData](#m_pdata)メンバー変数を NULL に設定し、ポインターのコピーを返します。

## <a name="cheapptrbasefree"></a><a name="free"></a>ヒーププターベース::無料

によって指されているオブジェクトを削除`CHeapPtrBase`します。

```cpp
void Free() throw();
```

### <a name="remarks"></a>解説

が指すオブジェクト`CHeapPtrBase`が解放され[、CHeapPtrBase::m_pData](#m_pdata)メンバー変数が NULL に設定されます。

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a>ヒーププターベース::m_pData

ポインター データ メンバー変数。

```
T* m_pData;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a>Cヒーププターベース::演算子&amp;

&amp; 演算子。

```
T** operator&() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが指すオブジェクトのアドレスを`CHeapPtrBase`返します。

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a>Cヒーププターベース::演算子 -&gt;

メンバーへのポインター演算子。

```
T* operator->() const throw();
```

### <a name="return-value"></a>戻り値

メンバー変数の値[m_pDataを](#m_pdata)返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトが指すクラスのメソッドを`CHeapPtrBase`呼び出すために使います。 デバッグ ビルドでは、NULL を指すとアサーション`CHeapPtrBase`エラーが発生します。

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a>Cヒーププターベース::演算子 T*

キャスト演算子。

```
operator T*() const throw();
```

### <a name="remarks"></a>解説

を返します[m_pData。](#m_pdata)

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a>バイトの再割り当て

メモリを再割り当てします。

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
割り当てるメモリの新しい量 (バイト単位)。

### <a name="return-value"></a>戻り値

メモリが正常に割り当てられた場合は true、それ以外の場合は false を返します。

## <a name="see-also"></a>関連項目

[Cヒーププタークラス](../../atl/reference/cheapptr-class.md)<br/>
[クラス](../../atl/reference/ccomheapptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
