---
description: '詳細情報: DHTML イベントマップ'
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
ms.openlocfilehash: b9df8f1aa59472de033943efd28f5c688c61e706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220124"
---
# <a name="dhtml-event-maps"></a>DHTML イベント マップ

次のマクロは、DHTML イベントを処理するために使用できます。

## <a name="dhtml-event-map-macros"></a>DHTML イベントマップマクロ

次のマクロは、 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)派生クラスで DHTML イベントを処理するために使用できます。

|名前|説明|
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML イベントマップの開始をマークします。|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML イベントマップの開始をマークします。|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML イベントマップを宣言します。|
|[DHTML_EVENT](#dhtml_event)|1つの HTML 要素について、ドキュメントレベルでイベントを処理するために使用されます。|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX コントロールによって発生するイベントを処理するために使用されます。|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|特定の CSS クラスを持つすべての HTML 要素について、ドキュメントレベルでイベントを処理するために使用されます。|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|要素レベルでイベントを処理するために使用されます。|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|HTML 要素からのイベントを処理するために使用され `onafterupdate` ます。|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|HTML 要素からのイベントを処理するために使用され `onbeforeupdate` ます。|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|HTML 要素からのイベントを処理するために使用され `onblur` ます。|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|HTML 要素からのイベントを処理するために使用され `onchange` ます。|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|HTML 要素からのイベントを処理するために使用され `onclick` ます。|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|HTML 要素からのイベントを処理するために使用され `ondataavailable` ます。|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|HTML 要素からのイベントを処理するために使用され `ondatasetchanged` ます。|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|HTML 要素からのイベントを処理するために使用され `ondatasetcomplete` ます。|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|HTML 要素からのイベントを処理するために使用され `ondblclick` ます。|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|HTML 要素からのイベントを処理するために使用され `ondragstart` ます。|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|HTML 要素からのイベントを処理するために使用され `onerrorupdate` ます。|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|HTML 要素からのイベントを処理するために使用され `onfilterchange` ます。|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|HTML 要素からのイベントを処理するために使用され `onfocus` ます。|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|HTML 要素からのイベントを処理するために使用され `onhelp` ます。|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|HTML 要素からのイベントを処理するために使用され `onkeydown` ます。|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|HTML 要素からのイベントを処理するために使用され `onkeypress` ます。|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|HTML 要素からのイベントを処理するために使用され `onkeyup` ます。|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|HTML 要素からのイベントを処理するために使用され `onmousedown` ます。|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|HTML 要素からのイベントを処理するために使用され `onmousemove` ます。|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|HTML 要素からのイベントを処理するために使用され `onmouseout` ます。|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|HTML 要素からのイベントを処理するために使用され `onmouseover` ます。|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|HTML 要素からのイベントを処理するために使用され `onmouseup` ます。|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|HTML 要素からのイベントを処理するために使用され `onresize` ます。|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|HTML 要素からのイベントを処理するために使用され `onrowenter` ます。|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|HTML 要素からのイベントを処理するために使用され `onrowexit` ます。|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|HTML 要素からのイベントを処理するために使用され `onselectstart` ます。|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|特定の HTML タグを持つすべての要素について、ドキュメントレベルでイベントを処理するために使用されます。|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML イベントマップの終了をマークします。|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|DHTML イベントマップの終了をマークします。 |

## <a name="url-event-map-macros"></a>URL イベントマップマクロ

次のマクロは、 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生クラスで DHTML イベントを処理するために使用できます。

|名前|説明|
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|マルチページ DHTML と URL イベントマップの開始をマークします。|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|埋め込み DHTML イベントマップの開始をマークします。|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL イベントエントリマップの開始をマークします。|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|マルチページ DHTML と URL イベントマップを宣言します。|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|マルチページ DHTML と URL イベントマップの末尾をマークします。|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|埋め込み DHTML イベントマップの終了をマークします。|
|[END_URL_ENTRIES](#end_url_entries)|URL イベントエントリマップの終了をマークします。|
|[URL_EVENT_ENTRY](#url_event_entry)|URL または HTML リソースを複数ページのダイアログのページにマップします。|

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a> BEGIN_DHTML_EVENT_MAP

によって識別されるクラスのソースファイルに配置されたときに、DHTML イベントマップの開始をマークし `className` ます。

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
DHTML イベントマップを格納しているクラスの名前。 このクラスは、 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) から直接または間接的に派生し、そのクラス定義内に [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) マクロを含める必要があります。

### <a name="remarks"></a>解説

クラスに DHTML イベントマップを追加して、 `CDHtmlDialog` web ページ内の HTML 要素または ActiveX コントロールによって起動されたイベントをクラス内のハンドラー関数にルーティングするために使用できる情報をに提供します。

クラスの実装 (.cpp) ファイルに BEGIN_DHTML_EVENT_MAP マクロを配置した後、クラスが処理するイベントのマクロを DHTML_EVENT します (たとえば、マウスを置いたイベントの DHTML_EVENT_ONMOUSEOVER)。 [END_DHTML_EVENT_MAP](#end_dhtml_event_map)マクロを使用して、イベントマップの終了をマークします。 これらのマクロは、次の関数を実装します。

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a> BEGIN_DHTML_EVENT_MAP_INLINE

クラス *名* のクラス定義内で、DHTML イベントマップの開始をマークします。

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
DHTML イベントマップを格納しているクラスの名前。 このクラスは、 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) から直接または間接的に派生し、そのクラス定義内に [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) マクロを含める必要があります。

### <a name="remarks"></a>解説

クラスに DHTML イベントマップを追加して、 `CDHtmlDialog` web ページ内の HTML 要素または ActiveX コントロールによって起動されたイベントをクラス内のハンドラー関数にルーティングするために使用できる情報をに提供します。

クラスの定義 (.h) ファイルに BEGIN_DHTML_EVENT_MAP マクロを配置した後、クラスが処理するイベントのマクロを DHTML_EVENT します (たとえば、マウスを置いたイベントの DHTML_EVENT_ONMOUSEOVER)。 [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)マクロを使用して、イベントマップの終了をマークします。 これらのマクロは、次の関数を実装します。

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a> DECLARE_DHTML_EVENT_MAP

クラス定義で DHTML イベントマップを宣言します。

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>解説

このマクロは、 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)派生クラスの定義で使用されます。

マップを実装するには、 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) または [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) を使用します。

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) は、次の関数を宣言します。

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event"></a><a name="dhtml_event"></a> DHTML_EVENT

要素 *名* で識別される HTML 要素によって発行された *dispid* によって識別されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
処理するイベントの DISPID。

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。ドキュメントイベントを処理する場合は NULL。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a> DHTML_EVENT_AXCONTROL

*ControlName* によって識別される ActiveX コントロールによって起動される *dispid* によって識別されるイベントを処理します。

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
処理するイベントのディスパッチ ID。

*controlName*<br/>
イベントを発生させているコントロールの HTML ID を保持している LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a> DHTML_EVENT_CLASS

要素によって識別されたイベントを (ドキュメントレベルで) ハンドルします。このイベントは、要素 *名* によって識別される CSS クラスを持つ HTML 要素によっ *て生成さ* れます。

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
処理するイベントのディスパッチ ID。

*elemName*<br/>
イベントの発生源となった HTML 要素の CSS クラスを保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a> DHTML_EVENT_ELEMENT

(要素 *名* によって識別される要素で) *dispid* によって識別されるイベントを処理します。

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
処理するイベントのディスパッチ ID。

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

このマクロを使用してバブルイベント以外のイベントを処理する場合、イベントのソースは、要素 *名* によって識別される要素になります。

このマクロを使用してバブルイベントを処理する場合は、要素がイベントのソースとして指定されていない *可能性があり* ます (ソースは、要素 *名* に含まれる任意の要素にすることができます)。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a> DHTML_EVENT_ONAFTERUPDATE

`onafterupdate`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a> DHTML_EVENT_ONBEFOREUPDATE

`onbeforeupdate`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a> DHTML_EVENT_ONBLUR

イベントを (要素レベルで) ハンドルし `onblur` ます。 これは、バブルイベントではありません。

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a> DHTML_EVENT_ONCHANGE

イベントを (要素レベルで) ハンドルし `onchange` ます。 これは、バブルイベントではありません。

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a> DHTML_EVENT_ONCLICK

`onclick`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a> DHTML_EVENT_ONDATAAVAILABLE

`ondataavailable`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a> DHTML_EVENT_ONDATASETCHANGED

`ondatasetchanged`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a> DHTML_EVENT_ONDATASETCOMPLETE

`ondatasetcomplete`によって識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドル `elemName` します。

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a> DHTML_EVENT_ONDBLCLICK

`ondblclick`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a> DHTML_EVENT_ONDRAGSTART

`ondragstart`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a> DHTML_EVENT_ONERRORUPDATE

`onerrorupdate`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a> DHTML_EVENT_ONFILTERCHANGE

`onfilterchange`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a> DHTML_EVENT_ONFOCUS

イベントを (要素レベルで) ハンドルし `onfocus` ます。 これは、バブルイベントではありません。

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a> DHTML_EVENT_ONHELP

`onhelp`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a> DHTML_EVENT_ONKEYDOWN

`onkeydown`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a> DHTML_EVENT_ONKEYPRESS

`onkeypress`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a> DHTML_EVENT_ONKEYUP

`onkeyup`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a> DHTML_EVENT_ONMOUSEDOWN

`onmousedown`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a> DHTML_EVENT_ONMOUSEMOVE

`onmousemove`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a> DHTML_EVENT_ONMOUSEOUT

`onmouseout`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a> DHTML_EVENT_ONMOUSEOVER

`onmouseover`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a> DHTML_EVENT_ONMOUSEUP

`onmouseup`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a> DHTML_EVENT_ONRESIZE

イベントを (要素レベルで) ハンドルし `onresize` ます。 これは、バブルイベントではありません。

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a> DHTML_EVENT_ONROWENTER

`onrowenter`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a> DHTML_EVENT_ONROWEXIT

`onrowexit`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a> DHTML_EVENT_ONSELECTSTART

`onselectstart`要素 *名* で識別される HTML 要素によって生成されるイベントを、(ドキュメントレベルで) ハンドルします。

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>パラメーター

*elemName*<br/>
イベントの発生源である HTML 要素の ID を保持する LPCWSTR。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a> DHTML_EVENT_TAG

によって識別されるイベント (ドキュメントレベル) は、 `dispid` 要素 *名* によって識別される html タグを持つ html 要素によって生成されます。

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*dispid*<br/>
処理するイベントのディスパッチ ID。

*elemName*<br/>
イベントの発生源となった HTML 要素の HTML タグ。

*memberFxn*<br/>
イベントのハンドラー関数。

### <a name="remarks"></a>解説

このマクロを使用して、クラスの [DHTML イベントマップ](#begin_dhtml_event_map_inline) にエントリを追加します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a> END_DHTML_EVENT_MAP

DHTML イベントマップの終了をマークします。

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>解説

[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)と組み合わせて使用する必要があります。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a> BEGIN_DHTML_URL_EVENT_MAP

マルチページダイアログで DHTML および URL イベントマップの定義を開始します。

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>解説

[CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生クラスの実装ファイルに BEGIN_DHTML_URL_EVENT_MAP を配置します。 [埋め込み DHTML イベントマップ](#begin_embed_dhtml_event_map)と[URL エントリ](#begin_url_entries)を使用してそれを実行し、 [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)で閉じます。 クラス定義内に [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) マクロを含めます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a> BEGIN_EMBED_DHTML_EVENT_MAP

複数ページのダイアログで、埋め込み DHTML イベントマップの定義を開始します。

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
イベントマップを格納しているクラスの名前。 このクラスは、 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)から直接または間接的に派生する必要があります。 埋め込み DHTML イベントマップは、 [dhtml および URL イベントマップ](#begin_dhtml_url_event_map)内にある必要があります。

*mapName*<br/>
イベントマップがあるページを指定します。 これは、URL または HTML リソースを実際に定義する [URL_EVENT_ENTRY](#url_event_entry)マクロ内の *mapName* と一致します。

### <a name="remarks"></a>解説

マルチページ DHTML ダイアログは複数の HTML ページで構成されており、それぞれが DHTML イベントを発生させる可能性があるため、埋め込みイベントマップを使用して、イベントをページ単位でハンドラーにマップします。

DHTML および URL イベントマップ内の埋め込みイベントマップは、BEGIN_EMBED_DHTML_EVENT_MAP マクロと、それに続くマクロと[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)マクロ[DHTML_EVENT](#dhtml_event)で構成されます。

各埋め込みイベントマップには、 *mapName* (BEGIN_EMBED_DHTML_EVENT_MAP で指定) を url または HTML リソースにマップするための対応する [url イベントエントリ](#url_event_entry)が必要です。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a> BEGIN_URL_ENTRIES

マルチページダイアログで URL イベントエントリマップの定義を開始します。

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
URL イベントエントリマップを格納しているクラスの名前。 このクラスは、 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)から直接または間接的に派生する必要があります。 URL イベントエントリマップは、 [DHTML および url イベントマップ](#begin_dhtml_url_event_map)内にある必要があります。

### <a name="remarks"></a>解説

マルチページ DHTML ダイアログは複数の HTML ページで構成されているため、URL イベントエントリを使用して、url または HTML リソースを対応する [埋め込み DHTML イベントマップ](#begin_embed_dhtml_event_map)にマップします。 マクロ URL_EVENT_ENTRY BEGIN_URL_ENTRIES と [END_URL_ENTRIES](#end_url_entries) マクロの間に配置します。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a> DECLARE_DHTML_URL_EVENT_MAP

クラス定義で DHTML および URL イベントマップを宣言します。

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>解説

このマクロは、 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)派生クラスの定義で使用されます。

Dhtml および URL イベントマップには、dhtml イベントマップと[url イベントエントリ](#begin_url_entries)[が含まれ](#begin_embed_dhtml_event_map)ており、dhtml イベントをページ単位でハンドラーにマップします。 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)を使用してマップを実装します。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a> END_DHTML_URL_EVENT_MAP

DHTML および URL イベントマップの終了をマークします。

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
イベントマップを格納しているクラスの名前。 このクラスは、 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)から直接または間接的に派生する必要があります。 これは、対応する [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)マクロの *className* と一致している必要があります。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a> END_EMBED_DHTML_EVENT_MAP

埋め込み DHTML イベントマップの終了をマークします。

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="end_url_entries"></a><a name="end_url_entries"></a> END_URL_ENTRIES

URL イベントエントリマップの終了をマークします。

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="url_event_entry"></a><a name="url_event_entry"></a> URL_EVENT_ENTRY

URL または HTML リソースを複数ページのダイアログのページにマップします。

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>パラメーター

*className*<br/>
URL イベントエントリマップを格納しているクラスの名前。 このクラスは、 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)から直接または間接的に派生する必要があります。 URL イベントエントリマップは、 [DHTML および url イベントマップ](#begin_dhtml_url_event_map)内にある必要があります。

*url*<br/>
ページの URL または HTML リソース。

*mapName*<br/>
Url が *url* であるページを指定します。 これは、このページのイベントをマップする [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)マクロの *mapName* と一致します。

### <a name="remarks"></a>解説

ページが HTML リソースの場合、 *url* はリソースの ID 番号の文字列形式である必要があります (つまり、123または ID_HTMLRES1 ではなく、"123")。

ページ識別子 *mapName* は、埋め込み DHTML イベントマップを URL イベントエントリマップにリンクするために使用される任意のシンボルです。 スコープは、DHTML および URL イベントマップに限定されます。

### <a name="example"></a>例

[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)の例を参照してください。

### <a name="requirements"></a>要件

  **ヘッダー** afxdhtml

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a> END_DHTML_EVENT_MAP_INLINE

DHTML イベントマップの終了をマークします。

### <a name="syntax"></a>構文

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>解説

[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)と組み合わせて使用する必要があります。

### <a name="requirements"></a>要件

**ヘッダー:** afxdhtml

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)
