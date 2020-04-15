---
title: DHTML イベント マップ
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: 30c755b2901374cffab3ce91d0683811ef6624b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365805"
---
# <a name="dhtml-event-maps"></a>DHTML イベント マップ

次のマクロを使用して DHTML イベントを処理できます。

## <a name="dhtml-event-map-macros"></a>DHTML イベント マップ マクロ

次のマクロを使用して[、CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)派生クラスの DHTML イベントを処理できます。

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML イベント マップの開始位置を示します。|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML イベント マップの開始位置を示します。|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML イベント マップを宣言します。|
|[DHTML_EVENT](#dhtml_event)|1 つの HTML 要素のドキュメント レベルでイベントを処理するために使用します。|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX コントロールによって発生したイベントを処理するために使用します。|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|特定の CSS クラスを持つすべての HTML 要素のドキュメント レベルでイベントを処理するために使用します。|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|要素レベルでイベントを処理するために使用します。|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|HTML 要素から`onafterupdate`イベントを処理するために使用します。|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|HTML 要素から`onbeforeupdate`イベントを処理するために使用します。|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|HTML 要素から`onblur`イベントを処理するために使用します。|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|HTML 要素から`onchange`イベントを処理するために使用します。|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|HTML 要素から`onclick`イベントを処理するために使用します。|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|HTML 要素から`ondataavailable`イベントを処理するために使用します。|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|HTML 要素から`ondatasetchanged`イベントを処理するために使用します。|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|HTML 要素から`ondatasetcomplete`イベントを処理するために使用します。|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|HTML 要素から`ondblclick`イベントを処理するために使用します。|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|HTML 要素から`ondragstart`イベントを処理するために使用します。|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|HTML 要素から`onerrorupdate`イベントを処理するために使用します。|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|HTML 要素から`onfilterchange`イベントを処理するために使用します。|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|HTML 要素から`onfocus`イベントを処理するために使用します。|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|HTML 要素から`onhelp`イベントを処理するために使用します。|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|HTML 要素から`onkeydown`イベントを処理するために使用します。|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|HTML 要素から`onkeypress`イベントを処理するために使用します。|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|HTML 要素から`onkeyup`イベントを処理するために使用します。|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|HTML 要素から`onmousedown`イベントを処理するために使用します。|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|HTML 要素から`onmousemove`イベントを処理するために使用します。|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|HTML 要素から`onmouseout`イベントを処理するために使用します。|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|HTML 要素から`onmouseover`イベントを処理するために使用します。|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|HTML 要素から`onmouseup`イベントを処理するために使用します。|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|HTML 要素から`onresize`イベントを処理するために使用します。|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|HTML 要素から`onrowenter`イベントを処理するために使用します。|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|HTML 要素から`onrowexit`イベントを処理するために使用します。|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|HTML 要素から`onselectstart`イベントを処理するために使用します。|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|特定の HTML タグを持つすべての要素について、ドキュメント レベルでイベントを処理するために使用します。|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML イベント マップの末尾をマークします。|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML イベント マップの末尾をマークします。 |

## <a name="url-event-map-macros"></a>URL イベント マップ マクロ

次のマクロを使用して[、派生](../../mfc/reference/cmultipagedhtmldialog-class.md)クラスの DHTML イベントを処理できます。

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|マルチページ DHTML および URL イベント マップの開始を示します。|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|埋め込まれた DHTML イベント マップの開始位置を示します。|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL イベントエントリマップの開始位置を示します。|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|複数ページの DHTML と URL イベント マップを宣言します。|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|マルチページ DHTML と URL イベント マップの末尾を示します。|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|埋め込まれた DHTML イベント マップの末尾をマークします。|
|[END_URL_ENTRIES](#end_url_entries)|URL イベントエントリマップの終わりを示します。|
|[URL_EVENT_ENTRY](#url_event_entry)|URL または HTML リソースを複数ページのダイアログ内のページにマップします。|

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP

で`className`識別されるクラスのソース ファイルに配置された場合、DHTML イベント マップの先頭をマークします。

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
DHTML イベント マップを含むクラスの名前。 このクラスは[、CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)から直接または間接的に派生し、クラス定義内に[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)マクロを含める必要があります。

### <a name="remarks"></a>解説

クラスに DHTML イベント マップを追加して、WEB ページ内の HTML 要素または ActiveX コントロールによって発生`CDHtmlDialog`するイベントをクラス内のハンドラー関数にルーティングするために使用できる情報を提供します。

クラスの実装 (.cpp) ファイルにBEGIN_DHTML_EVENT_MAPマクロを配置し、そのクラスが処理するイベントに対してDHTML_EVENTマクロを配置します (マウスオーバー イベントのDHTML_EVENT_ONMOUSEOVERなど)。 [END_DHTML_EVENT_MAP](#end_dhtml_event_map)マクロを使用して、イベント マップの終了をマークします。 これらのマクロは、次の関数を実装します。

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE

クラス定義内の DHTML イベント マップの先頭を*示*します。

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
DHTML イベント マップを含むクラスの名前。 このクラスは[、CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)から直接または間接的に派生し、クラス定義内に[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)マクロを含める必要があります。

### <a name="remarks"></a>解説

クラスに DHTML イベント マップを追加して、WEB ページ内の HTML 要素または ActiveX コントロールによって発生`CDHtmlDialog`するイベントをクラス内のハンドラー関数にルーティングするために使用できる情報を提供します。

BEGIN_DHTML_EVENT_MAPマクロをクラスの定義 (.h) ファイルに置き、そのクラスが処理するイベントのDHTML_EVENTマクロ (たとえば、マウスオーバー イベントのDHTML_EVENT_ONMOUSEOVER) を指定します。 [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)マクロを使用して、イベント マップの終了をマークします。 これらのマクロは、次の関数を実装します。

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP

クラス定義で DHTML イベント マップを宣言します。

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>解説

このマクロは[、CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)派生クラスの定義で使用されます。

[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)または[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)を使用してマップを実装します。

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)は、次の関数を宣言します。

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event"></a><a name="dhtml_event"></a>DHTML_EVENT

(ドキュメント レベルで) *dispid*によって識別されるイベントを*処理*します。

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
処理するイベントの DISPID。

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR、またはドキュメント イベントを処理する NULL。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL

*controlName*によって識別される ActiveX コントロールによって発生した*dispid*によって識別されるイベントを処理します。

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
処理するイベントのディスパッチ ID。

*コントロール名*<br/>
イベントを発生するコントロールの HTML ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS

(ドキュメント レベルで) *dispid*によって識別されるイベントを*処理*します。

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
処理するイベントのディスパッチ ID。

*elemName*<br/>
イベントをソースとする HTML 要素の CSS クラスを保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT

*(ememName*で識別される要素) で *、dispid*によって識別されるイベントを処理します。

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
処理するイベントのディスパッチ ID。

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

このマクロを使用して非バブル イベントを処理する場合、イベントのソースは*elemName*で識別される要素になります。

このマクロを使用してバブル イベントを処理する場合 *、elemName*によって識別される要素がイベントのソースでない可能性があります (ソースは*elemName*に含まれる要素である可能性があります)。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE

`onafterupdate` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE

`onbeforeupdate` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR

イベントを (要素レベルで)`onblur`処理します。 これは非バブルイベントです。

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE

イベントを (要素レベルで)`onchange`処理します。 これは非バブルイベントです。

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK

`onclick` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE

`ondataavailable` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED

`ondatasetchanged` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE

によって識別される HTML 要素によって`ondatasetcomplete`発生したイベントをドキュメント レベルで`elemName`処理します。

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK

`ondblclick` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART

`ondragstart` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE

`onerrorupdate` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE

`onfilterchange` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS

イベントを (要素レベルで)`onfocus`処理します。 これは非バブルイベントです。

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP

`onhelp` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN

`onkeydown` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS

`onkeypress` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP

`onkeyup` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN

`onmousedown` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE

`onmousemove` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT

`onmouseout` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER

`onmouseover` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP

`onmouseup` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE

イベントを (要素レベルで)`onresize`処理します。 これは非バブルイベントです。

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER

`onrowenter` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT

`onrowexit` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART

`onselectstart` *elemName*で識別される HTML 要素によって発生したイベントをドキュメント レベルで処理します。

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントをソースする HTML 要素の ID を保持する LPCWSTR です。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG

*elemName*で識別される HTML タグ`dispid`を持つ HTML 要素によって発生したイベントを (ドキュメント レベルで) 処理します。

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*Dispid*<br/>
処理するイベントのディスパッチ ID。

*elemName*<br/>
イベントをソースする HTML 要素の HTML タグ。

*メンバーFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの[DHTML イベント マップ](#begin_dhtml_event_map_inline)にエントリを追加します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP

DHTML イベント マップの末尾をマークします。

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>解説

[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)と組み合わせて使用する必要があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP

複数ページのダイアログで DHTML と URL イベント マップの定義を開始します。

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>解説

BEGIN_DHTML_URL_EVENT_MAPを[、派生](../../mfc/reference/cmultipagedhtmldialog-class.md)クラスの実装ファイルに配置します。 DHTML イベント マップと[URL エントリ](#begin_url_entries)を[埋め込んで](#begin_embed_dhtml_event_map)その後[、END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)で閉じます。 クラス定義内に[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)マクロを含めます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP

マルチページ ダイアログで埋め込まれた DHTML イベント マップの定義を開始します。

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
イベント マップを含むクラスの名前。 このクラスは、直接または間接的に[派生](../../mfc/reference/cmultipagedhtmldialog-class.md)する必要があります。 埋め込まれた DHTML イベント マップは[、DHTML および URL イベント マップ](#begin_dhtml_url_event_map)内になければなりません。

*マップ名*<br/>
イベント マップが表示されるページを指定します。 これは、実際に URL または HTML リソースを定義する[URL_EVENT_ENTRY](#url_event_entry)マクロ内の*mapName*と一致します。

### <a name="remarks"></a>解説

複数ページの DHTML ダイアログは複数の HTML ページで構成され、各ページが DHTML イベントを発生させることができるため、埋め込みイベント マップは、ページごとにイベントをハンドラーにマップするために使用されます。

DHTML および URL イベント マップ内の埋め込みイベント マップは、BEGIN_EMBED_DHTML_EVENT_MAP マクロとそれに続く[DHTML_EVENT](#dhtml_event)マクロと[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)マクロで構成されます。

埋め込まれた各イベント マップでは、対応する*mapName* [URL イベント エントリ](#url_event_entry)が必要 BEGIN_EMBED_DHTML_EVENT_MAPです。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES

複数ページのダイアログで URL イベント入力マップの定義を開始します。

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
URL イベントエントリマップを含むクラスの名前。 このクラスは、直接または間接的に[派生](../../mfc/reference/cmultipagedhtmldialog-class.md)する必要があります。 URL イベントエントリマップは[、DHTML および URL イベントマップ](#begin_dhtml_url_event_map)内になければなりません。

### <a name="remarks"></a>解説

複数ページの DHTML ダイアログは複数の HTML ページで構成されているため、URL イベント エントリを使用して、URL または HTML リソースを対応する[埋め込み DHTML イベント マップ](#begin_embed_dhtml_event_map)にマップします。 BEGIN_URL_ENTRIESマクロと[END_URL_ENTRIES](#end_url_entries)マクロの間にURL_EVENT_ENTRYマクロを配置します。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP

クラス定義で DHTML と URL イベント マップを宣言します。

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>解説

このマクロは、[派生](../../mfc/reference/cmultipagedhtmldialog-class.md)クラスの定義で使用されます。

DHTML および URL イベント マップには[、埋め込まれた DHTML イベント マップ](#begin_embed_dhtml_event_map)と[URL イベント エントリ](#begin_url_entries)が含まれ、DHTML イベントをページ単位でハンドラーにマップします。 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)を使用してマップを実装します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP

DHTML と URL イベント マップの末尾を示します。

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
イベント マップを含むクラスの名前。 このクラスは、直接または間接的に[派生](../../mfc/reference/cmultipagedhtmldialog-class.md)する必要があります。 これは、対応する[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)マクロの*className*と一致する必要があります。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP

埋め込まれた DHTML イベント マップの末尾をマークします。

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="end_url_entries"></a><a name="end_url_entries"></a>END_URL_ENTRIES

URL イベントエントリマップの終わりを示します。

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="url_event_entry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY

URL または HTML リソースを複数ページのダイアログ内のページにマップします。

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>パラメーター

*Classname*<br/>
URL イベントエントリマップを含むクラスの名前。 このクラスは、直接または間接的に[派生](../../mfc/reference/cmultipagedhtmldialog-class.md)する必要があります。 URL イベントエントリマップは[、DHTML および URL イベントマップ](#begin_dhtml_url_event_map)内になければなりません。

*url*<br/>
ページの URL または HTML リソース。

*マップ名*<br/>
URL が*url*であるページを指定します。 これは、このページのイベントをマップする[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)マクロ内の*mapName*と一致します。

### <a name="remarks"></a>解説

ページが HTML リソースの場合 *、url*はリソースの ID 番号 (123 または ID_HTMLRES1 ではなく"123" という文字列表現である必要があります)。

ページ識別子*mapName*は、埋め込まれた DHTML イベント マップを URL イベント エントリ マップにリンクするために使用される任意のシンボルです。 DHTML と URL イベント マップに限定されます。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdhtml.h

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

DHTML イベント マップの末尾をマークします。

### <a name="syntax"></a>構文

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>解説

[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)と組み合わせて使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdhtml.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)
