---
title: コネクション マップ
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 947cd09023ef4028a32db8e2e4e8b33f7e04e0dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374802"
---
# <a name="connection-maps"></a>コネクション マップ

OLE コントロールは、他のアプリケーションにインターフェイスを公開できます。 これらのインターフェイスは、コンテナーからそのコントロールへのアクセスのみを許可します。 OLE コントロールが他の OLE オブジェクトの外部インターフェイスにアクセスする場合は、コネクション ポイントを確立する必要があります。 このコネクション ポイントを使用すると、イベント マップや通知関数などの外部ディスパッチ マップへの制御送信アクセスが許可されます。

Microsoft Foundation クラス ライブラリには、コネクション ポイントをサポートするプログラミング モデルが用意されています。 このモデルでは、OLE コントロールのインターフェイスまたはコネクション ポイントを指定するために"接続マップ" が使用されます。 接続マップには、接続ポイントごとに 1 つのマクロが含まれます。 接続マップの詳細については、[クラス](../../mfc/reference/cconnectionpoint-class.md)を参照してください。

通常、コントロールは、イベント用とプロパティ通知用の 2 つの接続ポイントのみをサポートします。 これらは`COleControl`基本クラスによって実装され、コントロール ライターによる追加の作業は必要ありません。 クラスに実装する追加のコネクション ポイントは、手動で追加する必要があります。 接続マップとポイントをサポートするために、MFC には次のマクロが用意されています。

### <a name="connection-map-declaration-and-demarcation"></a>接続マップの宣言と境界

|||
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|追加のコネクション ポイントを実装する埋め込みクラスを宣言します (クラス宣言で使用する必要があります)。|
|[END_CONNECTION_PART](#end_connection_part)|コネクション ポイントの宣言を終了します (クラス宣言で使用する必要があります)。|
|[CONNECTION_IID](#connection_iid)|コントロールのコネクション ポイントのインターフェイス ID を指定します。|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|接続マップがクラスで使用されることを宣言します (クラス宣言で使用する必要があります)。|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|接続マップの定義を開始します (クラス実装で使用する必要があります)。|
|[END_CONNECTION_MAP](#end_connection_map)|接続マップの定義を終了します (クラス実装で使用する必要があります)。|
|[CONNECTION_PART](#connection_part)|コントロールの接続マップ内の接続ポイントを指定します。|

次の関数は、接続ポイントを使用して接続を確立および切断するシンクを支援します。

### <a name="initializationtermination-of-connection-points"></a>接続ポイントの初期化/終了

|||
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|ソースとシンクの間の接続を確立します。|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|ソースとシンクの間の接続を切断します。|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a>BEGIN_CONNECTION_PART

BEGIN_CONNECTION_PART マクロを使用して、イベントおよびプロパティ通知コネクション ポイント以外の追加コネクション ポイントの定義を開始します。

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
コネクション ポイントが指定されているコントロール クラスの名前を指定します。

*ローカルクラス*<br/>
コネクション ポイントを実装するローカル クラスの名前を指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する宣言 (.h) ファイルで、BEGIN_CONNECTION_PART マクロを使用してコネクション ポイントを開始し、CONNECTION_IID マクロと実装するその他のメンバー関数を追加して、END_CONNECTION_PART マクロを使用して接続ポイント マップを完成させます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="end_connection_part"></a><a name="end_connection_part"></a>END_CONNECTION_PART

コネクション ポイントの宣言を終了します。

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>パラメーター

*ローカルクラス*<br/>
コネクション ポイントを実装するローカル クラスの名前を指定します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="connection_iid"></a><a name="connection_iid"></a>CONNECTION_IID

BEGIN_CONNECTION_PART とEND_CONNECTION_PARTマクロの間で使用して、OLE コントロールでサポートされるコネクション ポイントのインターフェイス ID を定義します。

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>パラメーター

*Iid*<br/>
コネクション ポイントによって呼び出されるインターフェイスのインターフェイス ID。

### <a name="remarks"></a>解説

*iid*引数は、接続されたシンクでコネクション ポイントが呼び出すインターフェイスを識別するために使用されるインターフェイス ID です。 次に例を示します。

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

インターフェイスを呼び出すコネクション`ISinkInterface`ポイントを指定します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a>DECLARE_CONNECTION_MAP

プログラム`COleControl`内の各派生クラスは、コントロールがサポートする追加のコネクション ポイントを指定する接続マップを提供できます。

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>解説

コントロールが追加のポイントをサポートしている場合は、クラス宣言の最後にDECLARE_CONNECTION_MAP マクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルで、BEGIN_CONNECTION_MAP マクロ、コントロールのコネクション ポイントごとにマクロをCONNECTION_PART、接続マップの終わりを宣言するEND_CONNECTION_MAP マクロを使用します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a>BEGIN_CONNECTION_MAP

プログラム`COleControl`内の各派生クラスは、コントロールがサポートするコネクション ポイントを指定するコネクション マップを提供できます。

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
接続マップが設定されているコントロール クラスの名前を指定します。

*ザベース*<br/>
クラスの基本クラスの名前*を*指定します。

### <a name="remarks"></a>解説

実装 (.CPP) ファイルを使用してクラスのメンバー関数を定義し、BEGIN_CONNECTION_MAP マクロを使用して接続マップを開始し[、CONNECTION_PART](#connection_part)マクロを使用して各コネクション ポイントのマクロ エントリを追加します。 最後に[、END_CONNECTION_MAP](#end_connection_map)マクロを使用して接続マップを完成させます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="end_connection_map"></a><a name="end_connection_map"></a>END_CONNECTION_MAP

接続マップの定義を終了します。

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="connection_part"></a><a name="connection_part"></a>CONNECTION_PART

OLE コントロールのコネクション ポイントを特定のインターフェイス ID に割り当てる。

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
コネクション ポイントが指定されているコントロール クラスの名前を指定します。

*Iid*<br/>
コネクション ポイントによって呼び出されるインターフェイスのインターフェイス ID。

*ローカルクラス*<br/>
コネクション ポイントを実装するローカル クラスの名前を指定します。

### <a name="remarks"></a>解説

次に例を示します。

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

インターフェイスを呼び出す接続ポイントを持つ接続マップを`IID_ISinkInterface`実装します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a>アfx コネクションアダプタ

*pUnkSrc*で指定されたソースと *、pUnkSink*で指定されたシンクとの間の接続を確立します。

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

*プンクシンク*<br/>
インターフェイスを実装するオブジェクトへのポインター。

*Iid*<br/>
接続のインターフェイス ID。

*カウント*<br/>
TRUE は、接続を作成すると *、pUnkSink*の参照カウントがインクリメントされることを示します。 FALSE は、参照カウントをインクリメントしないことを示します。

*pdwクッキー*<br/>
接続識別子が返される DWORD へのポインター。 接続を切断`AfxConnectionUnadvise`するときに、この値を*dwCookie*パラメーターとして渡す必要があります。

### <a name="return-value"></a>戻り値

接続が確立された場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a>アfxコネクションアンアドバイス

*pUnkSink*で指定されたソースとシンクとの間の接続を切断します。 *pUnkSink*

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

*プンクシンク*<br/>
インターフェイスを実装するオブジェクトへのポインター。

*Iid*<br/>
コネクション ポイント インターフェイスのインターフェイス ID。

*カウント*<br/>
TRUE は、接続を切断すると *、pUnkSink*の参照カウントが減分されることを示します。 FALSE は、参照カウントを減算しないことを示します。

*ドウクッキー*<br/>
によって返される`AfxConnectionAdvise`接続識別子。

### <a name="return-value"></a>戻り値

接続が切断された場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
