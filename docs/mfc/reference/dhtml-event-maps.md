---
title: DHTML イベント マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 224a0c9b837763574c53e8464885f02ec5413971
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="dhtml-event-maps"></a>DHTML イベント マップ
DHTML イベントの処理には、次のマクロを使用できます。  
  
## <a name="dhtml-event-map-macros"></a>DHTML イベント マップ マクロ  
 DHTML イベントを処理する次のマクロを使用できます[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-クラスを派生します。  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML イベント マップの開始をマークします。|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML イベント マップの開始をマークします。|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML イベント マップを宣言します。|  
|[DHTML_EVENT](#dhtml_event)|1 つの HTML 要素のドキュメント レベルのイベントを処理するために使用します。|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX コントロールによって発生するイベントを処理するために使用します。|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|特定の CSS クラスとすべての HTML 要素のドキュメント レベルのイベントを処理するために使用します。|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|要素レベルでイベントを処理するために使用します。|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|処理に使用する、 **onblur** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|処理に使用する、 `onchange` HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|処理に使用する、 **onclick** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|処理に使用する、 **ondataavailable** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|処理に使用する、 **ondblclick** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|処理に使用する、 **ondragstart** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|処理に使用する、**詳細について**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|処理に使用する、 **onfocus** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|処理に使用する、 `onhelp` HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|処理に使用する、 **onkeydown** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|処理に使用する、 **onkeypress** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|処理に使用する、 **onkeyup** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|処理に使用する、 **onmousedown** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|処理に使用する、 `onmousemove` HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|処理に使用する、**タグ**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|処理に使用する、 **onmouseover** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|処理に使用する、 **onmouseup** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|処理に使用する、 **onresize** HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|処理に使用する、**詳細**HTML 要素からのイベントです。|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|処理に使用する、 **onselectstart** HTML 要素からのイベントです。|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|特定の HTML タグを持つすべての要素のドキュメント レベルのイベントを処理するために使用します。|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML イベント マップの最後をマークします。|  
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML イベント マップの最後をマークします。 |
  
## <a name="url-event-map-macros"></a>URL イベント マップ マクロ  
 DHTML イベントを処理する次のマクロを使用できます[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)-クラスを派生します。  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|マルチページ DHTML と URL のイベント マップの開始をマークします。|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|埋め込み DHTML イベント マップの開始をマークします。|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL イベント エントリ マップの開始をマークします。|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|マルチページ DHTML と URL イベントのマップを宣言します。|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|マルチページ DHTML と URL イベント マップの最後をマークします。|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|埋め込み DHTML イベント マップの最後をマークします。|  
|[END_URL_ENTRIES](#end_url_entries)|URL イベント エントリ マップの最後をマークします。|  
|[URL_EVENT_ENTRY](#url_event_entry)|マルチページ ダイアログは、内のページには、URL または HTML リソースをマップします。|  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP  
 DHTML イベント マップによって識別されるクラスのソース ファイルに配置した場合の開始をマーク`className`です。  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 DHTML イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)を含めると、 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)そのクラス定義内でのマクロです。  
  
### <a name="remarks"></a>コメント  
 DHTML イベント マップ クラスに追加情報を提供する**CDHtmlDialog** HTML 要素や、クラスのハンドラー関数に web ページでの ActiveX コントロールによって発生したイベントをルーティングに使用できます。  
  
 場所、`BEGIN_DHTML_EVENT_MAP`クラスの実装 (.cpp) ファイル内のマクロが続く`DHTML_EVENT`を処理するクラスは、イベントのマクロ (たとえば、 `DHTML_EVENT_ONMOUSEOVER` mouseover イベント)。 使用して、 [END_DHTML_EVENT_MAP](#end_dhtml_event_map)マクロ イベント マップの終わりをマークします。 これらのマクロは、次の関数を実装します。  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE  
 DHTML イベント マップのクラス定義内の開始をマーク`className`です。  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 DHTML イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)を含めると、 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)そのクラス定義内でのマクロです。  
  
### <a name="remarks"></a>コメント  
 DHTML イベント マップ クラスに追加情報を提供する**CDHtmlDialog** HTML 要素や、クラスのハンドラー関数に web ページでの ActiveX コントロールによって発生したイベントをルーティングに使用できます。  
  
 場所、`BEGIN_DHTML_EVENT_MAP`クラスの定義 (.h) ファイル内のマクロが続く`DHTML_EVENT`を処理するクラスは、イベントのマクロ (たとえば、 `DHTML_EVENT_ONMOUSEOVER` mouseover イベントの)。 使用して、 [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)マクロ イベント マップの終わりをマークします。 これらのマクロは、次の関数を実装します。  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  

  
##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP  
 DHTML イベント マップ、クラス定義で宣言しています。  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 このマクロの定義で使用するのには、 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-クラスを派生します。  
  
 使用して[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)または[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)マップを実装します。  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)次の関数を宣言します。  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event"></a>  DHTML_EVENT  
 によって識別されるイベントを (ドキュメント レベルで処理`dispid`で識別される HTML 要素で考案された`elemName`です。  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 イベントを処理するための DISPID です。  
  
 `elemName`  
 `LPCWSTR` 、イベントをソースとしての HTML 要素の ID を保持または**NULL**ドキュメント イベントを処理します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL  
 によって識別されるイベントを処理する`dispid`で指定された ActiveX コントロールによって発生した`controlName`です。  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 処理するイベントのディスパッチ ID。  
  
 `controlName`  
 `LPCWSTR`イベントを発生させるコントロールの HTML ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS  
 によって識別されるイベントを (ドキュメント レベルで処理`dispid`で識別される CSS クラスを使用した任意の HTML 要素で考案された`elemName`です。  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 処理するイベントのディスパッチ ID。  
  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の CSS クラスを保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT  
 処理 (で識別される要素に`elemName`) によって識別されるイベント`dispid`です。  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 処理するイベントのディスパッチ ID。  
  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
 イベントのソースがによって識別される要素になる場合、このマクロを使用すると、非イベントを処理すると、`elemName`です。  
  
 要素が識別される場合、このマクロを使用すると、バブルのイベントを処理すると、`elemName`イベントのソースができない可能性があります (ソースのいずれかの要素に含まれる可能性があります`elemName`)。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR  
 (レベル要素) を処理、 **onblur**イベント。 これは、バブルではありません。  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE  
 (レベル要素) を処理、`onchange`イベント。 これは、バブルではありません。  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK  
 (ドキュメント レベルで処理、 **onclick**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE  
 (ドキュメント レベルで処理、 **ondataavailable**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK  
 (ドキュメント レベルで処理、 **ondblclick**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART  
 (ドキュメント レベルで処理、 **ondragstart**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE  
 (ドキュメント レベルで処理、**詳細について**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS  
 (レベル要素) を処理、 **onfocus**イベント。 これは、バブルではありません。  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP  
 (ドキュメント レベルで処理、`onhelp`で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN  
 (ドキュメント レベルで処理、 **onkeydown**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS  
 (ドキュメント レベルで処理、 **onkeypress**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP  
 (ドキュメント レベルで処理、 **onkeyup**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN  
 (ドキュメント レベルで処理、 **onmousedown**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE  
 (ドキュメント レベルで処理、`onmousemove`で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT  
 (ドキュメント レベルで処理、**タグ**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER  
 (ドキュメント レベルで処理、 **onmouseover**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP  
 (ドキュメント レベルで処理、 **onmouseup**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE  
 (レベル要素) を処理、 **onresize**イベント。 これは、バブルではありません。  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT  
 (ドキュメント レベルで処理、**詳細**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART  
 (ドキュメント レベルで処理、 **onselectstart**で識別される HTML 要素によってイベントの発生元`elemName`です。  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `elemName`  
 `LPCWSTR`イベントをソースとしての HTML 要素の ID を保持します。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG  
 によって識別されるイベントを (ドキュメント レベルで処理`dispid`で識別される HTML タグを持つ任意の HTML 要素で考案された`elemName`です。  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>パラメーター  
 `dispid`  
 処理するイベントのディスパッチ ID。  
  
 `elemName`  
 イベントをソースとしての HTML 要素の HTML タグ。  
  
 `memberFxn`  
 イベントのハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するエントリを追加、 [DHTML イベント マップ](#begin_dhtml_event_map_inline)クラスにします。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="end_dhtml_event_map"></a>  END_DHTML_EVENT_MAP  
 DHTML イベント マップの最後をマークします。  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>コメント  
 組み合わせて使用する必要があります[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="begin_dhtml_url_event_map"></a>  BEGIN_DHTML_URL_EVENT_MAP  
 マルチページ ダイアログは、DHTML と URL のイベント マップの定義を開始します。  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>コメント  
 Put`BEGIN_DHTML_URL_EVENT_MAP`の実装ファイルに、[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)-クラスを派生します。 それに続く[DHTML イベント マップの埋め込み](#begin_embed_dhtml_event_map)と[URL エントリ](#begin_url_entries)として閉じます[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)です。 含める、 [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)クラス定義内でのマクロです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP  
 マルチページ ダイアログは、埋め込み DHTML イベント マップの定義を開始します。  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)です。 埋め込みの DHTML イベント マップは、内部になければなりません、 [DHTML と URL のイベント マップ](#begin_dhtml_url_event_map))。  
  
 *mapName*  
 イベント マップを持つページを指定します。 これに対応*mapName*で、 [URL_EVENT_ENTRY](#url_event_entry)マクロが実際には、URL または HTML リソースを定義します。  
  
### <a name="remarks"></a>コメント  
 DHTML イベントを発生させることができますは、複数の HTML ページを DHTML マルチページ ダイアログは、構成するため、マップの埋め込みイベントがイベントをページ単位のハンドラーにマップに使用されます。  
  
 DHTML と URL のイベント マップ内の埋め込みイベント マップから成る、`BEGIN_EMBED_DHTML_EVENT_MAP`マクロが続く[DHTML_EVENT](#dhtml_event)マクロと[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)マクロです。  
  
 各埋め込みイベント マップでは、対応する必要があります[URL イベント エントリ](#url_event_entry)にマップする*mapName* (で指定された`BEGIN_EMBED_DHTML_EVENT_MAP`) URL または HTML リソース。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES  
 マルチページ ダイアログは、URL イベント エントリ マップの定義を開始します。  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 URL のイベント エントリのマップを含むクラスの名前です。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)です。 内部 URL イベント エントリのマップがある必要があります、 [DHTML と URL のイベント マップ](#begin_dhtml_url_event_map))。  
  
### <a name="remarks"></a>コメント  
 Url または HTML にマップする URL エントリがイベントを使用ため DHTML マルチページ ダイアログは、複数の HTML ページで構成され、対応するリソース[DHTML イベント マップの埋め込み](#begin_embed_dhtml_event_map)です。 Put`URL_EVENT_ENTRY`間でのマクロ`BEGIN_URL_ENTRIES`と[END_URL_ENTRIES](#end_url_entries)マクロです。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP  
 クラス定義のイベント マップ DHTML と URL を宣言します。  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>コメント  
 このマクロの定義で使用するのには、[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)-クラスを派生します。  
  
 DHTML と URL イベント マップに含まれる[DHTML イベント マップの埋め込み](#begin_embed_dhtml_event_map)と[URL イベント エントリ](#begin_url_entries)DHTML イベントをページ単位のハンドラーにマップします。 使用して[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)マップを実装します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP  
 DHTML と URL のイベント マップの最後をマークします。  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 イベント マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)です。 これと一致する必要があります`className`、対応する[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)マクロです。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP  
 埋め込み DHTML イベント マップの最後をマークします。  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="end_url_entries"></a>  END_URL_ENTRIES  
 URL イベント エントリ マップの最後をマークします。  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  
  
##  <a name="url_event_entry"></a>  URL_EVENT_ENTRY  
 マルチページ ダイアログは、内のページには、URL または HTML リソースをマップします。  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 URL のイベント エントリのマップを含むクラスの名前です。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/cmultipagedhtmldialog-class.md)です。 内部 URL イベント エントリのマップがある必要があります、 [DHTML と URL のイベント マップ](#begin_dhtml_url_event_map))。  
  
 *Url*  
 ページの URL または HTML リソースです。  
  
 *mapName*  
 URL がページを指定*url*です。 これに対応*mapName*で、 [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)マクロをこのページからのイベントをマップします。  
  
### <a name="remarks"></a>コメント  
 ページが、HTML リソースの場合*url*リソースの ID 番号 (つまり、「123」、いない 123 または ID_HTMLRES1) の文字列形式にする必要があります。  
  
 ページ識別子*mapName*は、任意のシンボルを使用してリンクに埋め込まれた URL イベント エントリのマップを DHTML イベント マップします。 DHTML と URL イベント マップへのスコープで制限されることはできます。  
  
### <a name="example"></a>例  
 例を参照してください[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)です。  

  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdhtml.h  

##  <a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE
DHTML イベント マップの最後をマークします。  
   
### <a name="syntax"></a>構文    
```
END_DHTML_EVENT_MAP_INLINE( )    
```  
   
### <a name="remarks"></a>コメント  
 組み合わせて使用する必要があります[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdhtml.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
