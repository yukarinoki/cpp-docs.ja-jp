---
title: CDateTimeCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80b63c6bd44b6d3606b7807913f1e3ae1b4e33f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372331"
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
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|現在の日付と時刻の選択コントロールを閉じます。|  
|[CDateTimeCtrl::Create](#create)|日付と時刻の選択コントロールを作成しにアタッチ、`CDateTimeCtrl`オブジェクト。|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|現在の日付と時刻の選択コントロールに関する情報を取得します。|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|現在の日付または時刻を表示するために必要な日付と時刻選択コントロールの適切なサイズを返します。|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|月間予定表、日付と時刻の選択コントロール内の特定部分の色を取得します。|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|取得、`CMonthCalCtrl`日付と時刻の選択コントロールに関連付けられているオブジェクト。|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|現在の日付と時刻の選択コントロールの子月間予定表コントロールで使用するフォントを取得します。|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|現在の日付と時刻の選択コントロールのスタイルを取得します。|  
|[CDateTimeCtrl::GetRange](#getrange)|日付と時刻の選択コントロールのシステム時刻が許可されている現在の最小値と最大を取得します。|  
|[CDateTimeCtrl::GetTime](#gettime)|日付と時刻の選択コントロールから現在選択されている時刻を取得し、指定した配置`SYSTEMTIME`構造体。|  
|[CDateTimeCtrl::SetFormat](#setformat)|指定した書式設定文字列に従って日付と時刻の選択コントロールの表示を設定します。|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|月間予定表、日付と時刻ピッカー コントロール内の特定部分の色を設定します。|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|日付と時刻の選択コントロールの子月間予定表コントロールで使用するフォントを設定します。|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|現在の日付と時刻の選択コントロールのスタイルを設定します。|  
|[CDateTimeCtrl::SetRange](#setrange)|日付と時刻の選択コントロールの最小値と最大の許可されているシステム時刻を設定します。|  
|[CDateTimeCtrl::SetTime](#settime)|日付と時刻の選択コントロールの時間を設定します。|  
  
## <a name="remarks"></a>コメント  
 日付と時刻の選択コントロール (DTP コントロール) では、ユーザーに日付と時刻の情報を交換する単純なインターフェイスを提供します。 このインターフェイスには、コントロールに格納されている日付と時刻の情報の部分を表示するの各フィールドが含まれています。 ユーザーは、特定のフィールドに文字列の内容を変更することで、コントロールに格納されている情報を変更できます。 ユーザーは、フィールドをマウスまたはキーボードを使用して移動できます。  
  
 作成するときに、オブジェクトにさまざまなスタイルを適用することで、日付と時刻の選択コントロールをカスタマイズできます。 参照してください[日付と時刻の選択コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761728)日付と時刻の選択コントロールに固有のスタイルの詳細については、Windows SDK でします。 形式のスタイルを使用して DTP コントロールの表示形式を設定することができます。 これらのスタイルの形式は 「形式のスタイル」Windows SDK のトピックに記載されて[日付と時刻の選択コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761728)です。  
  
 日付と時刻の選択コントロールは、通知とで説明されるコールバックにも使用[を使用して CDateTimeCtrl](../../mfc/using-cdatetimectrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>  CDateTimeCtrl::CDateTimeCtrl  
 `CDateTimeCtrl` オブジェクトを構築します。  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>  CDateTimeCtrl::CloseMonthCal  
 現在の日付と時刻の選択コントロールを閉じます。  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`、つまり、日付と時刻の選択コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の日付と時刻の選択コントロールのドロップダウン カレンダーを閉じます。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>  CDateTimeCtrl::Create  
 日付と時刻の選択コントロールを作成しにアタッチ、`CDateTimeCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 日時コントロールのスタイルの組み合わせを指定します。 参照してください[日付と時刻の選択コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761728)日付と時刻のピッカー スタイルの詳細については Windows SDK に含まれています。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)日付と時刻の選択コントロールのサイズと位置である構造体。  
  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、日付と時刻の選択コントロールの親ウィンドウです。 なければなりません**NULL**です。  
  
 `nID`  
 日付と時刻の選択コントロールのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 作成が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>日付と時刻の選択コントロールを作成するには  
  
1.  呼び出す[CDateTimeCtrl](#cdatetimectrl)構築するために、`CDateTimeCtrl`オブジェクト。  
  
2.  このメンバー関数は、Windows の日付と時刻の選択コントロールを作成しにアタッチを呼び出して、`CDateTimeCtrl`オブジェクト。  
  
 呼び出すと**作成**、コモン コントロールを初期化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>  CDateTimeCtrl::GetDateTimePickerInfo  
 現在の日付と時刻の選択コントロールに関する情報を取得します。  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pDateTimePickerInfo`|ポインター、 [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729)を現在の日付と時刻の選択コントロールの説明を受け取る構造体。<br /><br /> 呼び出し元がこの構造体を割り当てます。 ただし、このメソッドは、初期化、`cbSize`構造体のメンバーです。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`、つまり、日付と時刻の選択コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の日付と時刻の選択コントロールに関する情報が正常に取得するかどうかを示します。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>  CDateTimeCtrl::GetMonthCalColor  
 月間予定表、日付と時刻の選択コントロール内の特定部分の色を取得します。  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iColor`  
 `int`を取得するか月カレンダーの色領域を指定する値。 値の一覧は、次を参照してください。、`iColor`パラメーター [SetMonthCalColor](#setmonthcalcolor)です。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**正常終了した場合は、月間予定表コントロールの指定した部分の色の設定を表す値です。 関数は、それ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>  CDateTimeCtrl::GetMonthCalCtrl  
 取得、`CMonthCalCtrl`日付と時刻の選択コントロールに関連付けられているオブジェクト。  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)オブジェクト、または**NULL**失敗した場合、またはウィンドウが表示されない場合。  
  
### <a name="remarks"></a>コメント  
 日付と時刻のピッカー コントロールは、ユーザーがドロップダウン矢印をクリックしたときに、月間予定表の子コントロールを作成します。 ときに、`CMonthCalCtrl`オブジェクトが不要、破棄すると、アプリケーションに依存しないこと、日時指定コントロールの子の月間予定表イベントを表すオブジェクトを格納するようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>  CDateTimeCtrl::GetMonthCalFont  
 現在の日付と時刻の選択コントロールの月間予定表コントロールで使用するフォントを取得します。  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CFont](../../mfc/reference/cfont-class.md)オブジェクト、または**NULL**失敗した場合。  
  
### <a name="remarks"></a>コメント  
 `CFont`戻り値によって指されるオブジェクトは一時オブジェクトであり、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="getmonthcalstyle"></a>  CDateTimeCtrl::GetMonthCalStyle  
 現在の日付と時刻の選択コントロールに関連付けられているドロップダウン月間予定表コントロールのスタイルを取得します。  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 日付と時刻のピッカー コントロール スタイルのビットごとの組み合わせであるドロップ ダウン月間予定表コントロールの (または) のスタイルです。 詳細については、次を参照してください。[月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919)です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763) Windows SDK で説明するメッセージ。  
  
##  <a name="getrange"></a>  CDateTimeCtrl::GetRange  
 日付と時刻の選択コントロールのシステム時刻が許可されている現在の最小値と最大を取得します。  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pMinRange`  
 ポインター、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトまたは[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトで許可されている最も早い時刻を含む、`CDateTimeCtrl`オブジェクト。  
  
 `pMaxRange`  
 ポインター、`COleDateTime`オブジェクトまたは`CTime`オブジェクトで許可されている最新の時刻を含む、`CDateTimeCtrl`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`設定されている範囲を示すフラグを含む値です。 If  
  
 `return value & GDTR_MAX` == 0  
  
 2 番目のパラメーターは有効です。 同様に場合、  
  
 `return value & GDTR_MIN` == 0  
  
 最初のパラメーターは有効です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767)Windows SDK で説明されている。 MFC の実装では、いずれかを指定できます`COleDateTime`または`CTime`の使用法。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>  CDateTimeCtrl::GetTime  
 日付と時刻の選択コントロールから現在選択されている時刻を取得し、指定した配置`SYSTEMTIME`構造体。  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *timeDest*  
 最初のバージョンへの参照で、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)システム時刻の情報を受け取るオブジェクト。 2 番目のバージョンへの参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)システム時刻の情報を受け取るオブジェクト。  
  
 *pTimeDest*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)システム時刻の情報を受け取る。 ことはできません**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 時間が正常に書き込む場合は 0 以外の最初のバージョンで、`COleDateTime`オブジェクト以外の場合は 0 です。 2 番目と 3 番目のバージョンで、`DWORD`値と等しい、 **dwFlag**セットのメンバー、[戻り](http://msdn.microsoft.com/library/windows/desktop/bb761730)構造体。 参照してください、**解説**詳細については、後述の「します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769)Windows SDK で説明されている。 MFC 実装で**GetTime**、使用することができます`COleDateTime`または`CTime`を使用するか、クラス、`SYSTEMTIME`時の情報を格納する、構造体。  
  
 戻り値`DWORD`で、2 番目と 3 番目のバージョン以降、ことを示します、日付と時刻の選択コントロールが「日がない」状態に設定されているかどうかで指定されている、[戻り](http://msdn.microsoft.com/library/windows/desktop/bb761730)構造体メンバー`dwFlags`です。 Equals を値が返されます場合**GDT_NONE**、コントロールは、「日付なし」状態に設定されているしを使用して、 **DTS_SHOWNONE**スタイル。 Equals を値が返されます場合**戻り**、システム時刻が正常に移行先の場所に格納します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>  CDateTimeCtrl::GetIdealSize  
 現在の日付または時刻を表示するために必要な日付と時刻選択コントロールの適切なサイズを返します。  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `psize`|ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)コントロールの適切なサイズを格納する構造体。|  
  
### <a name="return-value"></a>戻り値  
 戻り値は常に `true` です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`、つまり、日付と時刻の選択コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、日付と時刻の選択コントロールを表示する適切なサイズを取得します。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>  CDateTimeCtrl::SetFormat  
 指定した書式設定文字列に従って日付と時刻の選択コントロールの表示を設定します。  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrFormat*  
 希望の表示を定義する形式の 0 で終わる文字列へのポインター。 このパラメーターを設定**NULL**コントロールが現在のスタイルの既定の書式指定文字列にリセットされます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
> [!NOTE]
>  ユーザー入力は、この呼び出しの成功または失敗を判断できません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>  CDateTimeCtrl::SetMonthCalColor  
 月間予定表、日付と時刻ピッカー コントロール内の特定部分の色を設定します。  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>パラメーター  
 `iColor`  
 `int` 月間予定表コントロールの設定の領域を指定する値。 この値は、次のいずれかを指定できます。  
  
|[値]|説明|  
|-----------|-------------|  
|MCSC_BACKGROUND|か月間に表示される背景色を設定します。|  
|MCSC_MONTHBK|1 か月内に表示される背景色を設定します。|  
|MCSC_TEXT|テキストを表示する、1 か月以内に使用される色を設定します。|  
|MCSC_TITLEBK|カレンダーのタイトルに表示される背景色を設定します。|  
|MCSC_TITLETEXT|カレンダーの表題内のテキストの表示に使用する色を設定します。|  
|MCSC_TRAILINGTEXT|ヘッダーと末尾の日付のテキスト表示に使用する色を設定します。 ヘッダーと後続の日現在の暦に表示される前と次の月からの日数がします。|  
  
 `ref`  
 A **COLORREF**月間予定表の指定した領域に設定する色を表す値です。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**正常終了した場合は、月間予定表コントロールの指定した部分の前のカラー設定を表す値です。 それ以外の場合、メッセージは、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
  例を参照して[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)です。  
  
##  <a name="setmonthcalfont"></a>  CDateTimeCtrl::SetMonthCalFont  
 日付と時刻の選択コントロールの子月間予定表コントロールで使用するフォントを設定します。  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFont`  
 設定されるフォントを処理します。  
  
 `bRedraw`  
 かどうか、コントロール再描画するかすぐにフォントの設定を指定します。 このパラメーターを設定**TRUE**コントロールを自動的に再描画します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775)Windows SDK で説明されている。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  このコードを使用する場合のメンバにする、 `CDialog`-と呼ばれるクラスを派生`m_MonthFont`型の**CFont**です。  
  
##  <a name="setmonthcalstyle"></a>  CDateTimeCtrl::SetMonthCalStyle  
 現在の日付と時刻の選択コントロールに関連付けられているドロップダウン月間予定表コントロールのスタイルを設定します。  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwStyle`|予定表コントロールのスタイルは、月間予定表コントロールのスタイルのビットごとの組み合わせ (OR) は、新しい月です。 詳細については、次を参照してください。[月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919)です。|  
  
### <a name="return-value"></a>戻り値  
 ドロップ ダウン月間予定表コントロールの以前のスタイル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`、つまり、日付と時刻の選択コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、週の数、日数、曜日、および今日指標を表示しないの省略名を表示する日付と時刻のピッカー コントロールを設定します。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>  CDateTimeCtrl::SetRange  
 日付と時刻の選択コントロールの最小値と最大の許可されているシステム時刻を設定します。  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMinRange`  
 ポインター、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトまたは[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトで許可されている最も早い時刻を含む、`CDateTimeCtrl`オブジェクト。  
  
 `pMaxRange`  
 ポインター、`COleDateTime`オブジェクトまたは`CTime`オブジェクトで許可されている最新の時刻を含む、`CDateTimeCtrl`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780)Windows SDK で説明されている。 MFC の実装では、いずれかを指定できます`COleDateTime`または`CTime`の使用法。 場合、`COleDateTime`オブジェクトには、 **NULL**状態、範囲が削除されます。 場合、`CTime`ポインター、または`COleDateTime`ポインターが**NULL**範囲が削除されます。  
  
### <a name="example"></a>例  
  例を参照して[CDateTimeCtrl::GetRange](#getrange)です。  
  
##  <a name="settime"></a>  CDateTimeCtrl::SetTime  
 日付と時刻の選択コントロールの時間を設定します。  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *timeNew*  
 参照、 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトを含む、コントロールを設定します。  
  
 *pTimeNew*  
 2 番目のバージョンへのポインターの上で、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)コントロールを設定する時刻を含むオブジェクト。 3 番目のバージョンへのポインターの上で、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)コントロールを設定する時刻を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782)Windows SDK で説明されている。 MFC 実装で**SetTime**、使用することができます、`COleDateTime`または`CTime`を使用するか、クラス、`SYSTEMTIME`構造、時刻情報を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl クラス](../../mfc/reference/cmonthcalctrl-class.md)
