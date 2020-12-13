---
description: '詳細情報: CHandle クラス'
title: CHandle クラス
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
ms.openlocfilehash: 01c3b281daf829bc6488df35114c6cb853640ed1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141675"
---
# <a name="chandle-class"></a>CHandle クラス

このクラスには、handle オブジェクトを作成および使用するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CHandle
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|コンストラクターです。|
|[CHandle:: ~ CHandle](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHandle:: Attach](#attach)|オブジェクトを既存のハンドルにアタッチするには、このメソッドを呼び出し `CHandle` ます。|
|[CHandle:: Close](#close)|オブジェクトを閉じるには、このメソッドを呼び出し `CHandle` ます。|
|[CHandle::D etach](#detach)|オブジェクトからハンドルをデタッチするには、このメソッドを呼び出し `CHandle` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CHandle:: operator ハンドル](#operator_handle)|格納されているハンドルの値を返します。|
|[CHandle:: operator =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CHandle:: m_h](#m_h)|ハンドルを格納するメンバー変数。|

## <a name="remarks"></a>解説

オブジェクトは、 `CHandle` ハンドルが必要なときに常に使用できます。主な違いは、オブジェクトが自動的に削除されることです `CHandle` 。

> [!NOTE]
> 一部の API 関数では、空または無効なハンドルとして NULL が使用され、他の関数は INVALID_HANDLE_VALUE を使用します。 `CHandle` は NULL のみを使用し、INVALID_HANDLE_VALUE を実際のハンドルとして扱います。 INVALID_HANDLE_VALUE を返すことができる API を呼び出す場合は、 [CHandle:: Attach](#attach) を呼び出す前にこの値を確認するか、コンストラクターに渡し `CHandle` 、代わりに NULL を渡す必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="chandleattach"></a><a name="attach"></a> CHandle:: Attach

オブジェクトを既存のハンドルにアタッチするには、このメソッドを呼び出し `CHandle` ます。

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>パラメーター

*h*<br/>
`CHandle` は *、ハンドルの* 所有権を取得します。

### <a name="remarks"></a>解説

オブジェクトを `CHandle` *h* ハンドルに割り当て、その後、 **.h ()** を呼び出します。 デバッグビルドでは、 *h* が NULL の場合に ATLASSERT が発生します。 ハンドルが有効であるかどうかの確認は行われません。

## <a name="chandlechandle"></a><a name="chandle"></a> CHandle::CHandle

コンストラクターです。

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>パラメーター

*h*<br/>
既存のハンドルまたは `CHandle` 。

### <a name="remarks"></a>解説

新しいオブジェクトを作成し `CHandle` ます。必要に応じて、既存のハンドルまたはオブジェクトを使用し `CHandle` ます。

## <a name="chandlechandle"></a><a name="dtor"></a> CHandle:: ~ CHandle

デストラクターです。

```
~CHandle() throw();
```

### <a name="remarks"></a>解説

`CHandle` [CHandle:: Close](#close)を呼び出して、オブジェクトを解放します。

## <a name="chandleclose"></a><a name="close"></a> CHandle:: Close

オブジェクトを閉じるには、このメソッドを呼び出し `CHandle` ます。

```cpp
void Close() throw();
```

### <a name="remarks"></a>解説

開いているオブジェクトハンドルを閉じます。 ハンドルが NULL の場合、 `Close` が既に呼び出されている場合は、デバッグビルドで ATLASSERT が発生します。

## <a name="chandledetach"></a><a name="detach"></a> CHandle::D etach

オブジェクトからハンドルをデタッチするには、このメソッドを呼び出し `CHandle` ます。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>戻り値

デタッチされているハンドルを返します。

### <a name="remarks"></a>解説

ハンドルの所有権を解放します。

## <a name="chandlem_h"></a><a name="m_h"></a> CHandle:: m_h

ハンドルを格納するメンバー変数。

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a> CHandle:: operator =

代入演算子。

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>パラメーター

*h*<br/>
`CHandle` は *、ハンドルの* 所有権を取得します。

### <a name="return-value"></a>戻り値

新しいオブジェクトへの参照を返し `CHandle` ます。

### <a name="remarks"></a>解説

オブジェクトに `CHandle` 現在ハンドルが含まれている場合は、閉じられます。 `CHandle`渡されたオブジェクトのハンドル参照が NULL に設定されます。 これにより、2つの `CHandle` オブジェクトが同じアクティブハンドルを含むことがなくなります。

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a> CHandle:: operator ハンドル

格納されているハンドルの値を返します。

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>解説

[CHandle:: m_h](#m_h)に格納されている値を返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
