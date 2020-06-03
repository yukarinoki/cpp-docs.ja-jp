---
title: イベント マップ
ms.date: 09/07/2019
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: c79d2fb1ac73947ddb13adcbd444ff7b5d50bdb4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365737"
---
# <a name="event-maps"></a>イベント マップ

コントロールは、コントロールのコンテナーに対して、(コントロールの開発者によって決定される) 何らかのアクション (キーストローク、マウス クリック、コントロールの状態の変更など) が発生したことを通知する場合は、イベント発生関数を呼び出します。 この関数は、関連するイベントを発生させることによって、重要なアクションが発生したことをコントロール コンテナーに通知します。

Microsoft Foundation クラス ライブラリには、イベントを発生させるのに最適なプログラミング モデルが用意されています。 このモデルでは、特定のコントロールに対してどの関数がどのイベントを発生させるかを指定するために"イベント マップ"が使用されます。 イベント マップには、イベントごとに 1 つのマクロが含まれます。 たとえば、ストック Click イベントを発生させるイベント マップは次のようになります。

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

この`EVENT_STOCK_CLICK`マクロは、コントロールがマウスクリックを検出するたびにストック Click イベントを発生することを示します。 その他のストック イベントの詳細については[、「ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)」を参照してください。 また、カスタム イベントを示すマクロも使用できます。

イベント マップ マクロは重要ですが、通常は直接挿入しません。 これは、イベント発生関数をイベントに関連付けるために使用すると、ソース ファイルのプロパティ ウィンドウ **([プロパティ****]** ウィンドウ ) によって自動的にイベント マップ エントリが作成されるためです。 イベント マップ エントリを編集または追加する場合は、いつでも **[プロパティ]** ウィンドウを使用できます。

イベント マップをサポートするために、MFC には次のマクロが用意されています。

## <a name="event-map-macros"></a>イベント マップ マクロ

### <a name="event-map-declaration-and-demarcation"></a>イベント マップの宣言と境界

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|イベント マップをクラス内で使用してイベントをイベント発生関数にマップすることを宣言します (クラス宣言で使用する必要があります)。|
|[BEGIN_EVENT_MAP](#begin_event_map)|イベント マップの定義を開始します (クラス実装で使用する必要があります)。|
|[END_EVENT_MAP](#end_event_map)|イベント マップの定義を終了します (クラス実装で使用する必要があります)。|

### <a name="event-mapping-macros"></a>イベント マッピング マクロ

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|指定したイベントを発生させるイベント起動関数を示します。|
|[EVENT_CUSTOM_ID](#event_custom_id)|指定したディスパッチ ID を使用して、指定したイベントを発生させるイベント実行関数を示します。|

### <a name="message-mapping-macros"></a>メッセージ マッピング マクロ

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|OLE コントロールによって処理されるカスタム動詞を示します。|
|[ON_STDOLEVERB](#on_stdoleverb)|OLE コントロールの標準動詞マッピングをオーバーライドします。|

## <a name="declare_event_map"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP

プログラム`COleControl`内の各派生クラスは、コントロールが起動するイベントを指定するイベント マップを提供できます。

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>解説

クラス宣言の最後にDECLARE_EVENT_MAPマクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルで、BEGIN_EVENT_MAP マクロ、各コントロールのイベントのマクロ エントリ、およびEND_EVENT_MAP マクロを使用してイベント リストの最後を宣言します。

イベント マップの詳細については[、「ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="begin_event_map"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP

イベント マップの定義を開始します。

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
イベント マップが指定されているコントロール クラスの名前を指定します。

*Baseclass*<br/>
クラスの基本クラスの名前*を*指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、BEGIN_EVENT_MAP マクロを使用してイベント マップを開始し、各イベントのマクロ エントリを追加して、END_EVENT_MAP マクロを使用してイベント マップを完了します。

イベント マップおよびBEGIN_EVENT_MAP マクロの詳細については[、「ActiveX コントロール: イベント](../../mfc/mfc-activex-controls-events.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="end_event_map"></a><a name="end_event_map"></a>END_EVENT_MAP

END_EVENT_MAP マクロを使用して、イベント マップの定義を終了します。

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="event_custom"></a><a name="event_custom"></a>EVENT_CUSTOM

カスタム イベントのイベント マップ エントリを定義します。

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
イベントの名前です。

*プンファイア*<br/>
イベント発生関数の名前。

*vtsパラム*<br/>
関数のパラメーター リストを指定する 1 つ以上の定数のスペース区切りのリスト。

### <a name="remarks"></a>解説

*vtsParams*パラメータは、`VTS_`定数の値をスペースで区切ったリストです。 これらの値のうち 1 つ以上がスペースで区切られ (コンマではなく) 関数のパラメーター・リストが指定されます。 次に例を示します。

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

は、RGB カラー値を表す 32 ビット整数を含むリストを指定し、`IFontDisp`その後に OLE フォント オブジェクトのインターフェイスへのポインターを指定します。

定数`VTS_`とその意味は次のとおりです。

|Symbol|パラメーターのタイプ|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**長い**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|通貨|
|VTS_DATE|DATE|
|VTS_BSTR|**定数**__文字\*__|
|VTS_DISPATCH|LPディスパッチ|
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
> すべてのバリアント型に対して、バリアント型のデータ定数へのポインターを提供するVTS_FONTとVTS_PICTUREを除く、追加のバリアント定数が定義されています。 これらの定数は、この規則を`VTS_Pconstantname`使用して名前が付けられます。 たとえば、VTS_PCOLORはVTS_COLOR定数へのポインターです。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="event_custom_id"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID

*dispid*で指定されたディスパッチ ID に属するカスタム イベントのイベント発生関数を定義します。

```cpp
EVENT_CUSTOM_ID(
    pszName,
    dispid,
    pfnFire,
    vtsParams)
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
イベントの名前です。

*Dispid*<br/>
イベントを発生するときにコントロールが使用するディスパッチ ID。

*プンファイア*<br/>
イベント発生関数の名前。

*vtsパラム*<br/>
イベントの発生時にコントロール コンテナーに渡されるパラメーターの変数リスト。

### <a name="remarks"></a>解説

*vtsParams*引数は、`VTS_`定数の値をスペースで区切ったリストです。 コンマではなく空白で区切られたこれらの値の 1 つ以上は、関数のパラメーター リストを指定します。 次に例を示します。

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

は、RGB カラー値を表す 32 ビット整数を含むリストを指定し、`IFontDisp`その後に OLE フォント オブジェクトのインターフェイスへのポインターを指定します。

`VTS_`定数の一覧については[、「EVENT_CUSTOM」](#event_custom)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー** afxctl.h

## <a name="on_oleverb"></a><a name="on_oleverb"></a>ON_OLEVERB

このマクロは、カスタム動詞をコントロールの特定のメンバー関数にマップするメッセージ マップ エントリを定義します。

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
動詞の名前の文字列リソース ID。

*メンバーFxn*<br/>
動詞が呼び出されたときにフレームワークによって呼び出される関数。

### <a name="remarks"></a>解説

リソース エディターを使用して、文字列テーブルに追加されるカスタム動詞名を作成できます。

*メンバーFxn*の関数プロトタイプは次のとおりです。

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

*lpMsg* *、hWndParent*、および*lpRect*の各パラメーターの値は、`IOleObject::DoVerb`メンバー関数の対応するパラメーターから取得されます。

### <a name="requirements"></a>必要条件

**ヘッダー** afxole.h

## <a name="on_stdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB

このマクロを使用して、標準動詞の既定の動作をオーバーライドします。

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>パラメーター

*i動詞*<br/>
オーバーライドされる動詞の標準動詞インデックス。

*メンバーFxn*<br/>
動詞が呼び出されたときにフレームワークによって呼び出される関数。

### <a name="remarks"></a>解説

標準動詞インデックスは、フォーム`OLEIVERB_`の後にアクションが続きます。 OLEIVERB_SHOW、OLEIVERB_HIDE、OLEIVERB_UIACTIVATEは、標準的な動詞の例です。

*memberFxn*パラメーターとして使用する関数プロトタイプの説明については[、ON_OLEVERB](#on_oleverb)を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー** afxole.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
