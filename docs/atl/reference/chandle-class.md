---
title: クラスを処理します。
ms.date: 07/09/2019
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
ms.openlocfilehash: 4b883bdf3159c40f8d74866f04f655ae73d82a8a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747699"
---
# <a name="chandle-class"></a>クラスを処理します。

このクラスには、ハンドル オブジェクトを作成および使用するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CHandle
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ハンドル::Cハンドル](#chandle)|コンストラクターです。|
|[ハンドル::~Cハンドル](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ハンドル::アタッチ](#attach)|オブジェクトを既存のハンドルに`CHandle`アタッチします。|
|[ハンドル::閉じる](#close)|`CHandle`オブジェクトを閉じます。|
|[ハンドル::Dエタッハ](#detach)|`CHandle`オブジェクトからハンドルをデタッチします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ハンドル::演算子ハンドル](#operator_handle)|格納されているハンドルの値を返します。|
|[ハンドル::演算子 =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ハンドル::m_h](#m_h)|ハンドルを格納するメンバー変数。|

## <a name="remarks"></a>解説

ハンドル`CHandle`が必要な場合はいつでもオブジェクトを`CHandle`使用できます。

> [!NOTE]
> 一部の API 関数では空または無効なハンドルとして NULL を使用し、他の API 関数はINVALID_HANDLE_VALUEを使用します。 `CHandle`NULL のみを使用し、INVALID_HANDLE_VALUEを実際のハンドルとして扱います。 INVALID_HANDLE_VALUE返すことができる API を呼び出す場合は[、CHandle::Attach](#attach)を呼び出すか`CHandle`、コンストラクターに渡す前にこの値をチェックし、代わりに NULL を渡す必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="chandleattach"></a><a name="attach"></a>ハンドル::アタッチ

オブジェクトを既存のハンドルに`CHandle`アタッチします。

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`CHandle`ハンドル*h*の所有権を取得します。

### <a name="remarks"></a>解説

h ハンドル`CHandle`にオブジェクトを*h*割り当て **、h.Detach() を**呼び出します。 デバッグ ビルドでは *、h*が NULL の場合に ATLASSERT が発生します。 ハンドルの有効性に関する他のチェックは行いません。

## <a name="chandlechandle"></a><a name="chandle"></a>ハンドル::Cハンドル

コンストラクターです。

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>パラメーター

*H*<br/>
既存のハンドルまたは`CHandle`.

### <a name="remarks"></a>解説

既存のハンドル`CHandle`または`CHandle`オブジェクトを使用して、必要に応じて新しいオブジェクトを作成します。

## <a name="chandlechandle"></a><a name="dtor"></a>ハンドル::~Cハンドル

デストラクターです。

```
~CHandle() throw();
```

### <a name="remarks"></a>解説

`CHandle` [CHandle::Close](#close)を呼び出してオブジェクトを解放します。

## <a name="chandleclose"></a><a name="close"></a>ハンドル::閉じる

`CHandle`オブジェクトを閉じます。

```cpp
void Close() throw();
```

### <a name="remarks"></a>解説

開いているオブジェクト ハンドルを閉じます。 ハンドルが NULL の場合は、既に呼`Close`び出されている場合、デバッグ ビルドで ATLASSERT が発生します。

## <a name="chandledetach"></a><a name="detach"></a>ハンドル::Dエタッハ

`CHandle`オブジェクトからハンドルをデタッチします。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>戻り値

デタッチされているハンドルを返します。

### <a name="remarks"></a>解説

ハンドルの所有権を解放します。

## <a name="chandlem_h"></a><a name="m_h"></a>ハンドル::m_h

ハンドルを格納するメンバー変数。

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a>ハンドル::演算子 =

代入演算子。

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>パラメーター

*H*<br/>
`CHandle`ハンドル*h*の所有権を取得します。

### <a name="return-value"></a>戻り値

新しい`CHandle`オブジェクトへの参照を返します。

### <a name="remarks"></a>解説

オブジェクトに`CHandle`現在ハンドルが含まれている場合、そのハンドルは閉じられます。 渡`CHandle`されるオブジェクトのハンドル参照は NULL に設定されます。 これにより、2`CHandle`つのオブジェクトが同じアクティブ ハンドルを含めなくなります。

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a>ハンドル::演算子ハンドル

格納されているハンドルの値を返します。

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>解説

に格納されている値[m_hを返](#m_h)します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
