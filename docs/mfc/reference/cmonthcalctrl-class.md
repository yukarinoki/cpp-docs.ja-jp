---
title: CMonthCalCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45e0499297c814e4a214962bc2f51404960a8c38
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039220"
---
# <a name="cmonthcalctrl-class"></a>CMonthCalCtrl クラス
月間予定表コントロールの機能がカプセル化されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMonthCalCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMonthCalCtrl::CMonthCalCtrl](#cmonthcalctrl)|`CMonthCalCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMonthCalCtrl::Create](#create)|月間予定表コントロールを作成し、それにアタッチ、`CMonthCalCtrl`オブジェクト。|  
|[CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)|現在の月間予定表コントロールの境界線の幅を取得します。|  
|[CMonthCalCtrl::GetCalendarCount](#getcalendarcount)|現在の月のカレンダー コントロールに表示されるカレンダーの数を取得します。|  
|[CMonthCalCtrl::GetCalendarGridInfo](#getcalendargridinfo)|現在の月間予定表コントロールに関する情報を取得します。|  
|[CMonthCalCtrl::GetCalID](#getcalid)|現在の月間予定表コントロールのカレンダー識別子を取得します。|  
|[CMonthCalCtrl::GetColor](#getcolor)|月間予定表コントロールの指定した領域の色を取得します。|  
|[CMonthCalCtrl::GetCurrentView](#getcurrentview)|現在の月の予定表コントロールで現在表示されているビューを取得します。|  
|[CMonthCalCtrl::GetCurSel](#getcursel)|現在選択されている日付によって示されるは、システム時刻を取得します。|  
|[CMonthCalCtrl::GetFirstDayOfWeek](#getfirstdayofweek)|予定表の左端の列に表示する週の最初の日を取得します。|  
|[CMonthCalCtrl::GetMaxSelCount](#getmaxselcount)|月間予定表コントロールで選択できる日数の現在の最大数を取得します。|  
|[CMonthCalCtrl::GetMaxTodayWidth](#getmaxtodaywidth)|現在の月の予定表コントロールの「今日」の文字列の最大の幅を取得します。|  
|[CMonthCalCtrl::GetMinReqRect](#getminreqrect)|月間予定表コントロールで、完全な月を表示するために必要な最小サイズを取得します。|  
|[CMonthCalCtrl::GetMonthDelta](#getmonthdelta)|月間予定表コントロールのスクロール率を取得します。|  
|[CMonthCalCtrl::GetMonthRange](#getmonthrange)|日付、月間予定表コントロールの表示の高値と安値の制限を表す情報を取得します。|  
|[CMonthCalCtrl::GetRange](#getrange)|月間予定表コントロールで設定現在の最小値と最大の日付を取得します。|  
|[CMonthCalCtrl::GetSelRange](#getselrange)|ユーザーが現在選択されている日付範囲の上限と下限を表す日付情報を取得します。|  
|[CMonthCalCtrl::GetToday](#gettoday)|月間予定表コントロールの「現在」として指定された日付について日付の情報を取得します。|  
|[CMonthCalCtrl::HitTest](#hittest)|月間予定表コントロールのどのセクションでは、画面上の任意の時点を決定します。|  
|[CMonthCalCtrl::IsCenturyView](#iscenturyview)|現在の月間予定表コントロールの現在のビューが 4 桁の年のビューであるかどうかを示します。|  
|[CMonthCalCtrl::IsDecadeView](#isdecadeview)|現在の月間予定表コントロールの現在のビューが 10 年ビューであるかどうかを示します。|  
|[CMonthCalCtrl::IsMonthView](#ismonthview)|現在の月間予定表コントロールの現在のビューが月単位の表示であるかどうかを示します。|  
|[CMonthCalCtrl::IsYearView](#isyearview)|現在の月間予定表コントロールの現在のビューが年のビューであるかどうかを示します。|  
|[CMonthCalCtrl::SetCalendarBorder](#setcalendarborder)|現在の月間予定表コントロールの境界線の幅を設定します。|  
|[CMonthCalCtrl::SetCalendarBorderDefault](#setcalendarborderdefault)|現在の月間予定表コントロールの枠線の既定の幅を設定します。|  
|[CMonthCalCtrl::SetCalID](#setcalid)|現在の月間予定表コントロールのカレンダー識別子を設定します。|  
|[CMonthCalCtrl::SetCenturyView](#setcenturyview)|2 桁の年のビューを表示する現在の月のカレンダー コントロールを設定します。|  
|[CMonthCalCtrl::SetColor](#setcolor)|月間予定表コントロールの指定した領域の色を設定します。|  
|[CMonthCalCtrl::SetCurrentView](#setcurrentview)|指定されたビューを表示する現在の月のカレンダー コントロールを設定します。|  
|[か](#setcursel)|月間予定表コントロールで現在選択されている日付を設定します。|  
|[CMonthCalCtrl::SetDayState](#setdaystate)|月間予定表コントロールでの日付の表示を設定します。|  
|[CMonthCalCtrl::SetDecadeView](#setdecadeview)|10 年間のビューに現在の月のカレンダー コントロールを設定します。|  
|[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)|予定表の左端の列に表示する曜日を設定します。|  
|[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)|月間予定表コントロールで選択できる日数の最大数を設定します。|  
|[CMonthCalCtrl::SetMonthDelta](#setmonthdelta)|月間予定表コントロールのスクロール率を設定します。|  
|[CMonthCalCtrl::SetMonthView](#setmonthview)|月のビューを表示する現在の月の予定表コントロールを設定します。|  
|[CMonthCalCtrl::SetRange](#setrange)|最小値と最大の値は、月間予定表コントロールの日付を設定します。|  
|[CMonthCalCtrl::SetSelRange](#setselrange)|指定した日付範囲に月間予定表の選択コントロールを設定します。|  
|[CMonthCalCtrl::SetToday](#settoday)|現在の日の予定表コントロールを設定します。|  
|[CMonthCalCtrl::SetYearView](#setyearview)|年のビューに現在の月のカレンダー コントロールを設定します。|  
|[CMonthCalCtrl::SizeMinReq](#sizeminreq)|再描画月間予定表は、その最小値、1 か月のサイズに制御します。|  
|[CMonthCalCtrl::SizeRectToMin](#sizerecttomin)|現在の月のカレンダー コントロールは、指定した四角形に収まるすべてのカレンダーを含めることができる最も小さな四角形を計算します。|  
  
## <a name="remarks"></a>Remarks  
 月間予定表コントロールでは、ユーザーが日付を選択できる、単純なカレンダー インターフェイスを持つユーザーを提供します。 ユーザーは別に表示を変更できます。  
  
-   前後の月にスクロールします。  
  
-   現在表示されるテキストを現在の日付をクリックすると (場合、 **MCS_NOTODAY**スタイルは使用されません)。  
  
-   1 か月またはポップアップ メニューからの年を選択します。  
  
 月をカスタマイズする表示カレンダー コントロールを作成するときに、オブジェクトをさまざまなスタイルを適用しています。 これらのスタイルが説明されている[月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919)Windows SDK に含まれています。  
  
 月間予定表コントロールを 1 か月以上表示し、太字で (休日) などの特別な日を示すことが、日付。  
  
 月間予定表コントロールの使い方の詳細については、次を参照してください。[を使用して CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CMonthCalCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdtctl.h  
  
##  <a name="cmonthcalctrl"></a>  CMonthCalCtrl::CMonthCalCtrl  
 `CMonthCalCtrl` オブジェクトを構築します。  
  
```  
CMonthCalCtrl();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります**作成**オブジェクトを構築した後です。  
  
##  <a name="create"></a>  CMonthCalCtrl::Create  
 月間予定表コントロールを作成し、それにアタッチ、`CMonthCalCtrl`オブジェクト。  
  
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
 *dwStyle*  
 月間予定表コントロールに適用されるスタイルを Windows の組み合わせを指定します。 参照してください[月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919)スタイルの詳細については、Windows SDK に含まれています。  
  
 *rect*  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。 月間予定表コントロールのサイズと位置が含まれています。  
  
 *pt*  
 参照、[ポイント](http://msdn.microsoft.com/library/windows/desktop/dd162805)月間予定表コントロールの場所を識別する構造体。  
  
 *pParentWnd*  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、月間予定表コントロールの親ウィンドウです。 なければなりません**NULL**です。  
  
 *nID*  
 月間予定表コントロールのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 作成、1 か月表示カレンダー コントロールで 2 つの手順。  
  
1.  呼び出す[CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)構築するために、`CMonthCalCtrl`オブジェクト。  
  
2.  このメンバー関数、月間予定表コントロールを作成してにアタッチする、`CMonthCalCtrl`オブジェクト。  
  
 呼び出すと`Create`、コモン コントロールを初期化します。 バージョン`Create`する呼び出しでは、サイズの方法を決定します。  
  
-   1 か月にコントロールのサイズを自動的に MFC を使用するオーバーライドを呼び出す、 *pt*パラメーター。  
  
-   自分でコントロールのサイズを使用してこの関数のオーバーライドを呼び出す、 *rect*パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]  
  
##  <a name="getcalendarborder"></a>  CMonthCalCtrl::GetCalendarBorder  
 現在の月間予定表コントロールの境界線の幅を取得します。  
  
```  
int GetCalendarBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ピクセル単位で、コントロールの境界線の幅。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760945) Windows SDK で説明するメッセージ。  
  
##  <a name="getcalendarcount"></a>  CMonthCalCtrl::GetCalendarCount  
 現在の月のカレンダー コントロールに表示されるカレンダーの数を取得します。  
  
```  
int GetCalendarCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 月間予定表コントロールで現在表示されているカレンダーの数。 カレンダーの許容最大数は 12 です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCALENDARCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760947) Windows SDK で説明するメッセージ。  
  
##  <a name="getcalendargridinfo"></a>  CMonthCalCtrl::GetCalendarGridInfo  
 現在の月間予定表コントロールに関する情報を取得します。  
  
```  
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[out]*pmcGridInfo*|ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb760925)現在の月のカレンダー コントロールに関する情報を受け取る構造体。 呼び出し元を割り当てると、この構造体を初期化します。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCALENDARGRIDINFO](http://msdn.microsoft.com/library/windows/desktop/bb760949) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_monthCalCtrl`、つまり月間予定表コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>例  
 次のコード例では、`GetCalendarGridInfo`現在の月のカレンダー コントロールを表示するカレンダーの日付を取得します。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]  
  
##  <a name="getcalid"></a>  CMonthCalCtrl::GetCalID  
 現在の月間予定表コントロールのカレンダー識別子を取得します。  
  
```  
CALID GetCalID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 1 つ、[カレンダー識別子](http://msdn.microsoft.com/library/windows/desktop/dd317732)定数。  
  
### <a name="remarks"></a>Remarks  
 カレンダーの識別子を表しますグレゴリオ暦 (ローカライズ版)、日本語、イスラム暦などの地域に固有のカレンダーの予定表。 アプリケーションでは、予定表の識別子を持つ関数をサポートするさまざまな言語を使用できます。  
  
 このメソッドは、送信、 [MCM_GETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760951) Windows SDK で説明するメッセージ。  
  
##  <a name="getcolor"></a>  CMonthCalCtrl::GetColor  
 予定表で指定されたコントロールの月の領域の色を取得*nRegion*です。  
  
```  
COLORREF GetColor(int nRegion) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nRegion*  
 色の取得元となる月間予定表コントロールの領域。 値の一覧は、次を参照してください。、 *nRegion*のパラメーター [SetColor](#setcolor)です。  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)正常終了した場合は、月間予定表コントロールの部分に関連付けられている色を指定する値。 それ以外の場合、このメンバー関数は-1 を返します。  
  
##  <a name="getcurrentview"></a>  CMonthCalCtrl::GetCurrentView  
 現在の月の予定表コントロールで現在表示されているビューを取得します。  
  
```  
DWORD GetCurrentView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のビューは、次の値のいずれかで示される。  
  
|[値]|説明|  
|-----------|-------------|  
|`MCMV_MONTH`|月単位のビュー|  
|`MCMV_YEAR`|年のビュー|  
|`MCMV_DECADE`|10 年間の表示|  
|`MCMV_CENTURY`|2 桁の年のビュー|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_monthCalCtrl`、つまり月間予定表コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>例  
 月間予定表を表示する次のコード例のレポート コントロールが現在表示をします。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]  
  
##  <a name="getcursel"></a>  CMonthCalCtrl::GetCurSel  
 現在選択されている日付によって示されるは、システム時刻を取得します。  
  
```  
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;  
   
BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *refDateTime*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトまたは[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。 現在の時刻を受信します。  
  
 *pDateTime*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)は現在選択されている日付情報を受信する構造体。 このパラメーターが有効なアドレスでなければならないし、することはできません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。otherwize 0 です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb760957)Windows SDK で説明されている。  
  
> [!NOTE]
>  場合、このメンバー関数が失敗したスタイル**MCS_MULTISELECT**が設定されています。  
  
 MFC の実装で`GetCurSel`を指定することができます、`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
##  <a name="getfirstdayofweek"></a>  CMonthCalCtrl::GetFirstDayOfWeek  
 予定表の左端の列に表示する週の最初の日を取得します。  
  
```  
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pbLocal*  
 ポインター、 **BOOL**値。 値が 0 以外の場合、コントロールの設定では、コントロール パネルの設定は一致しません。  
  
### <a name="return-value"></a>戻り値  
 週の最初の日を表す整数値。 参照してください**解説**整数値の詳細についてです。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb760958)Windows SDK で説明されている。 週の曜日は、次のように、整数として表されます。  
  
|[値]|週の曜日|  
|-----------|---------------------|  
|0|月曜日|  
|1|火曜日|  
|2|水曜日|  
|3|木曜日|  
|4|金曜日|  
|5|土曜日|  
|6|日曜日|  
  
### <a name="example"></a>例  
  例を参照して[CMonthCalCtrl::SetFirstDayOfWeek](#setfirstdayofweek)です。  
  
##  <a name="getmaxselcount"></a>  CMonthCalCtrl::GetMaxSelCount  
 月間予定表コントロールで選択できる日数の現在の最大数を取得します。  
  
```  
int GetMaxSelCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの選択できる日数の合計数を表す整数値。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb760960)Windows SDK で説明されている。 コントロールには、このメンバー関数を使用して、 **MCS_MULTISELECT**セットのスタイルを設定します。  
  
### <a name="example"></a>例  
  例を参照して[CMonthCalCtrl::SetMaxSelCount](#setmaxselcount)です。  
  
##  <a name="getmaxtodaywidth"></a>  CMonthCalCtrl::GetMaxTodayWidth  
 現在の月の予定表コントロールの「今日」の文字列の最大の幅を取得します。  
  
```  
DWORD GetMaxTodayWidth() const;  
```  
  
### <a name="return-value"></a>戻り値  
 「今日」文字列をピクセル単位の幅。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_monthCalCtrl`、つまり月間予定表コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>例  
 次のコード例を示しています、`GetMaxTodayWidth`メソッドです。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、「今日」文字列、月間予定表コントロールの下部に表示されるをクリックして、現在の日付を返すことができます。 「今日」の文字列には、ラベルのテキストと日付のテキストが含まれています。  
  
 このメソッドは、送信、 [MCM_GETMAXTODAYWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760962) Windows SDK で説明するメッセージ。  
  
##  <a name="getminreqrect"></a>  CMonthCalCtrl::GetMinReqRect  
 月間予定表コントロールで、完全な月を表示するために必要な最小サイズを取得します。  
  
```  
BOOL GetMinReqRect(RECT* pRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pRect*  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る。 このパラメーターが有効なアドレスでなければならないし、することはできません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、このメンバー関数を 0 以外を返すと`lpRect`適切な境界情報を受信します。 失敗した場合は、このメンバー関数は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETMINREQRECT](http://msdn.microsoft.com/library/windows/desktop/bb760978)Windows SDK で説明されている。  
  
##  <a name="getmonthdelta"></a>  CMonthCalCtrl::GetMonthDelta  
 月間予定表コントロールのスクロール率を取得します。  
  
```  
int GetMonthDelta() const;  
```  
  
### <a name="return-value"></a>戻り値  
 月間予定表コントロールのスクロール率。 スクロール率とは、ユーザーが 1 回、スクロール ボタンをクリックしたときに、コントロールが表示を移動する月数です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb760980)Windows SDK で説明されている。  
  
##  <a name="getmonthrange"></a>  CMonthCalCtrl::GetMonthRange  
 日付、月間予定表コントロールの表示の高値と安値の制限を表す情報を取得します。  
  
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
 *refMinRange*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)許可される日付の最小値を含むオブジェクト。  
  
 *refMaxRange*  
 参照、`COleDateTime`または`CTime`許可される日付の最大値を含むオブジェクト。  
  
 *pMinRange*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)最も低い範囲の最後の日付を含む構造体。  
  
 *整数*  
 ポインター、`SYSTEMTIME`最も高い範囲の最後の日付を含む構造体。  
  
 *dwFlags*  
 取得する範囲の制限の範囲を指定する値。 この値は、次のいずれかにする必要があります。  
  
|[値]|説明|  
|-----------|-------------|  
|GMR_DAYSTATE|前と末尾の部分的にのみ表示される表示された範囲の月が含まれます。|  
|GMR_VISIBLE|完全に表示される月だけが含まれます。|  
  
### <a name="return-value"></a>戻り値  
 によって示される範囲を表す、月単位で 2 つの制限により展開される整数*refMinRange*と*refMaxRange*番目と 2 番目のバージョン、または*pMinRange*および*整数*3 番目のバージョンにします。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETMONTHRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760981)Windows SDK で説明されている。 MFC の実装で`GetMonthRange`を指定できます`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
### <a name="example"></a>例  
  例を参照して[CMonthCalCtrl::SetDayState](#setdaystate)です。  
  
##  <a name="getrange"></a>  CMonthCalCtrl::GetRange  
 月間予定表コントロールで設定現在の最小値と最大の日付を取得します。  
  
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
 *pMinRange*  
 ポインター、`COleDateTime`オブジェクト、`CTime`オブジェクト、または[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)最も低い範囲の最後の日付を含む構造体。  
  
 *整数*  
 ポインター、`COleDateTime`オブジェクト、`CTime`オブジェクト、または[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)最も高い範囲の最後の日付を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 A `DWORD` 0 にすることができます (制限が設定されていない) または制限情報を指定する値は次の組み合わせ。  
  
|[値]|説明|  
|-----------|-------------|  
|GDTR_MAX|コントロールの上限を設定します。*整数*が有効であり、適用可能な日付の情報が含まれています。|  
|GDTR_MIN|コントロールの最小値を設定します。*pMinRange*が有効であり、適用可能な日付の情報が含まれています。|  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760983)Windows SDK で説明されている。 MFC の実装で`GetRange`を指定することができます、`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]  
  
##  <a name="getselrange"></a>  CMonthCalCtrl::GetSelRange  
 ユーザーが現在選択されている日付範囲の上限と下限を表す日付情報を取得します。  
  
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
 *refMinRange*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)許可される日付の最小値を含むオブジェクト。  
  
 *refMaxRange*  
 参照、`COleDateTime`または`CTime`許可される日付の最大値を含むオブジェクト。  
  
 *pMinRange*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)最も低い範囲の最後の日付を含む構造体。  
  
 *整数*  
 ポインター、`SYSTEMTIME`最も高い範囲の最後の日付を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb760985)Windows SDK で説明されている。 `GetSelRange` 使用しない月間予定表コントロールに適用される場合は失敗、 **MCS_MULTISELECT**スタイル。  
  
 MFC の実装で`GetSelRange`を指定できます`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
##  <a name="gettoday"></a>  CMonthCalCtrl::GetToday  
 月間予定表コントロールの「現在」として指定された日付について日付の情報を取得します。  
  
```  
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;  
   
BOOL GetToday(LPSYSTEMTIME pDateTime) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *refDateTime*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)現在の日付を示すオブジェクト。  
  
 *pDateTime*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)日付情報を受け取る。 このパラメーターが有効なアドレスでなければならないし、することはできません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_GETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb760987)Windows SDK で説明されている。 MFC の実装で`GetToday`を指定することができます、`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]  
  
##  <a name="hittest"></a>  CMonthCalCtrl::HitTest  
 どの月間予定表コントロールは、指定した位置にある場合は、いずれかを判断します。  
  
```  
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```  
  
### <a name="parameters"></a>パラメーター  
 *pMCHitTest*  
 ポインター、 [MCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760927)月間予定表コントロールのポイントがヒット テストを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 `DWORD` 値。 等しい、 **uHit**のメンバー、 **MCHITTESTINFO**構造体。  
  
### <a name="remarks"></a>Remarks  
 `HitTest` 使用して、 **MCHITTESTINFO**ヒット テストに関する情報を格納する構造体。  
  
##  <a name="iscenturyview"></a>  CMonthCalCtrl::IsCenturyView  
 現在の月間予定表コントロールの現在のビューが 4 桁の年のビューであるかどうかを示します。  
  
```  
BOOL IsCenturyView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、現在のビューは、2 桁の年のビューです。それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) Windows SDK で説明するメッセージ。 返すかどうかはメッセージを`MCMV_CENTURY`、このメソッドが戻る`true`です。  
  
##  <a name="isdecadeview"></a>  CMonthCalCtrl::IsDecadeView  
 現在の月間予定表コントロールの現在のビューが 10 年ビューであるかどうかを示します。  
  
```  
BOOL IsDecadeView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true` 現在のビューが、10 年ビュー場合です。それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) Windows SDK で説明するメッセージ。 返すかどうかはメッセージを`MCMV_DECADE`、このメソッドが戻る`true`です。  
  
##  <a name="ismonthview"></a>  CMonthCalCtrl::IsMonthView  
 現在の月間予定表コントロールの現在のビューが月単位の表示であるかどうかを示します。  
  
```  
BOOL IsMonthView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true` 現在のビューが月のビューの場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) Windows SDK で説明するメッセージ。 返すかどうかはメッセージを`MCMV_MONTH`、このメソッドが戻る`true`です。  
  
##  <a name="isyearview"></a>  CMonthCalCtrl::IsYearView  
 現在の月間予定表コントロールの現在のビューが年のビューであるかどうかを示します。  
  
```  
BOOL IsYearView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true` 現在のビューが年のビューの場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_GETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760955) Windows SDK で説明するメッセージ。 返すかどうかはメッセージを`MCMV_YEAR`、このメソッドが戻る`true`です。  
  
##  <a name="setcalendarborder"></a>  CMonthCalCtrl::SetCalendarBorder  
 現在の月間予定表コントロールの境界線の幅を設定します。  
  
```  
void SetCalendarBorder(int cxyBorder);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*cxyBorder*|ピクセル単位で、罫線の幅。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドが成功した場合、境界線の幅に設定されている、 *cxyBorder*パラメーター。 罫線の幅は、現在指定されている既定値にリセットするそれ以外の場合、[テーマ](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)テーマが使用されない場合は 0 です。  
  
 このメソッドは、送信、 [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_monthCalCtrl`、つまり月間予定表コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>例  
 次のコード例のセット 8 ピクセルへの月間予定表の境界線の幅を制御します。 使用して、 [CMonthCalCtrl::GetCalendarBorder](#getcalendarborder)このメソッドが成功したかどうかを調べます。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]  
  
##  <a name="setcalendarborderdefault"></a>  CMonthCalCtrl::SetCalendarBorderDefault  
 現在の月間予定表コントロールの枠線の既定の幅を設定します。  
  
```  
void SetCalendarBorderDefault();
```  
  
### <a name="remarks"></a>Remarks  
 罫線の幅が現在の指定した既定値に設定されている[テーマ](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)テーマが使用されない場合は 0 です。  
  
 このメソッドは、送信、 [MCM_SETCALENDARBORDER](http://msdn.microsoft.com/library/windows/desktop/bb760993) Windows SDK で説明するメッセージ。  
  
##  <a name="setcalid"></a>  CMonthCalCtrl::SetCalID  
 現在の月間予定表コントロールのカレンダー識別子を設定します。  
  
```  
BOOL SetCalID(CALID calid);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*calid*|1 つ、[カレンダー識別子](http://msdn.microsoft.com/library/windows/desktop/dd317732)定数。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 カレンダーの識別子を指定グレゴリオ暦 (ローカライズ版)、日本語、イスラム暦などの地域に固有のカレンダーの予定表。 使用して、`SetCalID`で指定されているカレンダーを表示する方法、 *calid*パラメーターを予定表を含むロケールがコンピューターにインストールされている場合。  
  
 このメソッドは、送信、 [MCM_SETCALID](http://msdn.microsoft.com/library/windows/desktop/bb760995) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_monthCalCtrl`、つまり月間予定表コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>例  
 次のコード例では、和暦カレンダーを表示する月間予定表コントロールを設定します。 `SetCalID`暦が、コンピューターにインストールされている場合にのみ、メソッドが成功しました。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]  
  
##  <a name="setcenturyview"></a>  CMonthCalCtrl::SetCenturyView  
 2 桁の年のビューを表示する現在の月のカレンダー コントロールを設定します。  
  
```  
BOOL SetCenturyView();
```  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、 [CMonthCalCtrl::SetCurrentView](#setcurrentview)ビューを設定するメソッドを`MCMV_CENTURY`世紀のビューを表します。  
  
##  <a name="setcolor"></a>  CMonthCalCtrl::SetColor  
 月間予定表コントロールの指定した領域の色を設定します。  
  
```  
COLORREF SetColor(
    int nRegion,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>パラメーター  
 *nRegion*  
 設定するか月カレンダーの色を指定する整数値。 この値は、次のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|MCSC_BACKGROUND|か月間に表示される背景色です。|  
|MCSC_MONTHBK|月内の背景色です。|  
|MCSC_TEXT|月のテキストを表示するために使用する色です。|  
|MCSC_TITLEBK|カレンダーのタイトルに表示される背景色です。|  
|MCSC_TITLETEXT|カレンダーの表題内のテキストを表示するために使用する色です。|  
|MCSC_TRAILINGTEXT|ヘッダーと後続の日のテキストを表示するために使用する色です。 ヘッダーと後続の日現在の暦に表示される前と次の月からの日数がします。|  
  
 *ref*  
 A **COLORREF**月間予定表コントロールの指定した部分の新しい色の設定の値。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**正常終了した場合は、月間予定表コントロールの指定した部分の前のカラー設定を表す値です。 それ以外の場合は-1 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760997)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]  
  
##  <a name="setcurrentview"></a>  CMonthCalCtrl::SetCurrentView  
 指定されたビューを表示する現在の月のカレンダー コントロールを設定します。  
  
```  
BOOL SetCurrentView(DWORD dwNewView);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*dwNewView*|月単位、年間、10 年間、または 2 桁の年のビューを指定する値は次のいずれか。<br /><br /> MCMV_MONTH: 月間ビュー<br /><br /> MCMV_YEAR: 年間ビュー<br /><br /> MCMV_DECADE: 10 年間の表示<br /><br /> MCMV_CENTURY: 世紀ビュー|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、送信、 [MCM_SETCURRENTVIEW](http://msdn.microsoft.com/library/windows/desktop/bb760998) Windows SDK で説明するメッセージ。  
  
##  <a name="setcursel"></a>  か  
 月間予定表コントロールで現在選択されている日付を設定します。  
  
```  
BOOL SetCurSel(const COleDateTime& refDateTime);  
BOOL SetCurSel(const CTime& refDateTime);  
  BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>パラメーター  
 *refDateTime*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)または[CTime](../../atl-mfc-shared/reference/ctime-class.md)現在選択されている月間予定表コントロールを示すオブジェクト。  
  
 *pDateTime*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)を現在の選択項目として設定する日付を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETCURSEL](http://msdn.microsoft.com/library/windows/desktop/bb761002)Windows SDK で説明されている。 MFC の実装で`SetCurSel`を指定することができます、`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]  
  
##  <a name="setdaystate"></a>  CMonthCalCtrl::SetDayState  
 月間予定表コントロールでの日付の表示を設定します。  
  
```  
BOOL SetDayState(
    int nMonths,  
    LPMONTHDAYSTATE pStates);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMonths*  
 配列内に要素の数を示す値を*pStates*を指します。  
  
 *pStates*  
 ポインター、[月数](http://msdn.microsoft.com/library/windows/desktop/bb760915)月間予定表コントロールの表示で毎日を描画できる方法を定義する値の配列。 **月数**データ型は、ビット フィールドは、(1 ~ 31) の各ビットが 1 日に 1 か月の状態を表します。 対応する日付が表示されます、ビットがオンの場合で太字で表示します。それ以外の場合太字で表示されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETDAYSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761004)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]  
  
##  <a name="setdecadeview"></a>  CMonthCalCtrl::SetDecadeView  
 10 年間のビューに現在の月のカレンダー コントロールを設定します。  
  
```  
BOOL SetDecadeView();
```  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、 [CMonthCalCtrl::SetCurrentView](#setcurrentview)ビューを設定するメソッドを`MCMV_DECADE`、decade ビューを表します。  
  
##  <a name="setfirstdayofweek"></a>  CMonthCalCtrl::SetFirstDayOfWeek  
 予定表の左端の列に表示する曜日を設定します。  
  
```  
BOOL SetFirstDayOfWeek(
    int iDay,  
    int* lpnOld = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *iDay*  
 週の最初の日として設定するのには、曜日を表す整数値。 この値は、曜日番号のいずれかを指定する必要があります。 参照してください[については、「](#getfirstdayofweek)曜日番号の詳細についてはします。  
  
 *lpnOld*  
 以前の週の最初の日を示す整数を指すポインターを設定します。  
  
### <a name="return-value"></a>戻り値  
 週の最初の日以前は、以外の値に設定されている場合は 0 以外。 **LOCALE_IFIRSTDAYOFWEEK**、これは、コントロール パネルの設定に示されている日です。 それ以外の場合、この関数は、0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETFIRSTDAYOFWEEK](http://msdn.microsoft.com/library/windows/desktop/bb761006)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]  
  
##  <a name="setmaxselcount"></a>  CMonthCalCtrl::SetMaxSelCount  
 月間予定表コントロールで選択できる日数の最大数を設定します。  
  
```  
BOOL SetMaxSelCount(int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMax*  
 この値は、選択できる日数の最大数を表すに設定されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETMAXSELCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761008)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]  
  
##  <a name="setmonthdelta"></a>  CMonthCalCtrl::SetMonthDelta  
 月間予定表コントロールのスクロール率を設定します。  
  
```  
int SetMonthDelta(int iDelta);
```  
  
### <a name="parameters"></a>パラメーター  
 *iDelta*  
 コントロールのスクロール率として設定するか月の数。 この値が 0 の場合は、月のデルタは、コントロールに表示される月の数は、既定値にリセットされます。  
  
### <a name="return-value"></a>戻り値  
 以前のスクロール率。 スクロール率が設定されていない場合、戻り値は 0 です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETMONTHDELTA](http://msdn.microsoft.com/library/windows/desktop/bb761010)Windows SDK で説明されている。  
  
##  <a name="setmonthview"></a>  CMonthCalCtrl::SetMonthView  
 月のビューを表示する現在の月の予定表コントロールを設定します。  
  
```  
BOOL SetMonthView();
```  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、 [CMonthCalCtrl::SetCurrentView](#setcurrentview)ビューを設定するメソッドを`MCMV_MONTH`月のビューを表します。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_monthCalCtrl`、つまり月間予定表コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]  
  
### <a name="example"></a>例  
 次のコード例では、月、年、10 年間、および 2 桁の年のビューを表示する月間予定表コントロールを設定します。  
  
 [!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]  
  
##  <a name="setrange"></a>  CMonthCalCtrl::SetRange  
 月間予定表コントロールの最小値と最大許容される日付を設定します。  
  
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
 *pMinRange*  
 ポインター、`COleDateTime`オブジェクト、`CTime`オブジェクト、または[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)最も低い範囲の最後の日付を含む構造体。  
  
 *整数*  
 ポインター、`COleDateTime`オブジェクト、`CTime`オブジェクト、または`SYSTEMTIME`最も高い範囲の最後の日付を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761012)Windows SDK で説明されている。 MFC の実装で`SetRange`を指定できます`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
### <a name="example"></a>例  
  例を参照して[CMonthCalCtrl::GetRange](#getrange)です。  
  
##  <a name="setselrange"></a>  CMonthCalCtrl::SetSelRange  
 指定した日付範囲に月間予定表の選択コントロールを設定します。  
  
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
 *pMinRange*  
 ポインター、`COleDateTime`オブジェクト、`CTime`オブジェクト、または[SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)最も低い範囲の最後の日付を含む構造体。  
  
 *整数*  
 ポインター、`COleDateTime`オブジェクト、`CTime`オブジェクト、または`SYSTEMTIME`最も高い範囲の最後の日付を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETSELRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761014)Windows SDK で説明されている。 MFC の実装で`SetSelRange`を指定できます`COleDateTime`使用法、`CTime`使用法、または`SYSTEMTIME`使用法を構成します。  
  
##  <a name="settoday"></a>  CMonthCalCtrl::SetToday  
 現在の日の予定表コントロールを設定します。  
  
```  
void SetToday(const COleDateTime& refDateTime);  
void SetToday(const CTime* pDateTime);  
  void SetToday(const LPSYSTEMTIME pDateTime);
```  
  
### <a name="parameters"></a>パラメーター  
 *refDateTime*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)を現在の日付を含むオブジェクト。  
  
 *pDateTime*  
 2 番目のバージョンへのポインターで、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)現在の日付情報を含むオブジェクト。 3 番目のバージョンへのポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)現在の日付の情報を格納する構造体。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、Win32 メッセージの動作を実装して[MCM_SETTODAY](http://msdn.microsoft.com/library/windows/desktop/bb761016)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CMonthCalCtrl::GetToday](#gettoday)です。  
  
##  <a name="setyearview"></a>  CMonthCalCtrl::SetYearView  
 年のビューに現在の月のカレンダー コントロールを設定します。  
  
```  
BOOL SetYearView();
```  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、 [CMonthCalCtrl::SetCurrentView](#setcurrentview)ビューを設定するメソッドを`MCMV_YEAR`、年間のビューを表します。  
  
##  <a name="sizeminreq"></a>  CMonthCalCtrl::SizeMinReq  
 表示されるサイズの予定表コントロールの最小値を月には、1 か月が表示されます。  
  
```  
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bRepaint*  
 コントロールが再描画するかどうかを指定します。 既定では、 **TRUE**です。 場合**FALSE**、再描画するは行われません。  
  
### <a name="return-value"></a>戻り値  
 月間予定表コントロールのサイズは最小する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す`SizeMinReq`1 か月の暦の全体の月間予定表コントロールで、正常に表示されます。  
  
##  <a name="sizerecttomin"></a>  CMonthCalCtrl::SizeRectToMin  
 現在の月のカレンダー コントロールは、指定した四角形に収まるすべてのカレンダーを含めることができる最も小さな四角形を計算します。  
  
```  
LPRECT SizeRectToMin(LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*lpRect*|ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)カレンダーの必要な数を含む四角形を定義する構造体。|  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)によってサイズが小さい四角形、四角形を定義する構造が定義されている、 *lpRect*パラメーター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは計算によって指定される四角形に収まる数のカレンダー、 *lpRect*パラメーター、し、その数のカレンダーを含めることができる最も小さな四角形を返します。 実際には、このメソッドは、目的の予定表の数に合うように指定された四角形を縮小します。  
  
 このメソッドは、送信、 [MCM_SIZERECTTOMIN](http://msdn.microsoft.com/library/windows/desktop/bb761020) Windows SDK で説明するメッセージ。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDateTimeCtrl クラス](../../mfc/reference/cdatetimectrl-class.md)
