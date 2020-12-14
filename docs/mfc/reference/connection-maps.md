---
description: '詳細情報: 接続マップ'
title: コネクション マップ
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 61d2e7023ab97aa00952aee4786b34e60ba57af7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345252"
---
# <a name="connection-maps"></a>コネクション マップ

OLE コントロールは、他のアプリケーションにインターフェイスを公開できます。 これらのインターフェイスは、コンテナーからそのコントロールへのアクセスのみを許可します。 OLE コントロールが他の OLE オブジェクトの外部インターフェイスにアクセスする場合は、コネクションポイントを確立する必要があります。 この接続ポイントを使用すると、イベントマップや通知機能などの外部ディスパッチマップへの発信アクセスを制御できます。

Microsoft Foundation Class ライブラリには、接続ポイントをサポートするプログラミングモデルが用意されています。 このモデルでは、OLE コントロールのインターフェイスまたはコネクションポイントを指定するために "接続マップ" が使用されます。 接続マップには、接続ポイントごとに1つのマクロが含まれています。 接続マップの詳細については、 [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) クラスを参照してください。

通常、コントロールは2つのコネクションポイントだけをサポートします。1つはイベント用で、もう1つはプロパティ通知用です。 これらは基本クラスによって実装され、 `COleControl` コントロールライターによる追加の処理は必要ありません。 クラスに実装する追加の接続ポイントは、手動で追加する必要があります。 MFC には、接続マップとポイントをサポートするために、次のマクロが用意されています。

### <a name="connection-map-declaration-and-demarcation"></a>接続マップの宣言と境界

|名前|説明|
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|追加のコネクションポイントを実装する埋め込みクラスを宣言します (クラス宣言で使用する必要があります)。|
|[END_CONNECTION_PART](#end_connection_part)|コネクションポイントの宣言を終了します (クラス宣言で使用する必要があります)。|
|[CONNECTION_IID](#connection_iid)|コントロールの接続ポイントのインターフェイス ID を指定します。|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|接続マップがクラスで使用されることを宣言します (クラス宣言で使用する必要があります)。|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|接続マップの定義を開始します (クラスの実装で使用する必要があります)。|
|[END_CONNECTION_MAP](#end_connection_map)|接続マップの定義を終了します (クラスの実装で使用する必要があります)。|
|[CONNECTION_PART](#connection_part)|コントロールの接続マップ内の接続ポイントを指定します。|

次の関数は、接続ポイントを使用して接続を確立および切断する際にシンクをサポートします。

### <a name="initializationtermination-of-connection-points"></a>コネクションポイントの初期化と終了

|名前|説明|
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|ソースとシンクの間の接続を確立します。|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|ソースとシンクの間の接続を切断します。|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a> BEGIN_CONNECTION_PART

BEGIN_CONNECTION_PART マクロを使用して、イベントおよびプロパティ通知接続ポイント以外の追加の接続ポイントの定義を開始します。

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
接続ポイントがあるコントロールクラスの名前を指定します。

*localClass*<br/>
コネクションポイントを実装するローカルクラスの名前を指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する宣言 (.h) ファイルで、BEGIN_CONNECTION_PART マクロを使用して接続ポイントを起動し、CONNECTION_IID マクロおよび実装するその他のメンバー関数を追加して、END_CONNECTION_PART マクロを使用して接続ポイントマップを完了します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="end_connection_part"></a><a name="end_connection_part"></a> END_CONNECTION_PART

コネクションポイントの宣言を終了します。

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>パラメーター

*localClass*<br/>
コネクションポイントを実装するローカルクラスの名前を指定します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="connection_iid"></a><a name="connection_iid"></a> CONNECTION_IID

BEGIN_CONNECTION_PART マクロと END_CONNECTION_PART マクロを使用して、OLE コントロールでサポートされているコネクションポイントのインターフェイス ID を定義します。

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>パラメーター

*iid*<br/>
コネクションポイントによって呼び出されるインターフェイスのインターフェイス ID。

### <a name="remarks"></a>解説

*Iid* 引数は、接続されているシンクでコネクションポイントが呼び出すインターフェイスを識別するために使用されるインターフェイス ID です。 次に例を示します。

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

インターフェイスを呼び出すコネクションポイントを指定し `ISinkInterface` ます。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a> DECLARE_CONNECTION_MAP

`COleControl`プログラム内の各派生クラスは、コントロールがサポートする追加の接続ポイントを指定するための接続マップを提供できます。

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>解説

コントロールで追加のポイントがサポートされている場合は、クラス宣言の最後にある DECLARE_CONNECTION_MAP マクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルで、BEGIN_CONNECTION_MAP マクロを使用して、コントロールの各接続ポイントにマクロを CONNECTION_PART し、END_CONNECTION_MAP マクロを使用して接続マップの末尾を宣言します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a> BEGIN_CONNECTION_MAP

`COleControl`プログラム内の各派生クラスは、コントロールがサポートするコネクションポイントを指定するための接続マップを提供できます。

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
接続マップがあるコントロールクラスの名前を指定します。

*theBase*<br/>
*クラス* の基底クラスの名前を指定します。

### <a name="remarks"></a>解説

(を実装する場合は、CPP) クラスのメンバー関数を定義し、BEGIN_CONNECTION_MAP マクロを使用して接続マップを開始します。次に、 [CONNECTION_PART](#connection_part) マクロを使用して接続ポイントごとにマクロエントリを追加します。 最後に、 [END_CONNECTION_MAP](#end_connection_map) マクロを使用して接続マップを完成させます。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="end_connection_map"></a><a name="end_connection_map"></a> END_CONNECTION_MAP

接続マップの定義を終了します。

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="connection_part"></a><a name="connection_part"></a> CONNECTION_PART

OLE コントロールの接続ポイントを特定のインターフェイス ID にマップします。

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
接続ポイントがあるコントロールクラスの名前を指定します。

*iid*<br/>
コネクションポイントによって呼び出されるインターフェイスのインターフェイス ID。

*localClass*<br/>
コネクションポイントを実装するローカルクラスの名前を指定します。

### <a name="remarks"></a>解説

次に例を示します。

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

コネクションポイントを使用してインターフェイスを呼び出す接続マップを実装し `IID_ISinkInterface` ます。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a> AfxConnectionAdvise

*PUnkSrc* によって指定されたソースと、 *pUnkSink* によって指定されたシンクとの間の接続を確立するには、この関数を呼び出します。

```
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD FAR* pdwCookie);
```

### <a name="parameters"></a>パラメーター

*pUnkSrc*<br/>
インターフェイスを呼び出すオブジェクトへのポインター。

*pUnkSink*<br/>
インターフェイスを実装するオブジェクトへのポインター。

*iid*<br/>
接続のインターフェイス ID。

*bRefCount*<br/>
TRUE の場合、接続を作成すると参照カウントの *pUnkSink* が増加することを示します。 FALSE は、参照カウントをインクリメントしないことを示します。

*pdwCookie*<br/>
接続識別子が返される DWORD へのポインター。 接続を切断するときに、 *Dwcookie* パラメーターとしてこの値をに渡す必要があり `AfxConnectionUnadvise` ます。

### <a name="return-value"></a>戻り値

接続が確立された場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a> AfxConnectionUnadvise

*PUnkSrc* によって指定されたソースと、 *pUnkSink* によって指定されたシンクとの間の接続を切断するには、この関数を呼び出します。

```
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD dwCookie);
```

### <a name="parameters"></a>パラメーター

*pUnkSrc*<br/>
インターフェイスを呼び出すオブジェクトへのポインター。

*pUnkSink*<br/>
インターフェイスを実装するオブジェクトへのポインター。

*iid*<br/>
コネクションポイントインターフェイスのインターフェイス ID。

*bRefCount*<br/>
TRUE の場合、接続を切断すると参照カウントの *pUnkSink* が減少することを示します。 FALSE は、参照カウントをデクリメントしないことを示します。

*dwCookie*<br/>
によって返される接続識別子 `AfxConnectionAdvise` 。

### <a name="return-value"></a>戻り値

接続が切断された場合は0以外の。それ以外の場合は0です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
