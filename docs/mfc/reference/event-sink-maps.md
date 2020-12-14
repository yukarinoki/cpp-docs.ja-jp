---
description: 詳細については、「イベントシンクマップ」を参照してください。
title: イベント シンク マップ
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
ms.openlocfilehash: df18cdbba849ff0c8d7be5b038f997b6cc5df849
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219838"
---
# <a name="event-sink-maps"></a>イベント シンク マップ

埋め込み OLE コントロールがイベントを発生させると、コントロールのコンテナーは、MFC によって提供される "イベントシンクマップ" と呼ばれる機構を使用してイベントを受け取ります。 このイベントシンクマップは、特定のイベントのハンドラー関数、およびそれらのイベントのパラメーターを指定します。 イベントシンクマップの詳細については、「 [ActiveX コントロールコンテナー](../../mfc/activex-control-containers.md)」を参照してください。

### <a name="event-sink-maps"></a>イベント シンク マップ

|名前|説明|
|-|-|
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|イベントシンクマップの定義を開始します。|
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|イベントシンクマップを宣言します。|
|[END_EVENTSINK_MAP](#end_eventsink_map)|イベントシンクマップの定義を終了します。|
|[ON_EVENT](#on_event)|特定のイベントのイベントハンドラーを定義します。|
|[ON_EVENT_RANGE](#on_event_range)|一連の OLE コントロールから発生した特定のイベントのイベントハンドラーを定義します。|
|[ON_EVENT_REFLECT](#on_event_reflect)|コントロールのコンテナーによって処理される前に、コントロールによって発生するイベントを受け取ります。|
|[ON_PROPNOTIFY](#on_propnotify)|OLE コントロールからのプロパティ通知を処理するためのハンドラーを定義します。|
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|一連の OLE コントロールからのプロパティ通知を処理するためのハンドラーを定義します。|
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|コントロールがコンテナーによって処理される前に、コントロールによって送信されたプロパティ通知を受信します。|

## <a name="begin_eventsink_map"></a><a name="begin_eventsink_map"></a> BEGIN_EVENTSINK_MAP

イベントシンクマップの定義を開始します。

```
BEGIN_EVENTSINK_MAP(theClass, baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
イベントシンクがこのをマップするコントロールクラスの名前を指定します。

*baseClass*<br/>
*クラス* の基底クラスの名前を指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、BEGIN_EVENTSINK_MAP マクロを使用してイベントシンクマップを開始し、通知されるイベントごとにマクロエントリを追加して、END_EVENTSINK_MAP マクロを使用してイベントシンクマップを完了します。

イベントシンクマップと OLE コントロールコンテナーの詳細については、「 [ActiveX コントロールコンテナー](../../mfc/activex-control-containers.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="declare_eventsink_map"></a><a name="declare_eventsink_map"></a> DECLARE_EVENTSINK_MAP

OLE コンテナーは、イベントシンクマップを提供して、コンテナーに通知するイベントを指定できます。

```
DECLARE_EVENTSINK_MAP()
```

### <a name="remarks"></a>解説

クラス宣言の最後に DECLARE_EVENTSINK_MAP マクロを使用します。 次に、でを行います。クラスのメンバー関数を定義する CPP ファイル、BEGIN_EVENTSINK_MAP マクロ、通知される各イベントのマクロエントリ、およびイベントシンクリストの末尾を宣言するための END_EVENTSINK_MAP マクロを使用します。

イベントシンクマップの詳細については、「 [ActiveX コントロールコンテナー](../../mfc/activex-control-containers.md)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxwin.h

## <a name="end_eventsink_map"></a><a name="end_eventsink_map"></a> END_EVENTSINK_MAP

イベントシンクマップの定義を終了します。

```
END_EVENTSINK_MAP()
```

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="on_event"></a><a name="on_event"></a> ON_EVENT

OLE コントロールによって発生するイベントのイベントハンドラー関数を定義するには、ON_EVENT マクロを使用します。

```
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベントシンクマップが属するクラス。

*id*<br/>
OLE コントロールのコントロール ID。

*dispid*<br/>
コントロールによって発生したイベントのディスパッチ ID。

*pfnHandler*<br/>
イベントを処理するメンバー関数へのポインター。 この関数は、ブール型の戻り値の型と、イベントのパラメーターに一致するパラメーターの型を持つ必要があります (「 *Vtsparc ams*」を参照してください)。 関数は、イベントが処理されたことを示すために TRUE を返す必要があります。それ以外の場合は FALSE。

*Vtsparc*<br/>
イベントのパラメーターの型を指定する一連の **VTS_** 定数。 これらは、DISP_FUNCTION などのディスパッチマップエントリで使用されるものと同じ定数です。

### <a name="remarks"></a>解説

*Vtsparc ams* 引数は、 **VTS_** 定数の空白で区切られた値のリストです。 これらの値のうち1つ以上 (コンマではない) で区切られた関数のパラメーターリストを指定します。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

短整数の後に BOOL を含むリストを指定します。

**VTS_** 定数の一覧については、「 [EVENT_CUSTOM](event-maps.md#event_custom)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="on_event_range"></a><a name="on_event_range"></a> ON_EVENT_RANGE

ON_EVENT_RANGE マクロを使用して、連続する Id の範囲内にコントロール ID を持つ OLE コントロールによって発生するイベントのイベントハンドラー関数を定義します。

```
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベントシンクマップが属するクラス。

*idFirst*<br/>
範囲内の最初の OLE コントロールのコントロール ID。

*idLast*<br/>
範囲内の最後の OLE コントロールのコントロール ID。

*dispid*<br/>
コントロールによって発生したイベントのディスパッチ ID。

*pfnHandler*<br/>
イベントを処理するメンバー関数へのポインター。 この関数は、ブール型の戻り値の型、UINT 型の最初のパラメーター (コントロール ID の場合)、およびイベントのパラメーターに一致する追加のパラメーターの型を持つ必要があります (「 *Vtsparc ams*」を参照してください)。 関数は、イベントが処理されたことを示すために TRUE を返す必要があります。それ以外の場合は FALSE。

*Vtsparc*<br/>
イベントのパラメーターの型を指定する一連の **VTS_** 定数。 最初の定数は、コントロール ID の VTS_I4 型である必要があります。 これらは、DISP_FUNCTION などのディスパッチマップエントリで使用されるものと同じ定数です。

### <a name="remarks"></a>解説

*Vtsparc ams* 引数は、 **VTS_** 定数の空白で区切られた値のリストです。 これらの値のうち1つ以上 (コンマではない) で区切られた関数のパラメーターリストを指定します。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

短整数の後に BOOL を含むリストを指定します。

**VTS_** 定数の一覧については、「 [EVENT_CUSTOM](event-maps.md#event_custom)」を参照してください。

### <a name="example"></a>例

次の例は、MouseDown イベントのイベントハンドラーを示しています。これは、3つのコントロール (IDC_MYCTRL1 IDC_MYCTRL3) に対して実装されています。 イベントハンドラー関数は、 `OnRangeMouseDown` ダイアログクラス () のヘッダーファイルで次のように宣言され `CMyDlg` ています。

[!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]

次のコードは、ダイアログクラスの実装ファイルで定義されています。

[!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="on_event_reflect"></a><a name="on_event_reflect"></a> ON_EVENT_REFLECT

ON_EVENT_REFLECT マクロは、OLE コントロールのラッパークラスのイベントシンクマップで使用されると、コントロールによって発生するイベントを、コントロールのコンテナーによって処理される前に受信します。

```
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベントシンクマップが属するクラス。

*dispid*<br/>
コントロールによって発生したイベントのディスパッチ ID。

*pfnHandler*<br/>
イベントを処理するメンバー関数へのポインター。 この関数の戻り値の型とパラメーターの型は、イベントのパラメーターに一致している必要があります (「 *Vtsparc ams*」を参照してください)。 関数は、イベントが処理されたことを示すために TRUE を返す必要があります。それ以外の場合は FALSE。

*Vtsparc*<br/>
イベントのパラメーターの型を指定する一連の **VTS_** 定数。 これらは、DISP_FUNCTION などのディスパッチマップエントリで使用されるものと同じ定数です。

### <a name="remarks"></a>解説

*Vtsparc ams* 引数は、 **VTS_** 定数の空白で区切られた値のリストです。

これらの値のうち1つ以上 (コンマではない) で区切られた関数のパラメーターリストを指定します。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

短整数の後に BOOL を含むリストを指定します。

**VTS_** 定数の一覧については、「 [EVENT_CUSTOM](event-maps.md#event_custom)」を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="on_propnotify"></a><a name="on_propnotify"></a> ON_PROPNOTIFY

OLE コントロールからのプロパティ通知を処理するためのイベントシンクマップエントリを定義するには、ON_PROPNOTIFY マクロを使用します。

```
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベントシンクマップが属するクラス。

*id*<br/>
OLE コントロールのコントロール ID。

*dispid*<br/>
通知に関連するプロパティのディスパッチ ID。

*pfnRequest*<br/>
このプロパティの通知を処理するメンバー関数へ `OnRequestEdit` のポインター。 この関数は、ブール型の戻り値の型と **ブール** 型パラメーターを持つ必要があり <strong>\*</strong> ます。 この関数では、パラメーターを TRUE に設定して、プロパティを変更できるようにし、FALSE を許可しないようにする必要があります。 関数は、通知が処理されたことを示すために TRUE を返します。それ以外の場合は FALSE。

*pfnChanged*<br/>
このプロパティの通知を処理するメンバー関数へ `OnChanged` のポインター。 関数は、ブール型の戻り値の型と UINT パラメーターを持つ必要があります。 この関数は、通知が処理されたことを示すために TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*Vtsparc ams* 引数は、 **VTS_** 定数の空白で区切られた値のリストです。 これらの値のうち1つ以上 (コンマではない) で区切られた関数のパラメーターリストを指定します。 次に例を示します。

[!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]

短整数の後に BOOL を含むリストを指定します。

**VTS_** 定数の一覧については、「 [EVENT_CUSTOM](event-maps.md#event_custom)」を参照してください。

## <a name="on_propnotify_range"></a><a name="on_propnotify_range"></a> ON_PROPNOTIFY_RANGE

ON_PROPNOTIFY_RANGE マクロを使用して、連続する Id の範囲内でコントロール ID を持つ任意の OLE コントロールからのプロパティ通知を処理するためのイベントシンクマップエントリを定義します。

```

ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベントシンクマップが属するクラス。

*idFirst*<br/>
範囲内の最初の OLE コントロールのコントロール ID。

*idLast*<br/>
範囲内の最後の OLE コントロールのコントロール ID。

*dispid*<br/>
通知に関連するプロパティのディスパッチ ID。

*pfnRequest*<br/>
このプロパティの通知を処理するメンバー関数へ `OnRequestEdit` のポインター。 この関数は、戻り値の型とパラメーターを持つ必要があり `BOOL` `UINT` `BOOL*` ます。 この関数では、パラメーターを TRUE に設定して、プロパティを変更できるようにし、FALSE を許可しないようにする必要があります。 この関数は、通知が処理されたことを示すために TRUE を返します。それ以外の場合は FALSE。

*pfnChanged*<br/>
このプロパティの通知を処理するメンバー関数へ `OnChanged` のポインター。 関数は、 `BOOL` 戻り値の型とパラメーターを持つ必要があり `UINT` ます。 この関数は、通知が処理されたことを示すために TRUE を返します。それ以外の場合は FALSE。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="on_propnotify_reflect"></a><a name="on_propnotify_reflect"></a> ON_PROPNOTIFY_REFLECT

ON_PROPNOTIFY_REFLECT マクロは、OLE コントロールのラッパークラスのイベントシンクマップで使用されると、コントロールのコンテナーによって処理される前に、コントロールによって送信されるプロパティ通知を受け取ります。

```

ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
このイベントシンクマップが属するクラス。

*dispid*<br/>
通知に関連するプロパティのディスパッチ ID。

*pfnRequest*<br/>
このプロパティの通知を処理するメンバー関数へ `OnRequestEdit` のポインター。 この関数は、ブール型の戻り値の型と **ブール** 型パラメーターを持つ必要があり <strong>\*</strong> ます。 この関数では、パラメーターを TRUE に設定して、プロパティを変更できるようにし、FALSE を許可しないようにする必要があります。 関数は、通知が処理されたことを示すために TRUE を返します。それ以外の場合は FALSE。

*pfnChanged*<br/>
このプロパティの通知を処理するメンバー関数へ `OnChanged` のポインター。 関数にはブール型の戻り値を指定し、パラメーターを指定することはできません。 関数は、通知が処理されたことを示すために TRUE を返します。それ以外の場合は FALSE。

### <a name="requirements"></a>要件

  **ヘッダー** afxdisp.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
