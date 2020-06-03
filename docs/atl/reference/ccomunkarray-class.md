---
title: クラス
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
ms.openlocfilehash: c1d2f0296394d3979ef4f152e3f902c89adf5b45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327301"
---
# <a name="ccomunkarray-class"></a>クラス

このクラスは`IUnknown`ポインターを格納し[、IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)テンプレート クラスのパラメーターとして使用するように設計されています。

## <a name="syntax"></a>構文

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
静的配列に保持`IUnknown`できるポインターの最大数。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コマンクアレイ::コマンクアレイ](#ccomunkarray)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コマンウンクアレイ::追加](#add)|配列へのポインターを`IUnknown`追加します。|
|[コマンウンクアレイ::開始](#begin)|コレクション内の最初`IUnknown`のポインターへのポインターを返します。|
|[コマンウンクアレイ::エンド](#end)|コレクション内の最後`IUnknown`のポインターの 1 つ後のポインターを返します。|
|[コムウンクアレイ::ゲットクッキー](#getcookie)|指定した`IUnknown`ポインターに関連付けられている Cookie を取得します。|
|[コマンウンクアレイ::ゲットUnknown](#getunknown)|指定された Cookie に`IUnknown`関連付けられているポインターを取得します。|
|[コミュンクアレイ::削除](#remove)|配列からポインターを`IUnknown`削除します。|

## <a name="remarks"></a>解説

`CComUnkArray`は、接続ポイント上`IUnknown`の各インターフェイスの固定数のポインタを保持します。 `CComUnkArray`テンプレート[クラスのパラメーター](../../atl/reference/iconnectionpointimpl-class.md)として使用できます。 `CComUnkArray<1>`は、1 つの接続`CComUnkArray`ポイントに最適化されたテンプレートの特殊化です。

開始`CComUnkArray`と[begin](#begin)[終了](#end)のメソッドを使用して、すべてのコネクション ポイントをループできます (たとえば、イベントが発生したときなど)。

接続ポイント プロキシの作成の自動化の詳細については、「[オブジェクトへの](../../atl/adding-connection-points-to-an-object.md)接続ポイントの追加」を参照してください。

> [!NOTE]
> **注**クラス[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)は、コネクション ポイントを持つコントロールを作成するときに**クラスの追加**ウィザードで使用されます。 接続`CComDynamicUnkArray`ポイントの数を手動で指定する場合は、参照を`CComUnkArray<`*n*`>`に変更します*n*。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ccomunkarrayadd"></a><a name="add"></a>コマンウンクアレイ::追加

配列へのポインターを`IUnknown`追加します。

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
配列へのポインターを`IUnknown`追加します。

### <a name="return-value"></a>戻り値

新しく追加されたポインターに関連付けられた Cookie を返します。

## <a name="ccomunkarraybegin"></a><a name="begin"></a>コマンウンクアレイ::開始

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

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a>コマンクアレイ::コマンクアレイ

コンストラクターです。

```
CComUnkArray();
```

### <a name="remarks"></a>解説

ポインターを保持`nMaxSize``IUnknown`するようにコレクションを設定し、ポインターを NULL に初期化します。

## <a name="ccomunkarrayend"></a><a name="end"></a>コマンウンクアレイ::エンド

コレクション内の最後`IUnknown`のポインターの 1 つ後のポインターを返します。

```
IUnknown**
    end();
```

### <a name="return-value"></a>戻り値

`IUnknown`インターフェイス ポインターへのポインター。

### <a name="remarks"></a>解説

メソッド`CComUnkArray``begin`および`end`メソッドを使用して、イベントが発生した場合など、すべてのコネクション ポイントをループ処理できます。

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a>コムウンクアレイ::ゲットクッキー

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

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a>コマンウンクアレイ::ゲットUnknown

指定された Cookie に`IUnknown`関連付けられているポインターを取得します。

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*ドウクッキー*<br/>
関連付けられた`IUnknown`ポインターが必要な Cookie。

### <a name="return-value"></a>戻り値

一致`IUnknown`する Cookie が見つからない場合は、ポインターを返します。

## <a name="ccomunkarrayremove"></a><a name="remove"></a>コミュンクアレイ::削除

配列からポインターを`IUnknown`削除します。

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*ドウクッキー*<br/>
配列から削除する`IUnknown`ポインターを参照する Cookie。

### <a name="return-value"></a>戻り値

ポインターが削除された場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
