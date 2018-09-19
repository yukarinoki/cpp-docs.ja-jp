---
title: CComDynamicUnkArray クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e776fd88799999ce175ba2efc137fc0353cbe65a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068469"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray クラス

このクラスの配列を格納する`IUnknown`ポインター。

## <a name="syntax"></a>構文

```
class CComDynamicUnkArray
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|コンストラクターです。 コレクション値を NULL とコレクションのサイズを 0 に初期化します。|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComDynamicUnkArray::Add](#add)|追加するには、このメソッドを呼び出す、`IUnknown`配列へのポインター。|
|[CComDynamicUnkArray::begin](#begin)|最初のポインターを返します`IUnknown`コレクション内のポインター。|
|[CComDynamicUnkArray::clear](#clear)|配列が空にします。|
|[CComDynamicUnkArray::end](#end)|最後にポインターを返します`IUnknown`コレクション内のポインター。|
|[CComDynamicUnkArray::GetAt](#getat)|指定したインデックス位置にある要素を取得します。|
|[CComDynamicUnkArray::GetCookie](#getcookie)|関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された`IUnknown`ポインター。|
|[CComDynamicUnkArray::GetSize](#getsize)|配列の長さを返します。|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|取得するには、このメソッドを呼び出す、`IUnknown`ポインターに関連付けられたクッキーを指定します。|
|[CComDynamicUnkArray::Remove](#remove)|削除するには、このメソッドを呼び出す、`IUnknown`配列からポインター。|

## <a name="remarks"></a>Remarks

`CComDynamicUnkArray` 動的に割り当てられた配列を保持`IUnknown`ポインター、接続のインターフェイスの各ポイントします。 `CComDynamicUnkArray` パラメーターとして使用できる、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラス。

`CComDynamicUnkArray`メソッド[開始](#begin)と[エンド](#end)(たとえば、イベントが発生したときに) すべてのコネクション ポイントをループするために使用できます。

参照してください[オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md)詳細については接続の作成を自動化することでプロキシをポイントします。

> [!NOTE]
> **注**クラス`CComDynamicUnkArray`によって使用されます、**クラスの追加**接続ポイントを持つコントロールを作成するときにウィザード。 接続ポイントの数を手動で指定する場合は、変更からの参照を`CComDynamicUnkArray`に`CComUnkArray<` *n* `>`ここで、 *n*コネクション ポイントの数です必須。

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="add"></a>  CComDynamicUnkArray::Add

追加するには、このメソッドを呼び出す、`IUnknown`配列へのポインター。

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*pUnk*<br/>
`IUnknown`ポインター、配列に追加します。

### <a name="return-value"></a>戻り値

新しく追加されたポインターに関連付けられているクッキーを返します。

##  <a name="begin"></a>  CComDynamicUnkArray::begin

コレクションの先頭にポインターを返します`IUnknown`インターフェイス ポインター。

```
IUnknown**
    begin();
```

### <a name="return-value"></a>戻り値

ポインター、`IUnknown`インターフェイス ポインター。

### <a name="remarks"></a>Remarks

コレクションにはとしてローカルに格納されているインターフェイスへのポインターが含まれています`IUnknown`します。 それぞれをキャストする`IUnknown`インターフェイスを実際のインターフェイス型としています。 まず、インターフェイスに対してクエリを実行する必要はありません。

使用する前に、`IUnknown`インターフェイス、NULL がないこと確認する必要があります。

##  <a name="clear"></a>  CComDynamicUnkArray::clear

配列が空にします。

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>  CComDynamicUnkArray::CComDynamicUnkArray

コンストラクターです。

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Remarks

コレクションのサイズを 0 に設定し、null 値を初期化します。 デストラクターは、必要に応じて、コレクションを解放します。

##  <a name="dtor"></a>  CComDynamicUnkArray:: ~ CComDynamicUnkArray

デストラクターです。

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Remarks

クラスのコンス トラクターによって割り当てられたリソースを解放します。

##  <a name="end"></a>  CComDynamicUnkArray::end

最後にポインターを返します`IUnknown`コレクション内のポインター。

```
IUnknown**
    end();
```

### <a name="return-value"></a>戻り値

ポインター、`IUnknown`インターフェイス ポインター。

##  <a name="getat"></a>  CComDynamicUnkArray::GetAt

指定したインデックス位置にある要素を取得します。

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する要素のインデックス。

### <a name="return-value"></a>戻り値

ポインター、 [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)インターフェイス。

##  <a name="getcookie"></a>  CComDynamicUnkArray::GetCookie

関連付けられているクッキーを取得するには、このメソッドを呼び出して、指定された`IUnknown`ポインター。

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>パラメーター

*ppFind*<br/>
`IUnknown`ポインターに関連付けられている cookie が必要です。

### <a name="return-value"></a>戻り値

関連付けられているクッキーを返します、`IUnknown`ポインター、または一致する場合は 0`IUnknown`ポインターが見つかりました。

### <a name="remarks"></a>Remarks

同じ 1 つ以上のインスタンスがある場合`IUnknown`ポインター、この関数は、1 つ目の cookie を返します。

##  <a name="getsize"></a>  CComDynamicUnkArray::GetSize

配列の長さを返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

配列の長さ。

##  <a name="getunknown"></a>  CComDynamicUnkArray::GetUnknown

取得するには、このメソッドを呼び出す、`IUnknown`ポインターに関連付けられたクッキーを指定します。

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*dwCookie*<br/>
Cookie を関連付けられている`IUnknown`ポインターが必要です。

### <a name="return-value"></a>戻り値

返します、`IUnknown`ポインター、または一致する cookie が検出されない場合は NULL です。

##  <a name="remove"></a>  CComDynamicUnkArray::Remove

削除するには、このメソッドを呼び出す、`IUnknown`配列からポインター。

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*dwCookie*<br/>
Cookie を参照すること、`IUnknown`ポインター、配列から削除します。

### <a name="return-value"></a>戻り値

ポインターが削除されたかどうかは TRUE を返しますそれ以外の場合は FALSE です。

## <a name="see-also"></a>関連項目

[CComUnkArray クラス](../../atl/reference/ccomunkarray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
