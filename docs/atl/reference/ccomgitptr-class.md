---
title: コムギプタークラス
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: 230eeb1577189d2057e530e1df8ef99c611fb32b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327841"
---
# <a name="ccomgitptr-class"></a>コムギプタークラス

このクラスは、インターフェイス ポインターとグローバル インターフェイス テーブル (GIT) を処理するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
GIT に格納されるインターフェイス ポインターの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ココムギプター::CComGITPtr](#ccomgitptr)|コンストラクターです。|
|[ココムギプター::~CComGITPtr](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ココムギップター::アタッチ](#attach)|インターフェイス ポインターをグローバル インターフェイス テーブル (GIT) に登録します。|
|[ココムギップター::コピート](#copyto)|渡されたポインターにグローバル インターフェイス テーブル (GIT) からインターフェイスをコピーします。|
|[ココムギップター::Dエタッハ](#detach)|`CComGITPtr`インターフェイスとオブジェクトの関連付けを解除します。|
|[クコムギットプター::ゲットクッキー](#getcookie)|`CComGITPtr`オブジェクトから Cookie を返します。|
|[CComGITPtr::取り消し](#revoke)|グローバル インターフェイス テーブル (GIT) からインターフェイスを削除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コムギプター::オペレーターDWORD](#operator_dword)|オブジェクトからクッキーを`CComGITPtr`返します。|
|[CComGITPtr::演算子 =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムギップター::m_dwCookie](#m_dwcookie)|クッキー。|

## <a name="remarks"></a>解説

フリー スレッド マーシャラーを集約し、他のオブジェクトから取得したインターフェイス ポインタを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャリングされるように追加の手順を実行する必要があります。 通常、この処理では、インターフェイス ポインターを GIT に格納し、使用するたびに GIT からポインターを取得します。 クラス`CComGITPtr`は、GIT に格納されているインターフェイス ポインターを使用するために提供されます。

> [!NOTE]
> グローバル インターフェイス テーブル機能は、Windows 95 で使用できるのは、DCOM バージョン 1.1 以降の Windows 95、Windows 98、Windows NT 4.0 (サービス パック 3 以降)、および Windows 2000 とのみです。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomgitptrattach"></a><a name="attach"></a>ココムギップター::アタッチ

インターフェイス ポインターをグローバル インターフェイス テーブル (GIT) に登録します。

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
GIT に追加するインターフェイス ポインター。

*ドウクッキー*<br/>
インターフェイス ポインターを識別するために使用される Cookie。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

デバッグ ビルドでは、GIT が有効でない場合、または Cookie が NULL に等しい場合にアサーション エラーが発生します。

## <a name="ccomgitptrccomgitptr"></a><a name="ccomgitptr"></a>ココムギプター::CComGITPtr

コンストラクターです。

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]グローバル インターフェイス テーブル (GIT) に格納されるインターフェイス ポインター。

*Git*<br/>
[in]既存`CComGITPtr`のオブジェクトへの参照。

*ドウクッキー*<br/>
[in]インターフェイス ポインターを識別するために使用される Cookie。

*Rv*<br/>
[in]データの`CComGITPtr`移動元のソース オブジェクト。

### <a name="remarks"></a>解説

既存`CComGITPtr`のオブジェクト`CComGITPtr`を使用して、必要に応じて新しいオブジェクトを作成します。

*rv*を使用するコンストラクタは移動コンストラクタです。 データはソース*rv*から移動され *、rv*はクリアされます。

## <a name="ccomgitptrccomgitptr"></a><a name="dtor"></a>ココムギプター::~CComGITPtr

デストラクターです。

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>解説

[CComGITPtr::Revoke](#revoke)を使用して、グローバル インターフェイス テーブル (GIT) からインターフェイスを削除します。

## <a name="ccomgitptrcopyto"></a><a name="copyto"></a>ココムギップター::コピート

渡されたポインターにグローバル インターフェイス テーブル (GIT) からインターフェイスをコピーします。

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>パラメーター

*頁*<br/>
インターフェイスを受け取るポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

GIT からのインターフェイスが渡されたポインタにコピーされます。 ポインターは、不要になった場合に呼び出し元によって解放される必要があります。

## <a name="ccomgitptrdetach"></a><a name="detach"></a>ココムギップター::Dエタッハ

`CComGITPtr`インターフェイスとオブジェクトの関連付けを解除します。

```
DWORD Detach() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトからクッキーを`CComGITPtr`返します。

### <a name="remarks"></a>解説

呼び出し元は[、CComGITPtr::Revoke](#revoke)を使用して、GIT からインターフェイスを削除する必要があります。

## <a name="ccomgitptrgetcookie"></a><a name="getcookie"></a>クコムギットプター::ゲットクッキー

`CComGITPtr`オブジェクトから Cookie を返します。

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>戻り値

クッキーを返します。

### <a name="remarks"></a>解説

クッキーは、インターフェイスとその位置を識別するために使用される変数です。

## <a name="ccomgitptrm_dwcookie"></a><a name="m_dwcookie"></a>コムギップター::m_dwCookie

クッキー。

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>解説

クッキーは、インターフェイスとその位置を識別するために使用されるメンバー変数です。

## <a name="ccomgitptroperator-"></a><a name="operator_eq"></a>CComGITPtr::演算子 =

代入演算子。

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]インターフェイスへのポインター。

*Git*<br/>
[in]`CComGITPtr`オブジェクトへの参照。

*ドウクッキー*<br/>
[in]インターフェイス ポインターを識別するために使用される Cookie。

*Rv*<br/>
[in]データ`CComGITPtr`の移動元。

### <a name="return-value"></a>戻り値

更新された`CComGITPtr`オブジェクトを返します。

### <a name="remarks"></a>解説

既存の`CComGITPtr`オブジェクトまたはグローバル インターフェイス テーブルへの参照から、オブジェクトに新しい値を割り当てます。

## <a name="ccomgitptroperator-dword"></a><a name="operator_dword"></a>コムギプター::オペレーターDWORD

オブジェクトに関連付けられているクッキー`CComGITPtr`を返します。

```
operator DWORD() const;
```

### <a name="remarks"></a>解説

クッキーは、インターフェイスとその位置を識別するために使用される変数です。

## <a name="ccomgitptrrevoke"></a><a name="revoke"></a>CComGITPtr::取り消し

グローバル インターフェイス テーブル (GIT) から現在のインターフェイスを削除します。

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

GIT からインターフェイスを削除します。

## <a name="see-also"></a>関連項目

[フリー スレッド マーシャラー](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[アパートメント間のインターフェイスへのアクセス](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[グローバル インターフェイス テーブルを使用する場合](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
