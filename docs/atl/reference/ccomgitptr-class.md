---
description: '詳細情報: CComGITPtr クラス'
title: CComGITPtr クラス
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
ms.openlocfilehash: a457c0dea1679b177b72318d636c856334c85e36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146641"
---
# <a name="ccomgitptr-class"></a>CComGITPtr クラス

このクラスには、インターフェイスポインターとグローバルインターフェイステーブル (GIT) を処理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
GIT に格納されるインターフェイスポインターの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|コンストラクターです。|
|[CComGITPtr:: ~ CComGITPtr](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComGITPtr:: Attach](#attach)|このメソッドを呼び出して、グローバルインターフェイステーブル (GIT) にインターフェイスポインターを登録します。|
|[CComGITPtr:: CopyTo](#copyto)|このメソッドを呼び出して、グローバルインターフェイステーブル (GIT) から渡されたポインターにインターフェイスをコピーします。|
|[CComGITPtr::D etach](#detach)|オブジェクトからインターフェイスの関連付けを解除するには、このメソッドを呼び出し `CComGITPtr` ます。|
|[CComGITPtr:: GetCookie](#getcookie)|オブジェクトからクッキーを返すには、このメソッドを呼び出し `CComGITPtr` ます。|
|[CComGITPtr:: Revoke](#revoke)|このメソッドを呼び出して、グローバルインターフェイステーブル (GIT) からインターフェイスを削除します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComGITPtr:: operator DWORD](#operator_dword)|オブジェクトからクッキーを返し `CComGITPtr` ます。|
|[CComGITPtr:: operator =](#operator_eq)|代入演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComGITPtr:: m_dwCookie](#m_dwcookie)|クッキー。|

## <a name="remarks"></a>解説

フリースレッドマーシャラーを集約し、他のオブジェクトから取得したインターフェイスポインターを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャリングされるようにするために、追加の手順を実行する必要があります。 通常、これは、GIT にインターフェイスポインターを格納し、使用されるたびに GIT からポインターを取得する必要があります。 クラス `CComGITPtr` は、GIT に格納されているインターフェイスポインターを使用できるようにするために用意されています。

> [!NOTE]
> グローバルインターフェイステーブル機能は、Windows 95 の DCOM バージョン1.1 以降、Windows 98、Windows NT 4.0 Service Pack 3 以降、および Windows 2000 でのみ使用できます。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="ccomgitptrattach"></a><a name="attach"></a> CComGITPtr:: Attach

このメソッドを呼び出して、グローバルインターフェイステーブル (GIT) にインターフェイスポインターを登録します。

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
GIT に追加するインターフェイスポインター。

*dwCookie*<br/>
インターフェイスポインターを識別するために使用されるクッキー。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

デバッグビルドでは、GIT が有効でない場合、または cookie が NULL の場合にアサーションエラーが発生します。

## <a name="ccomgitptrccomgitptr"></a><a name="ccomgitptr"></a> CComGITPtr::CComGITPtr

コンストラクターです。

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からグローバルインターフェイステーブル (GIT) に格納されるインターフェイスポインター。

*git*<br/>
から既存のオブジェクトへの参照 `CComGITPtr` 。

*dwCookie*<br/>
からインターフェイスポインターを識別するために使用されるクッキー。

*rv*<br/>
から `CComGITPtr` データの移動元のオブジェクト。

### <a name="remarks"></a>解説

新しいオブジェクトを作成し `CComGITPtr` ます。必要に応じて、既存のオブジェクトを使用し `CComGITPtr` ます。

*Rv* を利用するコンストラクターは、移動コンストラクターです。 データは source から移動さ *れ、* *rv* はクリアされます。

## <a name="ccomgitptrccomgitptr"></a><a name="dtor"></a> CComGITPtr:: ~ CComGITPtr

デストラクターです。

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>解説

[CComGITPtr:: Revoke](#revoke)を使用して、グローバルインターフェイステーブル (GIT) からインターフェイスを削除します。

## <a name="ccomgitptrcopyto"></a><a name="copyto"></a> CComGITPtr:: CopyTo

このメソッドを呼び出して、グローバルインターフェイステーブル (GIT) から渡されたポインターにインターフェイスをコピーします。

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
インターフェイスを受け取るポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

渡されたポインターに GIT からのインターフェイスがコピーされます。 ポインターは、不要になったときに呼び出し元によって解放される必要があります。

## <a name="ccomgitptrdetach"></a><a name="detach"></a> CComGITPtr::D etach

オブジェクトからインターフェイスの関連付けを解除するには、このメソッドを呼び出し `CComGITPtr` ます。

```
DWORD Detach() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトからクッキーを返し `CComGITPtr` ます。

### <a name="remarks"></a>解説

[CComGITPtr:: Revoke](#revoke)を使用して、GIT からインターフェイスを削除するのは呼び出し元の権限です。

## <a name="ccomgitptrgetcookie"></a><a name="getcookie"></a> CComGITPtr:: GetCookie

オブジェクトからクッキーを返すには、このメソッドを呼び出し `CComGITPtr` ます。

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>戻り値

クッキーを返します。

### <a name="remarks"></a>解説

Cookie は、インターフェイスとその場所を識別するために使用される変数です。

## <a name="ccomgitptrm_dwcookie"></a><a name="m_dwcookie"></a> CComGITPtr:: m_dwCookie

クッキー。

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>解説

Cookie は、インターフェイスとその場所を識別するために使用されるメンバー変数です。

## <a name="ccomgitptroperator-"></a><a name="operator_eq"></a> CComGITPtr:: operator =

代入演算子。

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からインターフェイスへのポインター。

*git*<br/>
からオブジェクトへの参照 `CComGITPtr` 。

*dwCookie*<br/>
からインターフェイスポインターを識別するために使用されるクッキー。

*rv*<br/>
から `CComGITPtr` データの移動元の。

### <a name="return-value"></a>戻り値

更新されたオブジェクトを返し `CComGITPtr` ます。

### <a name="remarks"></a>解説

`CComGITPtr`既存のオブジェクトまたはグローバルインターフェイステーブルへの参照から、オブジェクトに新しい値を割り当てます。

## <a name="ccomgitptroperator-dword"></a><a name="operator_dword"></a> CComGITPtr:: operator DWORD

オブジェクトに関連付けられているクッキーを返し `CComGITPtr` ます。

```
operator DWORD() const;
```

### <a name="remarks"></a>解説

Cookie は、インターフェイスとその場所を識別するために使用される変数です。

## <a name="ccomgitptrrevoke"></a><a name="revoke"></a> CComGITPtr:: Revoke

現在のインターフェイスをグローバルインターフェイステーブル (GIT) から削除するには、このメソッドを呼び出します。

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

GIT からインターフェイスを削除します。

## <a name="see-also"></a>関連項目

[フリー スレッド マーシャラー](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[アパートメント間のインターフェイスへのアクセス](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[グローバルインターフェイステーブルを使用する場合](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
