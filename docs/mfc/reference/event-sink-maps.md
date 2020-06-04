---
title: イベント シンク マップ
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: 731ed2403aae3332e81702673d1181e9e52399a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365731"
---
# <a name="event-sink-maps"></a>イベント シンク マップ

埋め込み OLE コントロールがイベントを発生すると、コントロールのコンテナーは、MFC によって提供される "イベント シンク マップ" と呼ばれる機構を使用してイベントを受け取ります。 このイベント シンク マップは、各イベントのハンドラ関数と、それらのイベントのパラメータを指定します。 イベント シンク マップの詳細については[、「ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)」を参照してください。

### <a name="event-sink-maps"></a>イベント シンク マップ

|||
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|イベント シンク マップの定義を開始します。|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|イベント シンク マップを宣言します。|
|[END_EVENTSINK_MAP](#end_eventsink_map)|イベント シンク マップの定義を終了します。|
|[ON_EVENT](#on_event)|特定のイベントのイベント ハンドラーを定義します。|
|[ON_EVENT_RANGE](#on_event_range)|OLE コントロールのセットから発生する特定のイベントのイベント ハンドラーを定義します。|
|[ON_EVENT_REFLECT](#on_event_reflect)|コントロールのコンテナーによって処理される前に、コントロールによって発生したイベントを受け取ります。|
|[ON_PROPNOTIFY](#on_propnotify)|OLE コントロールからのプロパティ通知を処理するためのハンドラーを定義します。|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE コントロールのセットからプロパティ通知を処理するためのハンドラーを定義します。|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|コントロールのコンテナーによって処理される前に、コントロールから送信されたプロパティ通知を受信します。|

## <a name="begin_eventsink_map"></a><a name="begin_eventsink_map"></a>BEGIN_EVENTSINK_MAP

イベント シンク マップの定義を開始します。

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
イベント シンク マップがこれに割り当てるコントロール クラスの名前を指定します。

*Baseclass*<br/>
クラスの基本クラスの名前*を*指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、BEGIN_EVENTSINK_MAP マクロを使用してイベント シンク マップを開始し、通知対象の各イベントのマクロ エントリを追加し、END_EVENTSINK_MAP マクロを使用してイベント シンク マップを完了します。

イベント シンク マップと OLE コントロール コンテナの詳細については[、「ActiveX コントロール コンテナ](../../mfc/activex-control-containers.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="declare_eventsink_map"></a><a name="declare_eventsink_map"></a>DECLARE_EVENTSINK_MAP

OLE コンテナーは、コンテナーに通知されるイベントを指定するイベント シンク マップを提供できます。

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>解説

クラス宣言の最後にDECLARE_EVENTSINK_MAPマクロを使用します。 次に、 で.CPP ファイルクラスのメンバー関数を定義し、BEGIN_EVENTSINK_MAP マクロ、通知対象の各イベントのマクロ エントリ、およびイベント シンク リストの末尾を宣言するEND_EVENTSINK_MAP マクロを使用します。

イベント シンク マップの詳細については[、「ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="end_eventsink_map"></a><a name="end_eventsink_map"></a>END_EVENTSINK_MAP

イベント シンク マップの定義を終了します。

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="on_event"></a><a name="on_event"></a>ON_EVENT

ON_EVENT マクロを使用して、OLE コントロールによって発生するイベントのイベント ハンドラー関数を定義します。

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベント シンク マップが属するクラス。

*id*<br/>
OLE コントロールのコントロール ID。

*Dispid*<br/>
コントロールによって発生したイベントのディスパッチ ID。

*プンハンドラー*<br/>
イベントを処理するメンバー関数へのポインター。 この関数には、BOOL の戻り値の型と、イベントのパラメーターに一致するパラメーター型*が必要です (vtsParams*を参照)。 この関数は、イベントが処理されたことを示す TRUE を返す必要があります。それ以外の場合は FALSE。

*vtsパラム*<br/>
イベントのパラメーターの型を指定する**VTS_** 定数のシーケンス。 これらは、DISP_FUNCTIONなどのディスパッチ マップ エントリで使用される定数と同じです。

### <a name="remarks"></a>解説

*vtsParams*引数は **、VTS_** 定数の値の一覧をスペースで区切ったものです。 これらの値のうち 1 つ以上がスペースで区切られ (コンマではなく) 関数のパラメーター・リストが指定されます。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

は、短整数の後に BOOL が続くリストを指定します。

**VTS_** 定数の一覧については[、「EVENT_CUSTOM」](event-maps.md#event_custom)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="on_event_range"></a><a name="on_event_range"></a>ON_EVENT_RANGE

ON_EVENT_RANGE マクロを使用して、コントロール ID が連続した ID 範囲内にある OLE コントロールによって発生するイベントのイベント ハンドラー関数を定義します。

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベント シンク マップが属するクラス。

*id最初*<br/>
範囲内の最初の OLE コントロールのコントロール ID。

*idLast*<br/>
範囲内の最後の OLE コントロールのコントロール ID。

*Dispid*<br/>
コントロールによって発生したイベントのディスパッチ ID。

*プンハンドラー*<br/>
イベントを処理するメンバー関数へのポインター。 この関数には、BOOL の戻り値の型、UINT 型の最初のパラメーター (コントロール ID の場合)、およびイベントのパラメーターに一致する追加のパラメーター型*が必要です (vtsParams*を参照)。 この関数は、イベントが処理されたことを示す TRUE を返す必要があります。それ以外の場合は FALSE。

*vtsパラム*<br/>
イベントのパラメーターの型を指定する**VTS_** 定数のシーケンス。 最初の定数は、コントロール ID に対してVTS_I4型にする必要があります。 これらは、DISP_FUNCTIONなどのディスパッチ マップ エントリで使用される定数と同じです。

### <a name="remarks"></a>解説

*vtsParams*引数は **、VTS_** 定数の値の一覧をスペースで区切ったものです。 これらの値のうち 1 つ以上がスペースで区切られ (コンマではなく) 関数のパラメーター・リストが指定されます。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

は、短整数の後に BOOL が続くリストを指定します。

**VTS_** 定数の一覧については[、「EVENT_CUSTOM」](event-maps.md#event_custom)を参照してください。

### <a name="example"></a>例

次の例は、3 つのコントロール (IDC_MYCTRL3 を通じてIDC_MYCTRL1) に実装された MouseDown イベントのイベント ハンドラーを示しています。 イベント ハンドラ関数`OnRangeMouseDown`は、ダイアログ クラス ( `CMyDlg`) のヘッダー ファイルで次のように宣言されます。

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

以下のコードは、ダイアログ クラスの実装ファイルで定義されています。

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="on_event_reflect"></a><a name="on_event_reflect"></a>ON_EVENT_REFLECT

ON_EVENT_REFLECT マクロは、OLE コントロールのラッパー クラスのイベント シンク マップで使用すると、コントロールのコンテナーによって処理される前に、コントロールによって発生するイベントを受け取ります。

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベント シンク マップが属するクラス。

*Dispid*<br/>
コントロールによって発生したイベントのディスパッチ ID。

*プンハンドラー*<br/>
イベントを処理するメンバー関数へのポインター。 この関数には、イベントのパラメータに一致する BOOL 戻り値の型とパラメータ型*が必要です (vtsParams*を参照)。 この関数は、イベントが処理されたことを示す TRUE を返す必要があります。それ以外の場合は FALSE。

*vtsパラム*<br/>
イベントのパラメーターの型を指定する**VTS_** 定数のシーケンス。 これらは、DISP_FUNCTIONなどのディスパッチ マップ エントリで使用される定数と同じです。

### <a name="remarks"></a>解説

*vtsParams*引数は **、VTS_** 定数の値の一覧をスペースで区切ったものです。

これらの値のうち 1 つ以上がスペースで区切られ (コンマではなく) 関数のパラメーター・リストが指定されます。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

は、短整数の後に BOOL が続くリストを指定します。

**VTS_** 定数の一覧については[、「EVENT_CUSTOM」](event-maps.md#event_custom)を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="on_propnotify"></a><a name="on_propnotify"></a>ON_PROPNOTIFY

ON_PROPNOTIFY マクロを使用して、OLE コントロールからのプロパティ通知を処理するためのイベント シンク マップ エントリを定義します。

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベント シンク マップが属するクラス。

*id*<br/>
OLE コントロールのコントロール ID。

*Dispid*<br/>
通知に関連するプロパティのディスパッチ ID。

*依頼*<br/>
このプロパティの通知を処理する`OnRequestEdit`メンバー関数へのポインター。 この関数には、BOOL 戻り値の型と**BOOL**<strong>\*</strong>パラメータが必要です。 この関数は、プロパティを変更できるようにパラメータを TRUE に設定し、FALSE を使用して許可しないようにする必要があります。 この関数は、通知が処理されたことを示す TRUE を返す必要があります。それ以外の場合は FALSE。

*変更された*<br/>
このプロパティの通知を処理する`OnChanged`メンバー関数へのポインター。 関数には、BOOL 戻り値の型と UINT パラメーターを指定する必要があります。 この関数は、通知が処理されたことを示すために TRUE を返す必要があります。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*vtsParams*引数は **、VTS_** 定数の値の一覧をスペースで区切ったものです。 これらの値のうち 1 つ以上がスペースで区切られ (コンマではなく) 関数のパラメーター・リストが指定されます。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

は、短整数の後に BOOL が続くリストを指定します。

**VTS_** 定数の一覧については[、「EVENT_CUSTOM」](event-maps.md#event_custom)を参照してください。

## <a name="on_propnotify_range"></a><a name="on_propnotify_range"></a>ON_PROPNOTIFY_RANGE

ON_PROPNOTIFY_RANGE マクロを使用して、コントロール ID が連続した ID 範囲内にある OLE コントロールからのプロパティ通知を処理するためのイベント シンク マップ エントリを定義します。

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベント シンク マップが属するクラス。

*id最初*<br/>
範囲内の最初の OLE コントロールのコントロール ID。

*idLast*<br/>
範囲内の最後の OLE コントロールのコントロール ID。

*Dispid*<br/>
通知に関連するプロパティのディスパッチ ID。

*依頼*<br/>
このプロパティの通知を処理する`OnRequestEdit`メンバー関数へのポインター。 この関数には、戻`BOOL`り値の`UINT`型`BOOL*`とパラメーターが必要です。 この関数は、プロパティを変更できるようにパラメータを TRUE に設定し、FALSE を使用して許可しないようにする必要があります。 この関数は、通知が処理されたことを示すために TRUE を返す必要があります。それ以外の場合は FALSE。

*変更された*<br/>
このプロパティの通知を処理する`OnChanged`メンバー関数へのポインター。 関数には、戻り`BOOL`値の型と`UINT`パラメーターが必要です。 この関数は、通知が処理されたことを示すために TRUE を返す必要があります。それ以外の場合は FALSE。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="on_propnotify_reflect"></a><a name="on_propnotify_reflect"></a>ON_PROPNOTIFY_REFLECT

ole コントロールのラッパー クラスのイベント シンク マップで使用されるON_PROPNOTIFY_REFLECT マクロは、コントロールのコンテナーによって処理される前に、コントロールから送信されるプロパティ通知を受け取ります。

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベント シンク マップが属するクラス。

*Dispid*<br/>
通知に関連するプロパティのディスパッチ ID。

*依頼*<br/>
このプロパティの通知を処理する`OnRequestEdit`メンバー関数へのポインター。 この関数には、BOOL 戻り値の型と**BOOL**<strong>\*</strong>パラメータが必要です。 この関数は、プロパティを変更できるようにパラメータを TRUE に設定し、FALSE を使用して許可しないようにする必要があります。 この関数は、通知が処理されたことを示す TRUE を返す必要があります。それ以外の場合は FALSE。

*変更された*<br/>
このプロパティの通知を処理する`OnChanged`メンバー関数へのポインター。 関数には BOOL 戻り値の型が必要で、パラメーターは指定できません。 この関数は、通知が処理されたことを示す TRUE を返す必要があります。それ以外の場合は FALSE。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
