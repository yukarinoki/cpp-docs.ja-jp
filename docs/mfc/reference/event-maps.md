---
title: イベント マップ
ms.date: 06/20/2018
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: 98614aa41d3131d28c9e0c7584e5a88c2249ef97
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65612235"
---
# <a name="event-maps"></a>イベント マップ

コントロールが (キーストローク、マウスのクリックやコントロールの状態の変更) (コントロールの開発者によって決定) 何らかのアクションが発生したコンテナーに通知する必要があるたびに、イベント発生関数を呼び出します。 この関数は、コントロール コンテナー、関連するイベントを発生させることによっていくつかの重要なアクションが発生したことを通知します。

Microsoft Foundation Class ライブラリには、イベントを発生させるために最適化されたプログラミング モデルが用意されています。 このモデルで「イベント マップ」を使用する関数が特定のコントロールのイベントを発生させるかを指定します。 イベント マップには、イベントごとに 1 つのマクロが含まれます。 たとえば、イベント マップを発生させるストックの Click イベントを次に示します。

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

`EVENT_STOCK_CLICK`マクロでは、コントロールが在庫マウスが検出されるたびにイベントをクリックを起動することを示します。 その他のストック イベントのより詳細な一覧は、記事を参照してください。 [ActiveX コントロール。イベント](../../mfc/mfc-activex-controls-events.md)します。 マクロは、カスタム イベントを示すために使用できます。

イベント マップ マクロは重要ですが、一般に挿入しないに直接します。 これは、ため、[プロパティ] ウィンドウがイベント発生関数を関連付けるイベントを使用すると、ソース ファイルでイベント マップ エントリが自動的に作成されます。 編集したり、イベント マップ エントリを追加するとき、[プロパティ] ウィンドウを使用することができます。

イベント マップをサポートするためには、MFC には、次のマクロが用意されています。

## <a name="event-map-macros"></a>イベント マップ マクロ

### <a name="event-map-declaration-and-demarcation"></a>イベント マップの宣言と定義

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|イベント マップがクラスでイベントを (クラス宣言で使用する必要があります)、イベント発生関数にマップに使用されることを宣言します。|
|[BEGIN_EVENT_MAP](#begin_event_map)|イベント マップ (クラスの実装で使用する必要があります) の定義を開始します。|
|[END_EVENT_MAP](#end_event_map)|イベント マップ (クラスの実装で使用する必要があります) の定義を終了します。|

### <a name="event-mapping-macros"></a>イベント マップ マクロ

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|指定したイベントを発生させるどのイベント発生関数を示します。|
|[EVENT_CUSTOM_ID](#event_custom_id)|イベント発生関数が指定したディスパッチ ID を持つ、指定したイベントを発生させることを示します。|

### <a name="message-mapping-macros"></a>メッセージ マップ マクロ

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE コントロールによって処理されるカスタム動詞を示します。|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE コントロールの標準の動詞のマッピングをオーバーライドします。|

##  <a name="declare_event_map"></a>  DECLARE_EVENT_MAP

各`COleControl`-プログラム内の派生クラスは、コントロールは発生させるイベントを指定するイベント マップを提供できます。

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

クラスの宣言の最後に DECLARE_EVENT_MAP マクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルでを使用して、BEGIN_EVENT_MAP マクロ、マクロのエントリの各コントロールのイベント、および END_EVENT_MAP マクロのイベント リストの末尾を宣言します。

イベント マップの詳細については、記事を参照してください。 [ActiveX コントロール。イベント](../../mfc/mfc-activex-controls-events.md)します。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="begin_event_map"></a>  BEGIN_EVENT_MAP

イベント マップの定義を開始します。

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
イベントを持つマップ コントロール クラスの名前を指定します。

*baseClass*<br/>
基本クラスの名前を示す*クラス*します。

### <a name="remarks"></a>Remarks

クラスのメンバー関数を定義する実装 (.cpp) ファイル、BEGIN_EVENT_MAP マクロでは、イベントのマップを開始し、イベントの各マクロのエントリを追加 END_EVENT_MAP マクロを持つイベントのマップを完了します。

イベント マップと BEGIN_EVENT_MAP マクロの詳細については、この記事を参照してください。 [ActiveX コントロール。イベント](../../mfc/mfc-activex-controls-events.md)します。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

##  <a name="end_event_map"></a>  END_EVENT_MAP

イベント マップの定義を終了するのにには、END_EVENT_MAP マクロを使用します。

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

*pszName*<br/>
イベントの名前です。

*pfnFire*<br/>
イベント発生関数の名前。

*vtsParams*<br/>
関数のパラメーター リストを指定する 1 つまたは複数の定数のスペースで区切られたリスト。

### <a name="remarks"></a>Remarks

*VtsParams*パラメーターが空白で区切られた一覧から値の`VTS_`定数。 1 つ以上のスペース (コンマではない) で区切られたこれらの値は、関数のパラメーター リストを指定します。 例えば:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB を表す 32 ビット整数を含むリストを指すポインターによりその後に、値の色を指定します、 `IFontDisp` OLE フォント オブジェクトのインターフェイス。

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
> 追加のバリアント型定数は、すべてのバリアント型を除く VTS_FONT と VTS_PICTURE、variant データ定数へのポインターを提供する定義されています。 使用してこれらの定数の名前は、`VTS_Pconstantname`規則。 たとえば、VTS_PCOLOR、VTS_COLOR 定数ポインターです。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="event_custom_id"></a>  EVENT_CUSTOM_ID

関数で指定したディスパッチ ID に属するカスタム イベントを発生させるイベントを定義*dispid*します。

```cpp
EVENT_CUSTOM_ID(
  pszName,
  dispid,
  pfnFire,
  vtsParams)
```

### <a name="parameters"></a>パラメーター

*pszName*<br/>
イベントの名前です。

*dispid*<br/>
イベントを発生させるときに、コントロールによって使用されるディスパッチ ID。

*pfnFire*<br/>
イベント発生関数の名前。

*vtsParams*<br/>
パラメーターの変数の一覧は、イベントが発生したときに、コントロール コンテナーに渡されます。

### <a name="remarks"></a>Remarks

*VtsParams*引数は、スペースで区切られたリストから値の`VTS_`定数。 スペース、いないのコンマで区切られたこれらの値の 1 つ以上の関数のパラメーター リストを指定します。 例:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

RGB を表す 32 ビット整数を含むリストを指すポインターによりその後に、値の色を指定します、 `IFontDisp` OLE フォント オブジェクトのインターフェイス。

一覧については、`VTS_`定数を参照してください[EVENT_CUSTOM](#event_custom)します。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="on_oleverb"></a>  ON_OLEVERB

このマクロは、カスタム動詞をコントロールの特定のメンバー関数にマップするメッセージ マップ エントリを定義します。

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*idsVerbName*<br/>
動詞の名前の文字列リソース ID。

*memberFxn*<br/>
動詞が呼び出されたときに、フレームワークによって呼び出される関数。

### <a name="remarks"></a>Remarks

文字列テーブルに追加されるカスタム動詞名を作成するリソース エディターを使用できます。

関数のプロトタイプ*memberFxn*は。

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

値、 *lpMsg*、 *hWndParent*、および*lpRect*パラメーターの対応するパラメーターから取得されますが、`IOleObject::DoVerb`メンバー関数。

### <a name="requirements"></a>必要条件

**ヘッダー** afxole.h

## <a name="on_stdoleverb"></a>  ON_STDOLEVERB

標準の動詞の既定の動作をオーバーライドするのにには、このマクロを使用します。

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>パラメーター

*iVerb*<br/>
無効にされている動詞の標準の動詞のインデックス。

*memberFxn*<br/>
動詞が呼び出されたときに、フレームワークによって呼び出される関数。

### <a name="remarks"></a>Remarks

形式は、標準の動詞のインデックス`OLEIVERB_`、その後に操作します。 OLEIVERB_HIDE、および OLEIVERB_UIACTIVATE は、標準的な動詞の例を示します。

参照してください[ON_OLEVERB](#on_oleverb)として使用する関数プロトタイプの説明については、 *memberFxn*パラメーター。

### <a name="requirements"></a>必要条件

**ヘッダー** afxole.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
