---
title: クラス
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
ms.openlocfilehash: 57383823897a434f649c6c4af78e71fe6ff66a6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327906"
---
# <a name="ccomdynamicunkarray-class"></a>クラス

このクラスは、ポインターの`IUnknown`配列を格納します。

## <a name="syntax"></a>構文

```
class CComDynamicUnkArray
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コミュチュロアンクアレイ::コミュダイナミックアンクアレイ](#ccomdynamicunkarray)|コンストラクターです。 コレクション値を NULL に初期化し、コレクションのサイズを 0 に初期化します。|
|[コミュティックアンクアレイ::~コミュティックアンクアレイ](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の関数を実行します。](#add)|配列へのポインターを`IUnknown`追加します。|
|[コミュチュロアンクアレイ::開始](#begin)|コレクション内の最初`IUnknown`のポインターへのポインターを返します。|
|[コムダイナミックアンクアレイ::クリア](#clear)|配列を空にします。|
|[コムダイナミックアンクアレイ::エンド](#end)|コレクション内の最後`IUnknown`のポインターの 1 つ後のポインターを返します。|
|[コムダイナミックアンクアレイ::ゲットアット](#getat)|指定したインデックスにある要素を取得します。|
|[コムダイナミックアンクアレイ::ゲットクッキー](#getcookie)|指定した`IUnknown`ポインターに関連付けられている Cookie を取得します。|
|[次の関数を実行します。](#getsize)|配列の長さを返します。|
|[コムダイナミックアンクアレイ::ゲットUnknown](#getunknown)|指定された Cookie に`IUnknown`関連付けられているポインターを取得します。|
|[次の操作を行います。](#remove)|配列からポインターを`IUnknown`削除します。|

## <a name="remarks"></a>解説

`CComDynamicUnkArray`は、接続ポイント上のインタフェースである`IUnknown`ポインタの動的に割り当てられた配列を保持します。 `CComDynamicUnkArray`テンプレート[クラスのパラメーター](../../atl/reference/iconnectionpointimpl-class.md)として使用できます。

開始`CComDynamicUnkArray`と[begin](#begin)[終了](#end)のメソッドを使用して、すべてのコネクション ポイントをループできます (たとえば、イベントが発生したときなど)。

接続ポイント プロキシの作成の自動化の詳細については、「[オブジェクトへの](../../atl/adding-connection-points-to-an-object.md)接続ポイントの追加」を参照してください。

> [!NOTE]
> **注**クラス`CComDynamicUnkArray`は、コネクション ポイントを持つコントロールを作成するときに**クラスの追加**ウィザードで使用されます。 接続`CComDynamicUnkArray`ポイントの数を手動で指定する場合は、参照を`CComUnkArray<`*n*`>`に変更します*n*。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a>次の関数を実行します。

配列へのポインターを`IUnknown`追加します。

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
配列`IUnknown`に追加するポインター。

### <a name="return-value"></a>戻り値

新しく追加されたポインターに関連付けられている Cookie を返します。

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a>コミュチュロアンクアレイ::開始

`IUnknown`インターフェイス ポインターのコレクションの先頭へのポインターを返します。

```
IUnknown**
    begin();
```

### <a name="return-value"></a>戻り値

`IUnknown`インターフェイス ポインターへのポインター。

### <a name="remarks"></a>解説

このコレクションには、ローカルに格納されているインターフェイスへの`IUnknown`ポインターが格納されます。 各`IUnknown`インターフェイスを実際のインターフェイス型にキャストし、それを通じて呼び出します。 最初にインターフェイスを照会する必要はありません。

インターフェイスを使用`IUnknown`する前に、NULL ではないことを確認する必要があります。

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a>コムダイナミックアンクアレイ::クリア

配列を空にします。

```
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a>コミュチュロアンクアレイ::コミュダイナミックアンクアレイ

コンストラクターです。

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>解説

コレクションサイズをゼロに設定し、値を NULL に初期化します。 デストラクタは、必要に応じてコレクションを解放します。

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a>コミュティックアンクアレイ::~コミュティックアンクアレイ

デストラクターです。

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>解説

クラス コンストラクターによって割り当てられたリソースを解放します。

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a>コムダイナミックアンクアレイ::エンド

コレクション内の最後`IUnknown`のポインターの 1 つ後のポインターを返します。

```
IUnknown**
    end();
```

### <a name="return-value"></a>戻り値

`IUnknown`インターフェイス ポインターへのポインター。

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a>コムダイナミックアンクアレイ::ゲットアット

指定したインデックスにある要素を取得します。

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する要素のインデックス。

### <a name="return-value"></a>戻り値

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)インターフェイスへのポインター。

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a>コムダイナミックアンクアレイ::ゲットクッキー

指定した`IUnknown`ポインターに関連付けられている Cookie を取得します。

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>パラメーター

*を見つける*<br/>
関連`IUnknown`付けられた Cookie が必要なポインター。

### <a name="return-value"></a>戻り値

`IUnknown`ポインターに関連付けられた Cookie を返します`IUnknown`。

### <a name="remarks"></a>解説

同じ`IUnknown`ポインターのインスタンスが複数ある場合、この関数は最初のインスタンスのクッキーを返します。

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a>次の関数を実行します。

配列の長さを返します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

配列の長さ。

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a>コムダイナミックアンクアレイ::ゲットUnknown

指定された Cookie に`IUnknown`関連付けられているポインターを取得します。

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*ドウクッキー*<br/>
関連付けられた`IUnknown`ポインターが必要な Cookie。

### <a name="return-value"></a>戻り値

一致`IUnknown`する Cookie が見つからない場合は、ポインターを返します。

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a>次の操作を行います。

配列からポインターを`IUnknown`削除します。

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*ドウクッキー*<br/>
配列から削除する`IUnknown`ポインターを参照する Cookie。

### <a name="return-value"></a>戻り値

ポインターが削除された場合は TRUE を返します。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomunkarray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
