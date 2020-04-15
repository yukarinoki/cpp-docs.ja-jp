---
title: CDateTimeCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: d0433507c32c7359f8033836bf845defa8ad7f7a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321913"
---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl クラス

日時指定コントロールの機能がカプセル化されています。

## <a name="syntax"></a>構文

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|`CDateTimeCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDateTimeCtrl::月を閉じる](#closemonthcal)|現在の日時指定コントロールを閉じます。|
|[CDateTimeCtrl::作成](#create)|日時指定コントロールを作成し、オブジェクトに`CDateTimeCtrl`アタッチします。|
|[をクリックします。](#getdatetimepickerinfo)|現在の日時指定コントロールに関する情報を取得します。|
|[をクリックします。](#getidealsize)|現在の日付または時刻を表示するために必要な日時指定コントロールの理想的なサイズを返します。|
|[CDateTimeCtrl:::月数カルカラーを取得します](#getmonthcalcolor)|日付と時刻の選択コントロール内の月間予定表の特定の部分の色を取得します。|
|[CDateTimeCtrl:::月計算](#getmonthcalctrl)|日時指定コントロール`CMonthCalCtrl`に関連付けられているオブジェクトを取得します。|
|[をクリックします。](#getmonthcalfont)|日時指定コントロールの子月間予定表コントロールで現在使用されているフォントを取得します。|
|[CDateTimeCtrl:::ゲットマンズカルスタイル](#getmonthcalstyle)|現在の日時指定コントロールのスタイルを取得します。|
|[をクリックします。](#getrange)|日時指定コントロールの現在の最小および最大許容システム時間を取得します。|
|[CDateTimeCtrl::ゲットタイム](#gettime)|現在選択されている時刻を日時指定コントロールから取得し、指定した構造体に配置します`SYSTEMTIME`。|
|[フォーマットを設定します。](#setformat)|指定された書式指定文字列に従って、日時指定コントロールの表示を設定します。|
|[CDateTimeCtrl:::カレンダーの設定](#setmonthcalcolor)|日付と時刻の選択コントロール内の月間予定表の特定の部分の色を設定します。|
|[CDateTimeCtrl::セットマンスカルフォント](#setmonthcalfont)|日時指定コントロールの子月間予定表コントロールで使用するフォントを設定します。|
|[CDateTimeCtrl:::セットマンスカルスタイル](#setmonthcalstyle)|現在の日時指定コントロールのスタイルを設定します。|
|[CDateTimeCtrl::セットレンジ](#setrange)|日時指定コントロールのシステム許容最小時間と最大時間を設定します。|
|[CDateTimeCtrl::セットタイム](#settime)|日時指定コントロールの時刻を設定します。|

## <a name="remarks"></a>解説

日時指定コントロール (DTP コントロール) は、ユーザーと日付と時刻の情報を交換するための簡単なインターフェイスを提供します。 このインターフェイスにはフィールドが含まれ、各フィールドにはコントロールに格納されている日付と時刻の情報の一部が表示されます。 ユーザーは、特定のフィールドの文字列の内容を変更することによって、コントロールに格納されている情報を変更できます。 ユーザーは、マウスまたはキーボードを使用してフィールド間を移動できます。

オブジェクトの作成時にさまざまなスタイルを適用することで、日時指定コントロールをカスタマイズできます。 [日時指定コントロール](/windows/win32/Controls/date-and-time-picker-control-styles)に固有のスタイルの詳細については、「Windows SDK の日付と時刻の選択コントロールのスタイル」を参照してください。 フォーマット スタイルを使用して、DTP コントロールの表示形式を設定できます。 これらの形式スタイルについては、Windows SDK のトピック「[日付と時刻の選択コントロールのスタイル](/windows/win32/Controls/date-and-time-picker-control-styles)」の「書式スタイル」で説明されています。

日時指定コントロールは、通知とコールバックも使用[します。](../../mfc/using-cdatetimectrl.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdtctl.h

## <a name="cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl

`CDateTimeCtrl` オブジェクトを構築します。

```
CDateTimeCtrl();
```

## <a name="cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a>CDateTimeCtrl::月を閉じる

現在の日時指定コントロールを閉じます。

```
void CloseMonthCal() const;
```

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[DTM_CLOSEMONTHCAL](/windows/win32/Controls/dtm-closemonthcal)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、日付と時刻の指定コントロールにプログラムでアクセスするために使用される変数*m_dateTimeCtrl*を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>例

次のコード例では、現在の日時指定コントロールのドロップダウン カレンダーを閉じます。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

## <a name="cdatetimectrlcreate"></a><a name="create"></a>CDateTimeCtrl::作成

日時指定コントロールを作成し、オブジェクトに`CDateTimeCtrl`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
日付時刻コントロール スタイルの組み合わせを指定します。 [日付と時刻の選択のスタイル](/windows/win32/Controls/date-and-time-picker-control-styles)の詳細については、Windows SDK の「日付と時刻の選択コントロールのスタイル」を参照してください。

*Rect*<br/>
日時指定コントロールの位置とサイズである[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照。

*pParentWnd*<br/>
日付と時刻の選択コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。 NULL にすることはできません。

*nID*<br/>
日時指定コントロールのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

作成が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

##### <a name="to-create-a-date-and-time-picker-control"></a>日時指定コントロールを作成するには

1. オブジェクトを構築するには[、CDateTimeCtrl](#cdatetimectrl)を`CDateTimeCtrl`呼び出します。

1. このメンバー関数を呼び出して、Windows の日時指定コントロールを作成し、オブジェクト`CDateTimeCtrl`にアタッチします。

を呼び`Create`出すと、コモン コントロールが初期化されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

## <a name="cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a>をクリックします。

現在の日時指定コントロールに関する情報を取得します。

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*をクリックします。*|[アウト]現在の日時指定コントロールの説明を受け取る[日時ピッカー情報](/windows/win32/api/commctrl/ns-commctrl-datetimepickerinfo)構造体へのポインター。<br /><br /> 呼び出し元は、この構造体を割り当てる必要があります。 ただし、このメソッドは構造体の*cbSize*メンバーを初期化します。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[DTM_GETDATETIMEPICKERINFO](/windows/win32/Controls/dtm-getdatetimepickerinfo)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、日付と時刻の指定コントロールにプログラムでアクセスするために使用される変数*m_dateTimeCtrl*を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>例

現在の日時指定コントロールに関する情報が正常に取得されたかどうかを示すコード例を次に示します。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

## <a name="cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a>CDateTimeCtrl:::月数カルカラーを取得します

日付と時刻の選択コントロール内の月間予定表の特定の部分の色を取得します。

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>パラメーター

*アイカラー*<br/>
月カレンダーのどの色の領域を取得するかを指定する**int**値。 値の一覧については *、"iColor/* 値の設定" パラメーター[を](#setmonthcalcolor)参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合に、月間予定表コントロールの指定した部分の色設定を表す COLORREF 値。 関数は、失敗した場合は -1 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_GETMCCOLOR](/windows/win32/Controls/dtm-getmccolor)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

## <a name="cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a>CDateTimeCtrl:::月計算

日時指定コントロール`CMonthCalCtrl`に関連付けられているオブジェクトを取得します。

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>戻り値

[CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)オブジェクトへのポインター、または失敗した場合、またはウィンドウが表示されない場合は NULL。

### <a name="remarks"></a>解説

日付と時刻の選択コントロールは、ユーザーがドロップダウン矢印をクリックしたときに、子月間予定表コントロールを作成します。 オブジェクトが`CMonthCalCtrl`不要になった場合は破棄されるため、アプリケーションは日時指定コントロールの子月間カレンダーを表すオブジェクトを格納することに依存しないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

## <a name="cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a>をクリックします。

日時指定コントロールの月間予定表コントロールで現在使用されているフォントを取得します。

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>戻り値

[CFont](../../mfc/reference/cfont-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

戻`CFont`り値によって指されるオブジェクトは一時オブジェクトであり、次のアイドル処理時間中に破棄されます。

## <a name="cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a>CDateTimeCtrl:::ゲットマンズカルスタイル

現在の日時指定コントロールに関連付けられている、ドロップダウン月間予定表コントロールのスタイルを取得します。

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>戻り値

日付と時刻の選択コントロールのスタイルのビットごとの組み合わせ (OR) である、ドロップダウン月間予定表コントロールのスタイル。 詳細については、「[月間予定表コントロール のスタイル](/windows/win32/Controls/month-calendar-control-styles)」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[DTM_GETMCSTYLE](/windows/win32/Controls/dtm-getmcstyle)メッセージを送信します。

## <a name="cdatetimectrlgetrange"></a><a name="getrange"></a>をクリックします。

日時指定コントロールの現在の最小および最大許容システム時間を取得します。

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>パラメーター

*pMinRange*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへのポインターまたは`CDateTimeCtrl`オブジェクト内で許可されている最も早い時刻を含む[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。

*最大範囲*<br/>
オブジェクトまたはオブジェクトで`COleDateTime`許可されている`CTime`最新の時刻を含む`CDateTimeCtrl`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

どの範囲が設定されているかを示すフラグを含む DWORD 値。 状況

`return value & GDTR_MAX` == 0

2 番目のパラメータは有効です。 同様に、

`return value & GDTR_MIN` == 0

その後、最初のパラメータが有効です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_GETRANGE](/windows/win32/Controls/dtm-getrange)の動作を実装します。 MFC の実装では、使用法を`COleDateTime``CTime`指定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

## <a name="cdatetimectrlgettime"></a><a name="gettime"></a>CDateTimeCtrl::ゲットタイム

現在選択されている時刻を日時指定コントロールから取得し、指定した構造体に配置します`SYSTEMTIME`。

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>パラメーター

*タイムデスト*<br/>
最初のバージョンでは、システム時刻情報を受け取る[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。 2 番目のバージョンでは、システム時刻情報を受け取る[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*最も多い*<br/>
システム時刻情報を受け取る[システム時間](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。 NULL にすることはできません。

### <a name="return-value"></a>戻り値

最初のバージョンでは、時刻がオブジェクトに正常に書き込まれた場合`COleDateTime`は 0 以外の値を返します。それ以外の場合は 0。 2 番目と 3 番目のバージョンでは[、DWORD](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange)値は、構造体の*dwFlag*メンバ セットと同じです。 詳細については、後述**の「解説」** を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_GETSYSTEMTIME](/windows/win32/Controls/dtm-getsystemtime)の動作を実装します。 MFC`GetTime`の実装では、または`COleDateTime``CTime`クラスを使用するか、または構造体を`SYSTEMTIME`使用して時間情報を格納できます。

上記の 2 番目と 3 番目のバージョンの戻り値 DWORD は[、NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange)構造体メンバー *dwFlags*に示すように、日付と時刻の選択コントロールが "日付なし" 状態に設定されているかどうかを示します。 返される値がGDT_NONE場合、コントロールは "日付なし" に設定され、DTS_SHOWNONEスタイルが使用されます。 返される値がGDT_VALIDに等しい場合、システム時刻は正常にデスティネーションロケーションに保存されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

## <a name="cdatetimectrlgetidealsize"></a><a name="getidealsize"></a>をクリックします。

現在の日付または時刻を表示するために必要な日時指定コントロールの理想的なサイズを返します。

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Psize*|[アウト]コントロールに最適なサイズを格納する[SIZE](/windows/win32/api/windef/ns-windef-size)構造体へのポインター。|

### <a name="return-value"></a>戻り値

戻り値は常に TRUE です。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[DTM_GETIDEALSIZE](/windows/win32/Controls/dtm-getidealsize)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、日付と時刻の指定コントロールにプログラムでアクセスするために使用される変数*m_dateTimeCtrl*を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>例

次のコード例では、日付と時刻の選択コントロールを表示するのに最適なサイズを取得します。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

## <a name="cdatetimectrlsetformat"></a><a name="setformat"></a>フォーマットを設定します。

指定された書式指定文字列に従って、日時指定コントロールの表示を設定します。

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
目的の表示を定義する、0 で終わる書式指定文字列へのポインター。 このパラメーターを NULL に設定すると、コントロールは現在のスタイルの既定の書式指定文字列にリセットされます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

> [!NOTE]
> ユーザー入力では、この呼び出しの成功または失敗は判断されません。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_SETFORMAT](/windows/win32/Controls/dtm-setformat)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

## <a name="cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a>CDateTimeCtrl:::カレンダーの設定

日付と時刻の選択コントロール内の月間予定表の特定の部分の色を設定します。

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>パラメーター

*アイカラー*<br/>
月のカレンダー コントロールのどの領域を設定するかを指定する**int**値。 この値は、次のいずれかになります。

|[値]|意味|
|-----------|-------------|
|MCSC_BACKGROUND|月の背景色を設定します。|
|MCSC_MONTHBK|月内に表示される背景色を設定します。|
|MCSC_TEXT|月内にテキストを表示するために使用する色を設定します。|
|MCSC_TITLEBK|カレンダーのタイトルに表示される背景色を設定します。|
|MCSC_TITLETEXT|カレンダーのタイトル内のテキストを表示するために使用する色を設定します。|
|MCSC_TRAILINGTEXT|ヘッダーと末尾のテキストを表示するために使用する色を設定します。 ヘッダーと後続の日は、現在のカレンダーに表示される前月と翌月の日数です。|

*ref*<br/>
月間予定表の指定した領域に設定される色を表す COLORREF 値。

### <a name="return-value"></a>戻り値

正常終了した場合に、月間予定表コントロールの指定した部分に対する以前の色設定を表す COLORREF 値。 それ以外の場合、メッセージは -1 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_SETMCCOLOR](/windows/win32/Controls/dtm-setmccolor)の動作を実装します。

### <a name="example"></a>例

  [の例を](#getmonthcalcolor)参照してください。

## <a name="cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a>CDateTimeCtrl::セットマンスカルフォント

日時指定コントロールの子月間予定表コントロールで使用するフォントを設定します。

```
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*hフォント*<br/>
設定するフォントへのハンドル。

*引き出し*<br/>
フォントの設定後すぐにコントロールを再描画するかどうかを指定します。 このパラメーターを TRUE に設定すると、コントロールは再描画されます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_SETMCFONT](/windows/win32/Controls/dtm-setmcfont)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
> このコードを使用する場合は、派生クラスのメンバーを`CDialog` *m_MonthFont*型 と呼び出します`CFont`。

## <a name="cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a>CDateTimeCtrl:::セットマンスカルスタイル

現在の日時指定コントロールに関連付けられている、ドロップダウン月間予定表コントロールのスタイルを設定します。

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Dwstyle*|[in]新しい月間予定表コントロール スタイルは、月間予定表コントロール スタイルのビットごとの組み合わせ (OR) です。 詳細については、「[月間予定表コントロール のスタイル](/windows/win32/Controls/month-calendar-control-styles)」を参照してください。|

### <a name="return-value"></a>戻り値

ドロップダウン月間予定表コントロールの前のスタイル。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[DTM_SETMCSTYLE](/windows/win32/Controls/dtm-setmcstyle)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、日付と時刻の指定コントロールにプログラムでアクセスするために使用される変数*m_dateTimeCtrl*を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>例

次のコード例では、曜日番号、曜日の省略名、および今日のインジケータを表示するように日時指定コントロールを設定します。

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

## <a name="cdatetimectrlsetrange"></a><a name="setrange"></a>CDateTimeCtrl::セットレンジ

日時指定コントロールのシステム許容最小時間と最大時間を設定します。

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>パラメーター

*pMinRange*<br/>
[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへのポインターまたは`CDateTimeCtrl`オブジェクト内で許可されている最も早い時刻を含む[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。

*最大範囲*<br/>
オブジェクトまたはオブジェクトで`COleDateTime`許可されている`CTime`最新の時刻を含む`CDateTimeCtrl`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_SETRANGE](/windows/win32/Controls/dtm-setrange)の動作を実装します。 MFC の実装では、使用法を`COleDateTime``CTime`指定できます。 オブジェクトの`COleDateTime`ステータスが NULL の場合、範囲は削除されます。 `CTime`ポインターまたはポインターが`COleDateTime`NULL の場合、範囲は削除されます。

### <a name="example"></a>例

  [の例を](#getrange)参照してください。

## <a name="cdatetimectrlsettime"></a><a name="settime"></a>CDateTimeCtrl::セットタイム

日時指定コントロールの時刻を設定します。

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>パラメーター

*時間新しい*<br/>
コントロールの設定先を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。

*新しい時間*<br/>
上の 2 番目のバージョンでは、コントロールが設定される時刻を含む[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへのポインター。 上記の 3 番目のバージョンでは、コントロールが設定される時刻を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[DTM_SETSYSTEMTIME](/windows/win32/Controls/dtm-setsystemtime)の動作を実装します。 MFC の`SetTime`実装では、 または`COleDateTime``CTime`クラスを使用するか、構造体を`SYSTEMTIME`使用して時刻情報を設定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを計算します。](../../mfc/reference/cmonthcalctrl-class.md)
