---
title: イベント シンク マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ababaab7324d712457f6411ed731274ea361084b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373929"
---
# <a name="event-sink-maps"></a>イベント シンク マップ
埋め込み OLE コントロールは、イベントを発生させる、コントロールのコンテナーは、マップと呼ばれる、"イベント シンク、"MFC によって提供される機構を使用して、イベントを受信します。 このイベント シンク マップは、それぞれ特定のイベントと、これらのイベントのパラメーターのハンドラー関数を指定します。 イベント シンク マップの詳細については、記事を参照してください。 [ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)です。  
  
### <a name="event-sink-maps"></a>イベント シンク マップ  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|イベント シンク マップの定義を開始します。|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|イベント シンク マップを宣言します。|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|イベント シンク マップの定義を終了します。|  
|[ON_EVENT](#on_event)|特定のイベントのイベント ハンドラーを定義します。|  
|[ON_EVENT_RANGE](#on_event_range)|OLE コントロールのセットから発生した特定のイベントのイベント ハンドラーを定義します。|  
|[ON_EVENT_REFLECT](#on_event_reflect)|コントロールのコンテナーによって処理される前に、コントロールによって発生したイベントを受信します。|  
|[ON_PROPNOTIFY](#on_propnotify)|OLE コントロールからプロパティの通知を処理するためのハンドラーを定義します。|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE コントロールのセットからのプロパティの通知を処理するためのハンドラーを定義します。|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|プロパティによって送信された通知コントロールがコントロールのコンテナーによって処理される前に受け取ります。|  
  
##  <a name="begin_eventsink_map"></a>  BEGIN_EVENTSINK_MAP  
 イベント シンク マップの定義を開始します。  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 あるイベント シンク マップ コントロール クラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`です。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイル、起動するとイベント シンク マップ、`BEGIN_EVENTSINK_MAP`マクロ、各イベントについて通知を受けるは、マクロのエントリを追加し、完了とイベント シンク マップ、`END_EVENTSINK_MAP`マクロです。  
  
 イベント シンク マップと OLE コントロールのコンテナーの詳細については、記事を参照してください。 [ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="declare_eventsink_map"></a>  DECLARE_EVENTSINK_MAP  
 OLE コンテナーのコンテナーに通知するイベントを指定するイベント シンク マップを提供できます。  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 使用して、`DECLARE_EVENTSINK_MAP`クラスの宣言の最後にマクロです。 次に、します。クラスのメンバーを定義する CPP ファイルの機能を使用して、`BEGIN_EVENTSINK_MAP`マクロの通知を受信するイベントの各マクロ エントリと`END_EVENTSINK_MAP`イベント シンクのリストの末尾を宣言するマクロです。  
  
 イベント シンク マップの詳細については、記事を参照してください。 [ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="end_eventsink_map"></a>  END_EVENTSINK_MAP  
 イベント シンク マップの定義を終了します。  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_event"></a>  ON_EVENT  
 使用して、 `ON_EVENT` OLE コントロールによって発生したイベントのイベント ハンドラー関数を定義するマクロです。  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `id`  
 OLE コントロールのコントロール ID。  
  
 `dispid`  
 コントロールによって発生したイベントのディスパッチ ID。  
  
 `pfnHandler`  
 イベントを処理するメンバー関数へのポインター。 この関数が必要です、 **BOOL**型、およびイベントのパラメーターに一致するパラメーターの型を返す (を参照してください`vtsParams`)。 関数が返す必要があります**TRUE**イベントがそれ以外の処理を示すために**FALSE**です。  
  
 `vtsParams`  
 一連の**vts _** イベントのパラメーターの型を指定する定数。 これらは、ようなディスパッチ マップ エントリで使用される定数を同じ`DISP_FUNCTION`です。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _** 定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続けて短整数を含む一覧を示す、 **BOOL**です。  
  
 一覧については、 **vts _** 定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_event_range"></a>  ON_EVENT_RANGE  
 使用して、 `ON_EVENT_RANGE` Id の連続した範囲内のコントロール ID を持つ任意の OLE コントロールによって発生したイベントのイベント ハンドラー関数を定義するマクロです。  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `idFirst`  
 範囲の最初の OLE コントロールのコントロール ID。  
  
 `idLast`  
 範囲の最後の OLE コントロールのコントロール ID。  
  
 `dispid`  
 コントロールによって発生したイベントのディスパッチ ID。  
  
 `pfnHandler`  
 イベントを処理するメンバー関数へのポインター。 この関数が必要です、 **BOOL**型の最初のパラメーターの型を返す**UINT** (用、コントロールの ID)、およびイベントのパラメーターに一致する追加のパラメーターの型 (を参照してください`vtsParams`)。 関数が返す必要があります**TRUE**イベントがそれ以外の処理を示すために**FALSE**です。  
  
 `vtsParams`  
 一連の**vts _** イベントのパラメーターの型を指定する定数。 最初の定数が型でなければなりません**VTS_I4**コントロールの id これらは、ようなディスパッチ マップ エントリで使用される定数を同じ`DISP_FUNCTION`です。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _** 定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続けて短整数を含む一覧を示す、 **BOOL**です。  
  
 一覧については、 **vts _** 定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)です。  
  
### <a name="example"></a>例  
 次の例では、3 つのコントロールの実装、MouseDown イベントのイベント ハンドラー (`IDC_MYCTRL1`を通じて`IDC_MYCTRL3`)。 イベント ハンドラー関数`OnRangeMouseDown`、ダイアログ クラスのヘッダー ファイルで宣言されて ( `CMyDlg`) として。  
  
 [!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 次のコードは、ダイアログ クラスの実装ファイルで定義されます。  
  
 [!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_event_reflect"></a>  ON_EVENT_REFLECT  
 `ON_EVENT_REFLECT`イベント シンク マップ OLE コントロールのラッパー クラスを使用する場合、マクロがコントロールのコンテナーによって処理される前に、コントロールによって発生したイベントを受信します。  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 dispid  
 コントロールによって発生したイベントのディスパッチ ID。  
  
 `pfnHandler`  
 イベントを処理するメンバー関数へのポインター。 この関数が必要です、 **BOOL**型と、イベントのパラメーターに一致するパラメーターの型を返す (を参照してください`vtsParams`)。 関数が返す必要があります**TRUE**イベントがそれ以外の処理を示すために**FALSE**です。  
  
 `vtsParams`  
 一連の**vts _** イベントのパラメーターの型を指定する定数。 これらは、ようなディスパッチ マップ エントリで使用される定数を同じ`DISP_FUNCTION`です。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _** 定数。  
  
 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続けて短整数を含む一覧を示す、 **BOOL**です。  
  
 一覧については、 **vts _** 定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_propnotify"></a>  ON_PROPNOTIFY  
 使用して、 `ON_PROPNOTIFY` OLE コントロールからプロパティの通知を処理するためには、イベント シンク マップ エントリを定義するマクロです。  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `id`  
 OLE コントロールのコントロール ID。  
  
 `dispid`  
 通知に関連するプロパティのディスパッチ ID。  
  
 `pfnRequest`  
 処理するメンバー関数へのポインター、 **OnRequestEdit**このプロパティに通知します。 この関数が必要です、 **BOOL**型を返すと、 **BOOL\*** パラメーター。 この関数はパラメーターを設定する必要があります**TRUE**を変更するプロパティを許可して**FALSE**を許可しないようにします。 関数が返す必要があります**TRUE**通知されたそれ以外の処理を示す**FALSE**です。  
  
 `pfnChanged`  
 処理するメンバー関数へのポインター、 **OnChanged**このプロパティに通知します。 関数が必要、 **BOOL**型を返すと、 **UINT**パラメーター。 関数が返す必要があります**TRUE**通知がそれ以外の処理されたことを示す**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `vtsParams`引数がスペースで区切られた一連の値から、 **vts _** 定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 続けて短整数を含む一覧を示す、 **BOOL**です。  
  
 一覧については、 **vts _** 定数を参照してください[EVENT_CUSTOM](event-maps.md#event_custom)です。  
  
##  <a name="on_propnotify_range"></a>  ON_PROPNOTIFY_RANGE  
 使用して、`ON_PROPNOTIFY_RANGE`マクロを連続した Id の範囲内のコントロール ID を持つ任意の OLE コントロールからプロパティの通知を処理するためのイベント シンク マップ エントリを定義します。  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `idFirst`  
 範囲の最初の OLE コントロールのコントロール ID。  
  
 `idLast`  
 範囲の最後の OLE コントロールのコントロール ID。  
  
 `dispid`  
 通知に関連するプロパティのディスパッチ ID。  
  
 `pfnRequest`  
 処理するメンバー関数へのポインター、 **OnRequestEdit**このプロパティに通知します。 この関数が必要です、 **BOOL**型を返すと**UINT**と**BOOL\*** パラメーター。 関数がパラメーターを設定する必要があります**TRUE**を変更するプロパティを許可して**FALSE**を許可しないようにします。 関数が返す必要があります**TRUE**通知がそれ以外の処理されたことを示す**FALSE**です。  
  
 `pfnChanged`  
 処理するメンバー関数へのポインター、 **OnChanged**このプロパティに通知します。 関数が必要、 **BOOL**型を返すと、 **UINT**パラメーター。 関数が返す必要があります**TRUE**通知がそれ以外の処理されたことを示す**FALSE**です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
  
##  <a name="on_propnotify_reflect"></a>  ON_PROPNOTIFY_REFLECT  
 `ON_PROPNOTIFY_REFLECT`イベント シンク マップ OLE コントロールのラッパー クラスを使用する場合、マクロがコントロールのコンテナーによって処理される前に、コントロールによって送信されるプロパティの通知を受け取ります。  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 このイベント シンク マップが所属するクラスです。  
  
 `dispid`  
 通知に関連するプロパティのディスパッチ ID。  
  
 `pfnRequest`  
 処理するメンバー関数へのポインター、 **OnRequestEdit**このプロパティに通知します。 この関数が必要です、 **BOOL**型を返すと、 **BOOL\*** パラメーター。 この関数はパラメーターを設定する必要があります**TRUE**を変更するプロパティを許可して**FALSE**を許可しないようにします。 関数が返す必要があります**TRUE**通知されたそれ以外の処理を示す**FALSE**です。  
  
 `pfnChanged`  
 処理するメンバー関数へのポインター、 **OnChanged**このプロパティに通知します。 関数が必要、 **BOOL**型およびパラメーターを返します。 関数が返す必要があります**TRUE**通知されたそれ以外の処理を示す**FALSE**です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdisp.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
