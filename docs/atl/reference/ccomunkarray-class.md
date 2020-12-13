---
description: '詳細情報: CComUnkArray クラス'
title: CComUnkArray クラス
ms.date: 11/04/2016
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
ms.openlocfilehash: e03022fb751b487debb9f81d9e3d99ce46f1b9e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142143"
---
# <a name="ccomunkarray-class"></a>CComUnkArray クラス

このクラス `IUnknown` はポインターを格納し、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) テンプレートクラスのパラメーターとして使用するように設計されています。

## <a name="syntax"></a>構文

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>パラメーター

*nMaxSize*<br/>
`IUnknown`静的配列に保持できるポインターの最大数。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComUnkArray:: Add](#add)|配列へのポインターを追加するには、このメソッドを呼び出し `IUnknown` ます。|
|[CComUnkArray:: begin](#begin)|コレクション内の最初のポインターへのポインターを返し `IUnknown` ます。|
|[CComUnkArray:: end](#end)|コレクション内の最後のポインターの1つ後ろへのポインターを返し `IUnknown` ます。|
|[CComUnkArray:: GetCookie](#getcookie)|指定したポインターに関連付けられているクッキーを取得するには、このメソッドを呼び出し `IUnknown` ます。|
|[CComUnkArray:: GetUnknown](#getunknown)|`IUnknown`特定のクッキーに関連付けられているポインターを取得するには、このメソッドを呼び出します。|
|[CComUnkArray:: Remove](#remove)|配列からポインターを削除するには、このメソッドを呼び出し `IUnknown` ます。|

## <a name="remarks"></a>解説

`CComUnkArray` 固定された数のポインターを保持し `IUnknown` ます。各インターフェイスは接続ポイントにあります。 `CComUnkArray` は、 [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) テンプレートクラスのパラメーターとして使用できます。 `CComUnkArray<1>` は、 `CComUnkArray` 1 つの接続ポイントに対して最適化された、のテンプレート特殊化です。

`CComUnkArray` [Begin](#begin)および[end](#end)メソッドを使用して、すべてのコネクションポイントをループ処理できます (たとえば、イベントが発生したとき)。

接続ポイントプロキシの作成を自動化する方法の詳細については [、「オブジェクトへの接続ポイントの追加](../../atl/adding-connection-points-to-an-object.md) 」を参照してください。

> [!NOTE]
> **メモ** クラス [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) は、接続ポイントを持つコントロールを作成するときに、 **クラスの追加** ウィザードによって使用されます。 接続ポイントの数を手動で指定する場合は、参照をから `CComDynamicUnkArray` n に変更し `CComUnkArray<`  `>` ます。ここで、 *n* は必要な接続ポイントの数です。

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ccomunkarrayadd"></a><a name="add"></a> CComUnkArray:: Add

配列へのポインターを追加するには、このメソッドを呼び出し `IUnknown` ます。

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
配列へのポインターを追加するには、このメソッドを呼び出し `IUnknown` ます。

### <a name="return-value"></a>戻り値

新しく追加されたポインターに関連付けられているクッキーを返します。または、配列が新しいポインターを格納するのに十分な大きさでない場合は0を返します。

## <a name="ccomunkarraybegin"></a><a name="begin"></a> CComUnkArray:: begin

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

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a> CComUnkArray::CComUnkArray

コンストラクターです。

```
CComUnkArray();
```

### <a name="remarks"></a>解説

ポインターを保持するコレクションを設定 `nMaxSize` `IUnknown` し、ポインターを NULL に初期化します。

## <a name="ccomunkarrayend"></a><a name="end"></a> CComUnkArray:: end

コレクション内の最後のポインターの1つ後ろへのポインターを返し `IUnknown` ます。

```
IUnknown**
    end();
```

### <a name="return-value"></a>戻り値

インターフェイスポインターへのポインター `IUnknown` 。

### <a name="remarks"></a>解説

`CComUnkArray`メソッドとは、 `begin` `end` イベントが発生したときなど、すべての接続ポイントをループ処理するために使用できます。

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a> CComUnkArray:: GetCookie

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

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a> CComUnkArray:: GetUnknown

`IUnknown`特定のクッキーに関連付けられているポインターを取得するには、このメソッドを呼び出します。

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*dwCookie*<br/>
関連付けられた `IUnknown` ポインターが必要なクッキー。

### <a name="return-value"></a>戻り値

ポインターを返し `IUnknown` ます。一致するクッキーが見つからない場合は NULL を返します。

## <a name="ccomunkarrayremove"></a><a name="remove"></a> CComUnkArray:: Remove

配列からポインターを削除するには、このメソッドを呼び出し `IUnknown` ます。

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*dwCookie*<br/>
配列から削除するポインターを参照しているクッキー `IUnknown` 。

### <a name="return-value"></a>戻り値

ポインターが削除された場合は TRUE、それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[CComDynamicUnkArray クラス](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
