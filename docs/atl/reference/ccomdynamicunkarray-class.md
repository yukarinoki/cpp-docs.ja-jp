---
description: '詳細情報: CComDynamicUnkArray クラス'
title: CComDynamicUnkArray クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: fe817b097bbb75c7d09bffdb6883e5ac4a76f966
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152088"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray クラス

このクラスは、ポインターの配列を格納 `IUnknown` します。

## <a name="syntax"></a>構文

```
class CComDynamicUnkArray
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|コンストラクターです。 コレクションの値を NULL に、コレクションのサイズを0に初期化します。|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComDynamicUnkArray:: Add](#add)|配列へのポインターを追加するには、このメソッドを呼び出し `IUnknown` ます。|
|[CComDynamicUnkArray:: begin](#begin)|コレクション内の最初のポインターへのポインターを返し `IUnknown` ます。|
|[CComDynamicUnkArray:: clear](#clear)|配列を空にします。|
|[CComDynamicUnkArray:: end](#end)|コレクション内の最後のポインターの1つ後ろへのポインターを返し `IUnknown` ます。|
|[CComDynamicUnkArray:: GetAt](#getat)|指定したインデックスにある要素を取得します。|
|[CComDynamicUnkArray:: GetCookie](#getcookie)|指定したポインターに関連付けられているクッキーを取得するには、このメソッドを呼び出し `IUnknown` ます。|
|[CComDynamicUnkArray:: GetSize](#getsize)|配列の長さを返します。|
|[CComDynamicUnkArray:: GetUnknown](#getunknown)|`IUnknown`特定のクッキーに関連付けられているポインターを取得するには、このメソッドを呼び出します。|
|[CComDynamicUnkArray:: Remove](#remove)|配列からポインターを削除するには、このメソッドを呼び出し `IUnknown` ます。|

## <a name="remarks"></a>解説

`CComDynamicUnkArray` 接続ポイントのインターフェイスを動的に割り当てられたポインターの配列を保持 `IUnknown` します。 `CComDynamicUnkArray` は、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) テンプレートクラスのパラメーターとして使用できます。

`CComDynamicUnkArray` [Begin](#begin)および[end](#end)メソッドを使用して、すべてのコネクションポイントをループ処理できます (たとえば、イベントが発生したとき)。

接続ポイントプロキシの作成を自動化する方法の詳細については [、「オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md) 」を参照してください。

> [!NOTE]
> **メモ** クラスは、 `CComDynamicUnkArray` 接続ポイントを持つコントロールを作成するときに、 **クラスの追加** ウィザードによって使用されます。 接続ポイントの数を手動で指定する場合は、参照をから `CComDynamicUnkArray` n に変更し `CComUnkArray<`  `>` ます。ここで、 *n* は必要な接続ポイントの数です。

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a> CComDynamicUnkArray:: Add

配列へのポインターを追加するには、このメソッドを呼び出し `IUnknown` ます。

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
`IUnknown`配列に追加するポインター。

### <a name="return-value"></a>戻り値

新しく追加されたポインターに関連付けられているクッキーを返します。

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a> CComDynamicUnkArray:: begin

インターフェイスポインターのコレクションの先頭へのポインターを返し `IUnknown` ます。

```
IUnknown**
    begin();
```

### <a name="return-value"></a>戻り値

インターフェイスポインターへのポインター `IUnknown` 。

### <a name="remarks"></a>解説

コレクションには、としてローカルに格納されるインターフェイスへのポインターが含まれてい `IUnknown` ます。 各 `IUnknown` インターフェイスを実際のインターフェイス型にキャストしてから、を呼び出します。 最初にインターフェイスを照会する必要はありません。

インターフェイスを使用する前に `IUnknown` 、それが NULL でないことを確認する必要があります。

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a> CComDynamicUnkArray:: clear

配列を空にします。

```cpp
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a> CComDynamicUnkArray::CComDynamicUnkArray

コンストラクターです。

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>解説

コレクションのサイズをゼロに設定し、値を NULL に初期化します。 必要に応じて、デストラクターによってコレクションが解放されます。

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a> CComDynamicUnkArray:: ~ CComDynamicUnkArray

デストラクターです。

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>解説

クラスコンストラクターによって割り当てられたリソースを解放します。

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a> CComDynamicUnkArray:: end

コレクション内の最後のポインターの1つ後ろへのポインターを返し `IUnknown` ます。

```
IUnknown**
    end();
```

### <a name="return-value"></a>戻り値

インターフェイスポインターへのポインター `IUnknown` 。

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a> CComDynamicUnkArray:: GetAt

指定したインデックスにある要素を取得します。

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する要素のインデックス。

### <a name="return-value"></a>戻り値

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)インターフェイスへのポインター。

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a> CComDynamicUnkArray:: GetCookie

指定したポインターに関連付けられているクッキーを取得するには、このメソッドを呼び出し `IUnknown` ます。

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>パラメーター

*ppFind*<br/>
`IUnknown`関連付けられているクッキーが必要なポインター。

### <a name="return-value"></a>戻り値

ポインターに関連付けられているクッキーを返し `IUnknown` ます。一致するポインターが見つからない場合は0を返し `IUnknown` ます。

### <a name="remarks"></a>解説

同じポインターのインスタンスが複数ある場合 `IUnknown` 、この関数は最初のインスタンスのクッキーを返します。

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a> CComDynamicUnkArray:: GetSize

配列の長さを返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

配列の長さ。

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a> CComDynamicUnkArray:: GetUnknown

`IUnknown`特定のクッキーに関連付けられているポインターを取得するには、このメソッドを呼び出します。

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*dwCookie*<br/>
関連付けられた `IUnknown` ポインターが必要なクッキー。

### <a name="return-value"></a>戻り値

ポインターを返し `IUnknown` ます。一致するクッキーが見つからない場合は NULL を返します。

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a> CComDynamicUnkArray:: Remove

配列からポインターを削除するには、このメソッドを呼び出し `IUnknown` ます。

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*dwCookie*<br/>
配列から削除するポインターを参照しているクッキー `IUnknown` 。

### <a name="return-value"></a>戻り値

ポインターが削除された場合は TRUE を返します。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[CComUnkArray クラス](../../atl/reference/ccomunkarray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
