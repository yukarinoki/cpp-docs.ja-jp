---
title: クラスを計算します。
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: da9d588811361d3dfd72d44d5b9ced8460d23936
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319756"
---
# <a name="cmonthcalctrl-class"></a>クラスを計算します。

月間予定表コントロールの機能がカプセル化されています。

## <a name="syntax"></a>構文

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMonthCalCtrl:::CMonthCalCtrl](#cmonthcalctrl)|`CMonthCalCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMonthCalCtrl::作成](#create)|月間予定表コントロールを作成し、オブジェクトに`CMonthCalCtrl`アタッチします。|
|[カレンダーボーダーを取得します。](#getcalendarborder)|現在の月間予定表コントロールの境界線の幅を取得します。|
|[カレンダー数を計算します。](#getcalendarcount)|現在の月間予定表コントロールに表示されるカレンダーの数を取得します。|
|[をクリックします。](#getcalendargridinfo)|現在の月間予定表コントロールに関する情報を取得します。|
|[CMonthCalCtrl::計算](#getcalid)|現在の月間予定表コントロールの予定表識別子を取得します。|
|[CMonthCalCtrl::取得色](#getcolor)|月間予定表コントロールの指定した領域の色を取得します。|
|[CMonthCalCtrl::現在のビュー](#getcurrentview)|現在の月間予定表コントロールによって現在表示されているビューを取得します。|
|[月数計算Ctrl::ゲットカーセル](#getcursel)|現在選択されている日付で示されたシステム時刻を取得します。|
|[ウィークスカルCtrl::ゲットファーストデイオブウィーク](#getfirstdayofweek)|カレンダーの左端の列に表示される週の最初の曜日を取得します。|
|[CMonthCalCtrl::ゲットマックスセルカウント](#getmaxselcount)|月間予定表コントロールで選択できる現在の最大日数を取得します。|
|[次の値を使用します。](#getmaxtodaywidth)|現在の月間予定表コントロールの "Today" 文字列の最大幅を取得します。|
|[月数計算Ctrl::ゲットミンレクレック](#getminreqrect)|月間予定表コントロールで月全体を表示するために必要な最小サイズを取得します。|
|[月数計算Ctrl::ゲットマンスデルタ](#getmonthdelta)|月間予定表コントロールのスクロール率を取得します。|
|[月数計算Ctrl::月の範囲を取得します。](#getmonthrange)|月間予定表コントロールの表示の上限と下限を表す日付情報を取得します。|
|[CMonthCalCtrl::ゲットレンジ](#getrange)|月間予定表コントロールで設定されている現在の最小および最大の日付を取得します。|
|[CMonthCalCtrl::ゲットセルレンジ](#getselrange)|ユーザーが現在選択している日付範囲の上限と下限を表す日付情報を取得します。|
|[CMonthCalCtrl::ゲットトゥデイ](#gettoday)|月間予定表コントロールの "今日" として指定された日付の日付情報を取得します。|
|[CMonthCalCtrl::ヒットテスト](#hittest)|月間予定表コントロールのどのセクションが画面上の特定のポイントにあるかを決定します。|
|[CMonthCalCtrl::イズセンチュリービュー](#iscenturyview)|現在の月間予定表コントロールの現在のビューが世紀ビューかどうかを示します。|
|[CMonthCalCtrl::イディケイディビュー](#isdecadeview)|現在の月間予定表コントロールの現在のビューが 10 年ビューかどうかを示します。|
|[月数計算モード::IsMonthView](#ismonthview)|現在の月間予定表コントロールの現在のビューが月ビューかどうかを示します。|
|[CMonthCalCtrl::イズイヤービュー](#isyearview)|現在の月間予定表コントロールの現在のビューが年ビューかどうかを示します。|
|[カレンダーボーダーを設定します。](#setcalendarborder)|現在の月間予定表コントロールの境界線の幅を設定します。|
|[カレンダーボーダーの既定値](#setcalendarborderdefault)|現在の月間予定表コントロールの境界線の既定の幅を設定します。|
|[CMonthCalCtrl::セットカルイド](#setcalid)|現在の月間予定表コントロールのカレンダー識別子を設定します。|
|[CMonthCalCtrl::セットセンチュリービュー](#setcenturyview)|世紀ビューを表示する現在の月間予定表コントロールを設定します。|
|[CMonthCalCtrl::セットカラー](#setcolor)|月間予定表コントロールの指定した領域の色を設定します。|
|[CMonthCalCtrl::現在のビューを設定します。](#setcurrentview)|指定したビューを表示するように、現在の月間予定表コントロールを設定します。|
|[CMonthCalCtrl::セットカーセル](#setcursel)|月間予定表コントロールの現在選択されている日付を設定します。|
|[CMonthCalCtrl::セットデイステート](#setdaystate)|月間予定表コントロールの日の表示を設定します。|
|[CMonthCalCtrl::セットディケイディビュー](#setdecadeview)|現在の月間予定表コントロールを 10 年ビューに設定します。|
|[ウィークスカルCtrl::セットファーストデイオブウィーク](#setfirstdayofweek)|カレンダーの左端の列に表示する曜日を設定します。|
|[CMonthCalCtrl::セットマックスセルカウント](#setmaxselcount)|月間予定表コントロールで選択できる最大日数を設定します。|
|[月数計算Ctrl::月のデルタ](#setmonthdelta)|月間予定表コントロールのスクロールレートを設定します。|
|[CMonthCalCtrl:::ビューを設定します。](#setmonthview)|月間ビューを表示するように、現在の月間予定表コントロールを設定します。|
|[CMonthCalCtrl::セットレンジ](#setrange)|月間予定表コントロールの日付の最小値と最大値を設定します。|
|[CMonthCalCtrl::セットセルレンジ](#setselrange)|月間予定表コントロールの選択範囲を指定の日付範囲に設定します。|
|[CMonthCalCtrl::セットトゥデイ](#settoday)|現在の日のカレンダー コントロールを設定します。|
|[CMonthCalCtrl::セットイヤービュー](#setyearview)|現在の月間予定表コントロールを年表示に設定します。|
|[CMonthCalCtrl::サイズミンレク](#sizeminreq)|月間予定表コントロールを最小の 1 か月サイズに再描画します。|
|[CMonthCalCtrl::サイズレックトミン](#sizerecttomin)|現在の月間予定表コントロールの場合、指定した四角形に収まるすべてのカレンダーを含むことができる最小の四角形を計算します。|

## <a name="remarks"></a>解説

月間予定表コントロールは、ユーザーが日付を選択できる単純な予定表インターフェイスをユーザーに提供します。 ユーザーは、次の方法で表示を変更できます。

- 前後にスクロールして、月から月へスクロールします。

- [今日] テキストをクリックして現在の日を表示します (MCS_NOTODAY スタイルが使用されていない場合)。

- ポップアップ メニューから 1 か月または 1 年を選択する。

月カレンダー コントロールは、オブジェクトの作成時にさまざまなスタイルを適用することでカスタマイズできます。 これらのスタイルについては、Windows SDK の[月間予定表コントロール スタイル](/windows/win32/Controls/month-calendar-control-styles)で説明します。

月間予定表コントロールは、複数の月を表示でき、日付を太字にして特別な日 (祝日など) を示すことができます。

月間予定表コントロールの使用方法の詳細については、「 [CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md)の使用 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdtctl.h

## <a name="cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a>CMonthCalCtrl:::CMonthCalCtrl

`CMonthCalCtrl` オブジェクトを構築します。

```
CMonthCalCtrl();
```

### <a name="remarks"></a>解説

オブジェクトを構築`Create`した後で呼び出す必要があります。

## <a name="cmonthcalctrlcreate"></a><a name="create"></a>CMonthCalCtrl::作成

月間予定表コントロールを作成し、オブジェクトに`CMonthCalCtrl`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
月間予定表コントロールに適用される Windows スタイルの組み合わせを指定します。 スタイルの詳細については、Windows SDK の[月間予定表コントロール](/windows/win32/Controls/month-calendar-control-styles)スタイルを参照してください。

*Rect*<br/>
[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照。 月間予定表コントロールの位置とサイズを格納します。

*Pt*<br/>
月間予定表コントロールの場所を識別する[POINT](/previous-versions/dd162805\(v=vs.85\))構造体への参照。

*pParentWnd*<br/>
月間予定表コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。 NULL にすることはできません。

*nID*<br/>
月間予定表コントロールのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

次の 2 つの手順で月間予定表コントロールを作成します。

1. [オブジェクトを構築するには、CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)を`CMonthCalCtrl`呼び出します。

1. 月の予定表コントロールを作成し、オブジェクトにアタッチするこのメンバー関数を`CMonthCalCtrl`呼び出します。

を呼び`Create`出すと、コモン コントロールが初期化されます。 呼び出`Create`しのバージョンによって、サイズが決まります。

- MFC でコントロールのサイズを自動的に 1 か月に設定するには *、pt*パラメーターを使用するオーバーライドを呼び出します。

- コントロールのサイズを自分で設定するには *、rect*パラメーターを使用するこの関数のオーバーライドを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

## <a name="cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a>カレンダーボーダーを取得します。

現在の月間予定表コントロールの境界線の幅を取得します。

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>戻り値

コントロールの境界線の幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder)メッセージを送信します。

## <a name="cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a>カレンダー数を計算します。

現在の月間予定表コントロールに表示されるカレンダーの数を取得します。

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>戻り値

月間予定表コントロールに現在表示されているカレンダーの数。 カレンダーの最大数は 12 です。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount)メッセージを送信します。

## <a name="cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a>をクリックします。

現在の月間予定表コントロールに関する情報を取得します。

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*グリッド情報*|[アウト]現在の月間予定表コントロールに関する情報を受け取る[MCGRIDINFO](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo)構造体へのポインター。 呼び出し元は、この構造体の割り当てと初期化を行います。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_monthCalCtrl`月間予定表コントロールにプログラムでアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>例

このメソッドを`GetCalendarGridInfo`使用して、現在の月間予定表コントロールに表示されるカレンダー日付を取得するコード例を次に示します。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

## <a name="cmonthcalctrlgetcalid"></a><a name="getcalid"></a>CMonthCalCtrl::計算

現在の月間予定表コントロールの予定表識別子を取得します。

```
CALID GetCalID() const;
```

### <a name="return-value"></a>戻り値

[カレンダー識別子](/windows/win32/Intl/calendar-identifiers)定数の 1 つ。

### <a name="remarks"></a>解説

カレンダー識別子は、グレゴリオ暦 (ローカライズ)、日本語、イスラム暦など、地域固有のカレンダーを表します。 アプリケーションでは、さまざまな言語サポート機能を持つカレンダー識別子を使用できます。

このメソッドは、Windows SDK に記載されている[MCM_GETCALID](/windows/win32/Controls/mcm-getcalid)メッセージを送信します。

## <a name="cmonthcalctrlgetcolor"></a><a name="getcolor"></a>CMonthCalCtrl::取得色

*nRegion*で指定された月間予定表コントロールの領域の色を取得します。

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>パラメーター

*n地域*<br/>
色の取得元となる月間予定表コントロールの地域。 値の一覧については、 [SetColor](#setcolor)の*nRegion*パラメーターを参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は、月間予定表コントロールの部分に関連付けられている色を指定する[COLORREF](/windows/win32/gdi/colorref)値。 それ以外の場合、このメンバー関数は -1 を返します。

## <a name="cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a>CMonthCalCtrl::現在のビュー

現在の月間予定表コントロールによって現在表示されているビューを取得します。

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>戻り値

現在のビューは、次のいずれかの値で示されます。

|[値]|意味|
|-----------|-------------|
|MCMV_MONTH|月次ビュー|
|MCMV_YEAR|年間ビュー|
|MCMV_DECADE|ディケイドビュー|
|MCMV_CENTURY|センチュリービュー|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_monthCalCtrl`月間予定表コントロールにプログラムでアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>例

次のコード例では、月間予定表コントロールが現在表示されているビューを報告します。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

## <a name="cmonthcalctrlgetcursel"></a><a name="getcursel"></a>月数計算Ctrl::ゲットカーセル

現在選択されている日付で示されたシステム時刻を取得します。

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
オブジェクトまたは[CTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 現在の時刻を受信します。

*時間*<br/>
現在選択されている日付情報を受け取る[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。 このパラメーターは有効なアドレスである必要があり、NULL にすることはできません。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。その他の wize 0.

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETCURSEL](/windows/win32/Controls/mcm-getcursel)の動作を実装します。

> [!NOTE]
> スタイル MCS_MULTISELECTが設定されている場合、このメンバー関数は失敗します。

MFC`GetCurSel`の 実装では`COleDateTime`、使用方法、使用方法、または構造体の`CTime`使用方法を`SYSTEMTIME`指定できます。

## <a name="cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a>ウィークスカルCtrl::ゲットファーストデイオブウィーク

カレンダーの左端の列に表示される週の最初の曜日を取得します。

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>パラメーター

*pbローカル*<br/>
BOOL 値へのポインター。 値が 0 以外の場合、コントロールの設定がコントロール パネルの設定と一致しません。

### <a name="return-value"></a>戻り値

週の最初の曜日を表す整数値。 これらの整数が表す内容の詳細については、「**解説」** を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-getfirstdayofweek)の動作を実装します。 曜日は、次のように整数で表されます。

|[値]|曜日|
|-----------|---------------------|
|0|月曜日|
|1|Tuesday|
|2|水曜日|
|3|Thursday|
|4|金曜日|
|5|土曜日|
|6|土曜日|

### <a name="example"></a>例

  次の例[を参照してください](#setfirstdayofweek)。

## <a name="cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a>CMonthCalCtrl::ゲットマックスセルカウント

月間予定表コントロールで選択できる現在の最大日数を取得します。

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>戻り値

コントロールに対して選択できる合計日数を表す整数値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETMAXSELCOUNT](/windows/win32/Controls/mcm-getmaxselcount)の動作を実装します。 このメンバー関数は、MCS_MULTISELECT スタイルセットを持つコントロールに使用します。

### <a name="example"></a>例

  [の例を](#setmaxselcount)参照してください。

## <a name="cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a>次の値を使用します。

現在の月間予定表コントロールの "Today" 文字列の最大幅を取得します。

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>戻り値

"Today" 文字列の幅 (ピクセル単位)。

### <a name="example"></a>例

次のコード例では、`m_monthCalCtrl`月間予定表コントロールにプログラムでアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>例

メソッドのコード例を次に`GetMaxTodayWidth`示します。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>解説

ユーザーは、月間予定表コントロールの下部に表示される "Today" 文字列をクリックして、現在の日付に戻ることができます。 "Today" 文字列には、ラベル テキストと日付テキストが含まれます。

このメソッドは、Windows SDK で説明されている[MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth)メッセージを送信します。

## <a name="cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a>月数計算Ctrl::ゲットミンレクレック

月間予定表コントロールで月全体を表示するために必要な最小サイズを取得します。

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>パラメーター

*プレック*<br/>
外接する四角形の情報を受け取る[RECT](/previous-versions/dd162897\(v=vs.85\))構造体へのポインター。 このパラメーターは有効なアドレスである必要があり、NULL にすることはできません。

### <a name="return-value"></a>戻り値

成功した場合、このメンバー関数は 0`lpRect`以外を返し、該当する境界情報を受け取ります。 失敗した場合、メンバー関数は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETMINREQRECT](/windows/win32/Controls/mcm-getminreqrect)の動作を実装します。

## <a name="cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a>月数計算Ctrl::ゲットマンスデルタ

月間予定表コントロールのスクロール率を取得します。

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>戻り値

月間予定表コントロールのスクロール率。 スクロールレートは、ユーザーがスクロールボタンを 1 回クリックしたときにコントロールが表示を移動する月数です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta)の動作を実装します。

## <a name="cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a>月数計算Ctrl::月の範囲を取得します。

月間予定表コントロールの表示の上限と下限を表す日付情報を取得します。

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>パラメーター

*レミンレンジ*<br/>
許容される最小日付を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*最大レンジ*<br/>
最大許容日付を`COleDateTime`含`CTime`む または オブジェクトへの参照。

*pMinRange*<br/>
範囲の最下端にある日付を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

*最大範囲*<br/>
範囲の`SYSTEMTIME`最も高い末尾にある日付を含む構造体へのポインター。

*dwFlags*<br/>
取得する範囲制限の範囲を指定する値。 この値は、次のいずれかでなければなりません。

|[値]|意味|
|-----------|-------------|
|GMR_DAYSTATE|部分的にしか表示されない表示範囲の前月と後ろの月を含めます。|
|GMR_VISIBLE|完全に表示されている月のみを含めます。|

### <a name="return-value"></a>戻り値

第 1 バージョンと第 2 バージョンの*refMinRange*と*refMaxRange*で示される 2 つの制限、または 3 番目のバージョンの*pMinRange*と*pMaxRange*で示される範囲を月数で表す整数。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETMONTHRANGE](/windows/win32/Controls/mcm-getmonthrange)の動作を実装します。 MFC`GetMonthRange`の 実装では、使用法、`COleDateTime`使用方法、または`CTime`構造体の使用方法を`SYSTEMTIME`指定できます。

### <a name="example"></a>例

  [の例を](#setdaystate)参照してください。

## <a name="cmonthcalctrlgetrange"></a><a name="getrange"></a>CMonthCalCtrl::ゲットレンジ

月間予定表コントロールで設定されている現在の最小および最大の日付を取得します。

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>パラメーター

*pMinRange*<br/>
範囲の最下`COleDateTime`端にある日付`CTime`を含むオブジェクト、オブジェクト、または[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

*最大範囲*<br/>
範囲の最も`COleDateTime`高い末尾`CTime`にある日付を含むオブジェクト、オブジェクト、または[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="return-value"></a>戻り値

ゼロ (制限は設定されません) の DWORD、または制限情報を指定する次の値の組み合わせ。

|[値]|意味|
|-----------|-------------|
|GDTR_MAX|コントロールに対して最大制限が設定されます。*pMaxRange*は有効であり、適用可能な日付情報を含んでいます。|
|GDTR_MIN|コントロールに対して最小制限が設定されます。*pMinRange*は有効であり、適用可能な日付情報を含んでいます。|

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETRANGE](/windows/win32/Controls/mcm-getrange)の動作を実装します。 MFC`GetRange`の 実装では`COleDateTime`、使用方法、使用方法、または構造体の`CTime`使用方法を`SYSTEMTIME`指定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

## <a name="cmonthcalctrlgetselrange"></a><a name="getselrange"></a>CMonthCalCtrl::ゲットセルレンジ

ユーザーが現在選択している日付範囲の上限と下限を表す日付情報を取得します。

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>パラメーター

*レミンレンジ*<br/>
許容される最小日付を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*最大レンジ*<br/>
最大許容日付を`COleDateTime`含`CTime`む または オブジェクトへの参照。

*pMinRange*<br/>
範囲の最下端にある日付を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

*最大範囲*<br/>
範囲の`SYSTEMTIME`最も高い末尾にある日付を含む構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange)の動作を実装します。 `GetSelRange`MCS_MULTISELECT スタイルを使用しない月間予定表コントロールに適用すると失敗します。

MFC`GetSelRange`の 実装では、使用法、`COleDateTime`使用方法、または`CTime`構造体の使用方法を`SYSTEMTIME`指定できます。

## <a name="cmonthcalctrlgettoday"></a><a name="gettoday"></a>CMonthCalCtrl::ゲットトゥデイ

月間予定表コントロールの "今日" として指定された日付の日付情報を取得します。

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
現在の日付を示す[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*時間*<br/>
日付情報を受け取る[システムタイム](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。 このパラメーターは有効なアドレスである必要があり、NULL にすることはできません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday)の動作を実装します。 MFC`GetToday`の 実装では`COleDateTime`、使用方法、使用方法、または構造体の`CTime`使用方法を`SYSTEMTIME`指定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

## <a name="cmonthcalctrlhittest"></a><a name="hittest"></a>CMonthCalCtrl::ヒットテスト

指定した位置に月カレンダー コントロールがある場合に、そのコントロールを決定します。

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>パラメーター

*テスト*<br/>
月の予定表コントロールのヒット テスト ポイントを含む[MCHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo)構造体へのポインター。

### <a name="return-value"></a>戻り値

DWORD 値。 構造体の**uHit**メンバーと`MCHITTESTINFO`等しい。

### <a name="remarks"></a>解説

`HitTest`は、`MCHITTESTINFO`ヒット テストに関する情報を含む構造体を使用します。

## <a name="cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a>CMonthCalCtrl::イズセンチュリービュー

現在の月間予定表コントロールの現在のビューが世紀ビューかどうかを示します。

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>戻り値

現在のビューが世紀ビューの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview)メッセージを送信します。 そのメッセージがMCMV_CENTURY返された場合、このメソッドは TRUE を返します。

## <a name="cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a>CMonthCalCtrl::イディケイディビュー

現在の月間予定表コントロールの現在のビューが 10 年ビューかどうかを示します。

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>戻り値

現在のビューが 10 年ビューの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview)メッセージを送信します。 そのメッセージがMCMV_DECADEを返す場合、このメソッドは TRUE を返します。

## <a name="cmonthcalctrlismonthview"></a><a name="ismonthview"></a>月数計算モード::IsMonthView

現在の月間予定表コントロールの現在のビューが月ビューかどうかを示します。

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>戻り値

現在のビューが月ビューの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview)メッセージを送信します。 そのメッセージがMCMV_MONTH返す場合、このメソッドは TRUE を返します。

## <a name="cmonthcalctrlisyearview"></a><a name="isyearview"></a>CMonthCalCtrl::イズイヤービュー

現在の月間予定表コントロールの現在のビューが年ビューかどうかを示します。

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>戻り値

現在のビューが年ビューの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview)メッセージを送信します。 そのメッセージがMCMV_YEARを返す場合、このメソッドは TRUE を返します。

## <a name="cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a>カレンダーボーダーを設定します。

現在の月間予定表コントロールの境界線の幅を設定します。

```
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*cxyボーダー*|[in]境界線の幅 (ピクセル単位)。|

### <a name="remarks"></a>解説

このメソッドが成功すると、境界線の幅は*cxyBorder*パラメーターに設定されます。 それ以外の場合、境界線の幅は、現在の[テーマ](/windows/win32/Controls/visual-styles-overview)で指定されている既定値にリセットされ、テーマが使用されていない場合は 0 にリセットされます。

このメソッドは、Windows SDK で説明されている[MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_monthCalCtrl`月間予定表コントロールにプログラムでアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>例

次のコード例では、月間予定表コントロールの境界線の幅を 8 ピクセルに設定します。 このメソッド[が](#getcalendarborder)成功したかどうかを判断するには、メソッドを使用します。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

## <a name="cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a>カレンダーボーダーの既定値

現在の月間予定表コントロールの境界線の既定の幅を設定します。

```
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>解説

境界線の幅は、現在の[テーマ](/windows/win32/Controls/visual-styles-overview)で指定された既定値に設定されます。

このメソッドは、Windows SDK で説明されている[MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder)メッセージを送信します。

## <a name="cmonthcalctrlsetcalid"></a><a name="setcalid"></a>CMonthCalCtrl::セットカルイド

現在の月間予定表コントロールのカレンダー識別子を設定します。

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*キャリド*|[in][カレンダー識別子](/windows/win32/Intl/calendar-identifiers)定数の 1 つ。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

カレンダー識別子は、グレゴリオ暦 (ローカライズ)、日本語、イスラム暦などの地域固有のカレンダーを指定します。 カレンダーを`SetCalID`含むロケールがコンピュータにインストールされている場合は *、calid*パラメータで指定されたカレンダーを表示するには、このメソッドを使用します。

このメソッドは、Windows SDK に記載されている[MCM_SETCALID](/windows/win32/Controls/mcm-setcalid)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_monthCalCtrl`月間予定表コントロールにプログラムでアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>例

次のコード例では、月間予定表コントロールを設定して、天皇暦の暦を表示します。 この`SetCalID`メソッドは、そのカレンダーがコンピュータにインストールされている場合にのみ成功します。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

## <a name="cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a>CMonthCalCtrl::セットセンチュリービュー

世紀ビューを表示する現在の月間予定表コントロールを設定します。

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、世紀ビューを表すビューをに`MCMV_CENTURY`設定するために[、CMonthCalCtrl::SetCurrentView](#setcurrentview)メソッドを使用します。

## <a name="cmonthcalctrlsetcolor"></a><a name="setcolor"></a>CMonthCalCtrl::セットカラー

月間予定表コントロールの指定した領域の色を設定します。

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>パラメーター

*n地域*<br/>
設定する月カレンダーの色を指定する整数値。 この値は、次のいずれかになります。

|[値]|意味|
|-----------|-------------|
|MCSC_BACKGROUND|月の背景色を表示します。|
|MCSC_MONTHBK|月内に表示される背景色。|
|MCSC_TEXT|月内にテキストを表示するために使用される色。|
|MCSC_TITLEBK|カレンダーのタイトルに表示される背景色。|
|MCSC_TITLETEXT|カレンダーのタイトル内のテキストを表示するために使用する色。|
|MCSC_TRAILINGTEXT|ヘッダーおよび末尾のテキストを表示するために使用される色。 ヘッダーと後続の日は、現在のカレンダーに表示される前月と翌月の日数です。|

*ref*<br/>
月間予定表コントロールの指定した部分の新しい色設定の COLORREF 値。

### <a name="return-value"></a>戻り値

正常終了した場合は、月間予定表コントロールの指定した部分の前の色設定を表す COLORREF 値。 それ以外の場合、このメッセージは -1 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETCOLOR](/windows/win32/Controls/mcm-setcolor)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

## <a name="cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a>CMonthCalCtrl::現在のビューを設定します。

指定したビューを表示するように、現在の月間予定表コントロールを設定します。

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ドウニュービュー*|[in]月、年、または世紀のビューを指定する次の値の 1 つ。<br /><br /> MCMV_MONTH: 月次ビュー<br /><br /> MCMV_YEAR: 年次ビュー<br /><br /> MCMV_DECADE:10年景<br /><br /> MCMV_CENTURY: センチュリービュー|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview)メッセージを送信します。

## <a name="cmonthcalctrlsetcursel"></a><a name="setcursel"></a>CMonthCalCtrl::セットカーセル

月間予定表コントロールの現在選択されている日付を設定します。

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
現在選択されている月間予定表コントロールを示す[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへの参照。

*時間*<br/>
現在の選択として設定される日付を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETCURSEL](/windows/win32/Controls/mcm-setcursel)の動作を実装します。 MFC`SetCurSel`の 実装では`COleDateTime`、使用方法、使用方法、または構造体の`CTime`使用方法を`SYSTEMTIME`指定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

## <a name="cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a>CMonthCalCtrl::セットデイステート

月間予定表コントロールの日の表示を設定します。

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>パラメーター

*nMonths*<br/>
*pStates*が指す配列内の要素の数を示す値。

*pステート*<br/>
月間予定表コントロールが毎日表示される方法を定義する値の[MONTHDAYSTATE](/windows/win32/Controls/monthdaystate)配列へのポインター。 MONTHDAYSTATE データ型はビット フィールドで、各ビット (1 ~ 31) は 1 か月の 1 日の状態を表します。 ビットがオンの場合、対応する日は太字で表示されます。それ以外の場合は、強調なしで表示されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETDAYSTATE](/windows/win32/Controls/mcm-setdaystate)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

## <a name="cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a>CMonthCalCtrl::セットディケイディビュー

現在の月間予定表コントロールを 10 年ビューに設定します。

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、10 年のビューを表すビューをに設定するのに`MCMV_DECADE`[は、CMonthCalCtrl::SetCurrentView](#setcurrentview)メソッドを使用します。

## <a name="cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a>ウィークスカルCtrl::セットファーストデイオブウィーク

カレンダーの左端の列に表示する曜日を設定します。

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>パラメーター

*アイデイ*<br/>
週の最初の曜日として設定される曜日を表す整数値。 この値は、日の数字のいずれかでなければなりません。 曜日番号の説明については[、GetFirstDayOfWeek](#getfirstdayofweek)を参照してください。

*lp古い*<br/>
前に設定した週の最初の曜日を示す整数へのポインター。

### <a name="return-value"></a>戻り値

前の週の最初の曜日が、コントロール パネルの設定で示されている日であるLOCALE_IFIRSTDAYOFWEEK以外の値に設定されている場合は、0 以外の値。 それ以外の場合、この関数は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-setfirstdayofweek)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

## <a name="cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a>CMonthCalCtrl::セットマックスセルカウント

月間予定表コントロールで選択できる最大日数を設定します。

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>パラメーター

*nMax*<br/>
選択可能な日数の最大値を表すために設定される値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETMAXSELCOUNT](/windows/win32/Controls/mcm-setmaxselcount)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

## <a name="cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a>月数計算Ctrl::月のデルタ

月間予定表コントロールのスクロールレートを設定します。

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>パラメーター

*アイデルタ*<br/>
コントロールのスクロール レートとして設定する月数。 この値が 0 の場合、月のデルタは既定値 (コントロールに表示される月数) にリセットされます。

### <a name="return-value"></a>戻り値

前のスクロール速度。 スクロール速度が設定されていない場合、戻り値は 0 になります。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETMONTHDELTA](/windows/win32/Controls/mcm-setmonthdelta)の動作を実装します。

## <a name="cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a>CMonthCalCtrl:::ビューを設定します。

月間ビューを表示するように、現在の月間予定表コントロールを設定します。

```
BOOL SetMonthView();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、月のビューを表すMCMV_MONTHにビューを設定するのに[は、CMonthCalCtrl::SetCurrentView](#setcurrentview)メソッドを使用します。

### <a name="example"></a>例

次のコード例では、`m_monthCalCtrl`月間予定表コントロールにプログラムでアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>例

次のコード例では、月間予定表コントロールに月、年、10 年、および世紀のビューを表示するように設定します。

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

## <a name="cmonthcalctrlsetrange"></a><a name="setrange"></a>CMonthCalCtrl::セットレンジ

月間予定表コントロールの最小および最大許容日付を設定します。

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>パラメーター

*pMinRange*<br/>
範囲の最下`COleDateTime`端にある日付`CTime`を含むオブジェクト、オブジェクト、または[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

*最大範囲*<br/>
範囲の`COleDateTime`最も高い末尾`CTime`にある日付を`SYSTEMTIME`含むオブジェクト、オブジェクト、または構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETRANGE](/windows/win32/Controls/mcm-setrange)の動作を実装します。 MFC`SetRange`の 実装では、使用法、`COleDateTime`使用方法、または`CTime`構造体の使用方法を`SYSTEMTIME`指定できます。

### <a name="example"></a>例

  次の例[を](#getrange)参照してください。

## <a name="cmonthcalctrlsetselrange"></a><a name="setselrange"></a>CMonthCalCtrl::セットセルレンジ

月間予定表コントロールの選択範囲を指定の日付範囲に設定します。

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>パラメーター

*pMinRange*<br/>
範囲の最下`COleDateTime`端にある日付`CTime`を含むオブジェクト、オブジェクト、または[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

*最大範囲*<br/>
範囲の`COleDateTime`最も高い末尾`CTime`にある日付を`SYSTEMTIME`含むオブジェクト、オブジェクト、または構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETSELRANGE](/windows/win32/Controls/mcm-setselrange)の動作を実装します。 MFC`SetSelRange`の 実装では、使用法、`COleDateTime`使用方法、または`CTime`構造体の使用方法を`SYSTEMTIME`指定できます。

## <a name="cmonthcalctrlsettoday"></a><a name="settoday"></a>CMonthCalCtrl::セットトゥデイ

現在の日のカレンダー コントロールを設定します。

```
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>パラメーター

*時間*<br/>
現在の日付を含む[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。

*時間*<br/>
2 番目のバージョンでは、現在の日付情報を含む[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへのポインター。 3 番目のバージョンでは、現在の日付情報を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[MCM_SETTODAY](/windows/win32/Controls/mcm-settoday)の動作を実装します。

### <a name="example"></a>例

  次の例[を](#gettoday)参照してください。

## <a name="cmonthcalctrlsetyearview"></a><a name="setyearview"></a>CMonthCalCtrl::セットイヤービュー

現在の月間予定表コントロールを年表示に設定します。

```
BOOL SetYearView();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、[年間](#setcurrentview)ビューを表すMCMV_YEARにビューを設定するメソッドを使用します。

## <a name="cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a>CMonthCalCtrl::サイズミンレク

月間予定表コントロールを、1 か月の最小サイズに表示します。

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>パラメーター

*brepaint*<br/>
コントロールを再描画するかどうかを指定します。 既定では、TRUE。 FALSE の場合、再描画は行われません。

### <a name="return-value"></a>戻り値

月間予定表コントロールのサイズが最小値に設定されている場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

正常`SizeMinReq`に呼び出すと、1 か月のカレンダーの月間予定表コントロール全体が表示されます。

## <a name="cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a>CMonthCalCtrl::サイズレックトミン

現在の月間予定表コントロールの場合、指定した四角形に収まるすべてのカレンダーを含むことができる最小の四角形を計算します。

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Lprect*|[in]目的の数のカレンダーを含む四角形を定義する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体へのポインター。|

### <a name="return-value"></a>戻り値

サイズが*lpRect*パラメーターで定義された四角形以下の矩形を定義する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体へのポインター。

### <a name="remarks"></a>解説

このメソッドは *、lpRect*パラメーターで指定された四角形に収まるカレンダーの数を計算し、その数の予定表を含むことができる最小の四角形を返します。 実際には、このメソッドは、指定された四角形を、目的の数のカレンダーに正確に収まるように縮小します。

このメソッドは、Windows SDK で説明されている[MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin)メッセージを送信します。

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL1](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CDateTimeCtrl クラス](../../mfc/reference/cdatetimectrl-class.md)
