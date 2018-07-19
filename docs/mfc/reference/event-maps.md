---
title: イベント マップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4522b9ea2f336f5ac88f5444edc0c7df16b5bc6
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122390"
---
# <a name="event-maps"></a>イベント マップ

コントロール コンテナー (キーストローク、マウスのクリック、コントロールの状態の変更など) 何らかのアクション (コントロールの開発者によって決まります) が発生したに通知することを希望するたびにイベントを発生させる関数を呼び出します。 この関数は、コントロール コンテナー、関連するイベントを発生させることによっていくつかの重要なアクションが発生したことを通知します。

Microsoft Foundation Class ライブラリには、イベントを発生させるために最適化されたプログラミング モデルが用意されています。 このモデルでは「イベント マップ」を使用する機能が特定のコントロールのイベントを発生させるかを指定します。 イベント マップには、イベントごとに 1 つのマクロが含まれています。 たとえば、イベント マップを発生させるストックの Click イベントが次のようになります。

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

`EVENT_STOCK_CLICK`マクロは、コントロールがマウスを検出するたびにイベントをクリック、株価を発生することを示します。 その他のストック イベントの詳細な一覧については、記事を参照してください。 [ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)です。 マクロは、カスタム イベントを示すために使用できます。

イベント マップ マクロは重要ですが、一般に挿入しないに直接できます。 これはため、[プロパティ] ウィンドウがイベントを発生させる機能を関連付けるイベントを使用する場合、ソース ファイルでイベント マップ エントリが自動的に作成されます。 いつでも編集またはイベント マップ エントリを追加する [プロパティ] ウィンドウを使用することができます。

イベント マップをサポートするためには、MFC には、次のマクロが用意されています。

## <a name="event-map-macros"></a>イベント マップ マクロ

### <a name="event-map-declaration-and-demarcation"></a>イベント マップの宣言と定義

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|イベント マップがクラスでイベントを発生させる関数 (クラス宣言で使用する必要があります) にイベントをマップに使用されることを宣言します。|
|[BEGIN_EVENT_MAP](#begin_event_map)|イベント マップ (クラスの実装で使用する必要があります) の定義を開始します。|
|[END_EVENT_MAP](#end_event_map)|イベント マップ (クラスの実装で使用する必要があります) の定義を終了します。|

### <a name="event-mapping-macros"></a>イベント マップ マクロ

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|指定したイベントを発生させるどのイベントを発生させる関数を示します。|
|[EVENT_CUSTOM_ID](#event_custom_id)|イベントを発生させる関数が、指定したディスパッチ ID を使用して、指定したイベントを発生させることを示します。|

### <a name="message-mapping-macros"></a>メッセージ割り当てマクロ

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE コントロールによって処理するカスタム動詞を示します。|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE コントロールの標準的な動詞マッピングを上書きします。|

##  <a name="declare_event_map"></a>  DECLARE_EVENT_MAP

各`COleControl`-プログラム内の派生クラスは、コントロールは発生させるイベントを指定するためのイベント マップを提供できます。

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

クラスの宣言の終了時 DECLARE_EVENT_MAP マクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルを使用 BEGIN_EVENT_MAP マクロ マクロ エントリの各コントロールのイベントと END_EVENT_MAP マクロのイベントのリストの末尾を宣言します。

イベント マップの詳細については、記事を参照してください。 [ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)です。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="begin_event_map"></a>  BEGIN_EVENT_MAP

イベント マップの定義を開始します。

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*  
イベント マップを持つコントロール クラスの名前を指定します。

*baseClass*  
基本クラスの名前を指定*クラス*です。

### <a name="remarks"></a>Remarks

クラスのメンバー関数を定義する実装 (.cpp) ファイル、BEGIN_EVENT_MAP マクロでのイベント マップの開始、イベントの各マクロ エントリを追加し、END_EVENT_MAP マクロを持つイベント マップを完了します。

イベント マップと BEGIN_EVENT_MAP マクロの詳細については、記事を参照してください。 [ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)です。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

##  <a name="end_event_map"></a>  END_EVENT_MAP

END_EVENT_MAP マクロを使用すると、イベント マップの定義を終了します。

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="event_custom"></a>  EVENT_CUSTOM

カスタム イベントのイベント マップ エントリを定義します。

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*pszName*  
イベントの名前です。

*pfnFire*  
イベント発生関数の名前。

*vtsParams*  
関数のパラメーター リストを指定する 1 つまたは複数の定数のスペースで区切られた一覧です。

### <a name="remarks"></a>Remarks

*VtsParams*パラメーターはスペースで区切られた一連の値から、`VTS_`定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB を表す 32 ビット整数を含むリストへのポインターを続けて、値の色を指定します、 `IFontDisp` OLE フォント オブジェクトのインターフェイスです。

`VTS_`定数とその意味は次のようには。

|シンボル|パラメーターの型|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|通貨|
|VTS_DATE|DATE|
|VTS_BSTR|**const** __char\*__|
|VTS_DISPATCH|LPDISPATCH|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|HANDLE|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_OPTEXCLUSIVE|OLE_OPTEXCLUSIVE|
|VTS_PICTURE|`IPictureDisp*`|
|VTS_TRISTATE|OLE_TRISTATE|
|VTS_XPOS_PIXELS|OLE_XPOS_PIXELS|
|VTS_YPOS_PIXELS|OLE_YPOS_PIXELS|
|VTS_XSIZE_PIXELS|OLE_XSIZE_PIXELS|
|VTS_YSIZE_PIXELS|OLE_YSIZE_PIXELS|
|TS_XPOS_HIMETRIC|OLE_XPOS_HIMETRIC|
|VTS_YPOS_HIMETRIC|OLE_YPOS_HIMETRIC|
|VTS_XSIZE_HIMETRIC|OLE_XSIZE_HIMETRIC|
|VTS_YSIZE_HIMETRIC|OLE_YSIZE_HIMETRIC|

> [!NOTE]
> 追加のバリアント定数は、すべてのバリアント型、VTS_FONT と VTS_PICTURE、を除き、variant データ定数へのポインターを提供する定義されています。 これらの定数の名前、`VTS_Pconstantname`規則。 たとえば、VTS_PCOLOR は VTS_COLOR 定数へのポインターです。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="event_custom_id"></a>  EVENT_CUSTOM_ID

関数で指定されたディスパッチ ID に属するカスタム イベントを発生させるイベントを定義*dispid*です。

```cpp
EVENT_CUSTOM_ID(
  pszName,
  dispid,
  pfnFire,
  vtsParams)
```

### <a name="parameters"></a>パラメーター

*pszName*  
イベントの名前です。

*dispid*  
イベントを発生させるときに、コントロールで使用するディスパッチ ID。

*pfnFire*  
イベント発生関数の名前。

*vtsParams*  
パラメーターの変数の一覧は、イベントが発生したときに、コントロールのコンテナーに渡されます。

### <a name="remarks"></a>Remarks

*VtsParams*引数がスペースで区切られた一連の値から、`VTS_`定数。 これらの値のないコンマ、スペースで区切られた 1 つ以上の関数のパラメーター リストを指定します。 例えば:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB を表す 32 ビット整数を含むリストへのポインターを続けて、値の色を指定します、 `IFontDisp` OLE フォント オブジェクトのインターフェイスです。

一覧については、`VTS_`定数を参照してください[EVENT_CUSTOM](#event_custom)です。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="on_oleverb"></a>  ON_OLEVERB

このマクロは、カスタム動詞をコントロールの特定のメンバー関数にマップするメッセージ マップ エントリを定義します。

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*idsVerbName*動詞の名前の文字列リソースの ID。

*memberFxn*  
動詞が呼び出されたときに、フレームワークによって呼び出される関数。

### <a name="remarks"></a>Remarks

リソース エディターは、文字列テーブルに追加されるカスタム動詞名を作成して使用できます。

関数のプロトタイプ*memberFxn*は。

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

値、 *lpMsg*、 *hWndParent*、および*lpRect*パラメーターは、対応するパラメーターから取得、`IOleObject::DoVerb`メンバー関数。

### <a name="requirements"></a>必要条件

**ヘッダー** afxole.h

## <a name="on_stdoleverb"></a>  ON_STDOLEVERB

標準の動詞の既定の動作をオーバーライドするのにには、このマクロを使用します。

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>パラメーター

*iVerb*  
オーバーライドされている動詞は、標準的な動詞インデックスです。

*memberFxn*  
動詞が呼び出されたときに、フレームワークによって呼び出される関数。

### <a name="remarks"></a>Remarks

形式は、標準の動詞インデックス`OLEIVERB_`アクションと、その後です。 OLEIVERB_HIDE、および OLEIVERB_UIACTIVATE は、標準的な動詞の例を示します。

参照してください[ON_OLEVERB](#on_oleverb)として使用する関数のプロトタイプの詳細については、 *memberFxn*パラメーター。


### <a name="requirements"></a>必要条件

**ヘッダー** afxole.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
