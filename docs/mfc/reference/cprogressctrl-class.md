---
title: CProgressCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6317ce9484cc471611762d10e6f1482f24c2742a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cprogressctrl-class"></a>CProgressCtrl クラス
Windows コモン プログレス バー コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|`CProgressCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CProgressCtrl::Create](#create)|進行状況バー コントロールを作成し、それにアタッチ、`CProgressCtrl`オブジェクト。|  
|[CProgressCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用して進行状況コントロールを作成しにアタッチ、`CProgressCtrl`オブジェクト。|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|現在の進行状況バー コントロールの進行状況インジケーターのバーの色を取得します。|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|現在の進行状況バーの背景色を取得します。|  
|[CProgressCtrl::GetPos](#getpos)|進行状況バーの現在の位置を取得します。|  
|[CProgressCtrl::GetRange](#getrange)|進行状況バー コントロールの範囲の下限と上限の制限を取得します。|  
|[Cprogressctrl::getstate](#getstate)|現在の進行状況バー コントロールの状態を取得します。|  
|[CProgressCtrl::GetStep](#getstep)|現在の進行状況バー コントロールの進行状況バーのステップの増分値を取得します。|  
|[CProgressCtrl::OffsetPos](#offsetpos)|指定された増分での進行状況バー コントロールの現在位置を進めます、新しい位置を反映するバーを再描画します。|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|現在の進行状況バー コントロールの進行状況インジケーターのバーの色を設定します。|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|進行状況バーの背景色を設定します。|  
|[CProgressCtrl::SetMarquee](#setmarquee)|現在の進行状況バー コントロールのスクロール文字モード オンまたはオフをオンにします。|  
|[CProgressCtrl::SetPos](#setpos)|進行状況バー コントロールの現在位置を設定し、新しい位置を反映するバーを再描画します。|  
|[CProgressCtrl::SetRange](#setrange)|進行状況バー コントロールの最小値と最大の範囲を設定し、新しい範囲を反映するためにバーを再描画します。|  
|[CProgressCtrl::SetState](#setstate)|現在の進行状況バー コントロールの状態を設定します。|  
|[増分](#setstep)|進行状況バー コントロールのステップの増分値を指定します。|  
|[CProgressCtrl::StepIt](#stepit)|進行状況バー コントロールの現在位置を進めますステップの増分 (を参照してください[SetStep](#setstep)) し、新しい位置を反映するためにバーを再描画します。|  
  
## <a name="remarks"></a>コメント  
 進行状況バー コントロールは、アプリケーションは、時間のかかる操作の進行状況を示すために使用できるウィンドウです。 塗りつぶされて、左から右、システムで強調表示色として処理の進行状況に四角形で構成されます。  
  
 進行状況バー コントロールは、範囲と、現在の位置がします。 範囲は、操作の総実行時間を表し、現在の位置が、アプリケーションが行った操作の完了に向けた進行状況を表します。 ウィンドウ プロシージャは、範囲と現在の位置を使用して、強調表示色で塗りつぶすに進行状況バーの割合を決定します。 範囲と現在の位置の値が符号付き整数として表されるので、可能な範囲の現在位置の値は-2,147, 483,648 から 2,147, 483,647 包括的です。  
  
 使用する方法について`CProgressCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CProgressCtrl](../../mfc/using-cprogressctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl  
 `CProgressCtrl` オブジェクトを構築します。  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CProgressCtrl`オブジェクトを呼び出す`CProgressCtrl::Create`進行状況バー コントロールを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>  CProgressCtrl::Create  
 進行状況バー コントロールを作成し、それにアタッチ、`CProgressCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 進行状況バー コントロールのスタイルを指定します。 ウィンドウ stylesdescribed 内の任意の組み合わせを適用[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)に加えて、次の進行状況バー コントロールのスタイルをコントロールには、Windows sdk に。  
  
- `PBS_VERTICAL` 表示は、進行状況を垂直方向に、上下からです。 このフラグを設定しない進行状況バー コントロールは水平方向に、左を右側に表示します。  
  
- `PBS_SMOOTH` 段階的な smooth、進行状況バー コントロールに入力を表示します。 このフラグを設定しないコントロールでブロックで埋められます。  
  
 `rect`  
 進行状況バー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。 指定された座標のクライアント領域に対する相対パス、コントロールは、子ウィンドウを指定する必要があります、ため、`pParentWnd`です。  
  
 `pParentWnd`  
 通常、進行状況バー コントロールの親ウィンドウを指定します、`CDialog`です。 なければなりません**NULL です。**  
  
 `nID`  
 進行状況バー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合、`CProgressCtrl`オブジェクトが正常に作成されたそれ以外の**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CProgressCtrl` 2 つのステップ内のオブジェクト。 最初に、作成コンス トラクターを呼び出し、`CProgressCtrl`オブジェクト、およびを呼び出す**作成**、進行状況バー コントロールを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>  CProgressCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成しに関連付けます、`CProgressCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 `dwStyle`  
 進行状況バー コントロールのスタイルを指定します。 説明されているウィンドウ スタイルの任意の組み合わせを適用[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK に含まれています。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体`pParentWnd`です。  
  
 `pParentWnd`  
 コントロールの親であるウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル「はじめに」で指定された Windows の拡張スタイルを適用する**ws_ex**です。  
  
##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor  
 現在の進行状況バー コントロールの進行状況インジケーターのバーの色を取得します。  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 として表される、現在の進行状況バーの色、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値、または`CLR_DEFAULT`進行状況インジケーターのバーの色が既定の色である場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826) Windows SDK で説明するメッセージ。  
  
##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor  
 現在の進行状況バーの背景色を取得します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 として表される、現在の進行状況バーの背景色、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828) Windows SDK で説明するメッセージ。  
  
##  <a name="getpos"></a>  CProgressCtrl::GetPos  
 進行状況バーの現在の位置を取得します。  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの位置。  
  
### <a name="remarks"></a>コメント  
 進行状況バー コントロールの位置が、画面上の物理的な場所ではありませんではなく、上部と下部の範囲に示されている[SetRange](#setrange)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>  CProgressCtrl::GetRange  
 現在の下限と上限の制限または進行状況バー コントロールの範囲を取得します。  
  
```  
void GetRange(
    int& nLower,  
    int& nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLower`  
 進行状況バー コントロールの最小値を受け取る整数への参照。  
  
 `nUpper`  
 進行状況バー コントロールの数の上限を受け取る整数への参照。  
  
### <a name="remarks"></a>コメント  
 この関数によって参照される整数への下限および上限の値をコピーする`nLower`と`nUpper`、それぞれします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>  Cprogressctrl::getstate  
 現在の進行状況バー コントロールの状態を取得します。  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 これは、次の値のいずれか、現在の進行状況バー コントロールの状態。  
  
|[値]|状態|  
|-----------|-----------|  
|`PBST_NORMAL`|処理中|  
|`PBST_ERROR`|Error|  
|`PBST_PAUSED`|一時停止|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の進行状況バー コントロールの状態を取得します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>  CProgressCtrl::GetStep  
 現在の進行状況バー コントロールの進行状況バーのステップの増分値を取得します。  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バーの増分値です。  
  
### <a name="remarks"></a>コメント  
 ステップの増分値は、大量の呼び出し[CProgressCtrl::StepIt](#stepit)進行状況バーの現在の位置が増加します。  
  
 このメソッドは、送信、 [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の進行状況バー コントロールの増分値を取得します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos  
 指定された増分値で、進行状況バー コントロールの現在位置を進めます`nPos`し、新しい位置を反映するためにバーを再描画します。  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 位置を進めます量。  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの直前の位置。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor  
 現在の進行状況バー コントロールの進行状況インジケーターのバーの色を設定します。  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `clrBar`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)新しい進行状況インジケーターのバーの色を指定する値。 指定`CLR_DEFAULT`既定の色を使用する進行状況バーが発生します。|  
  
### <a name="return-value"></a>戻り値  
 として表される、進行状況インジケーターのバーの前のカラー、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値、または`CLR_DEFAULT`バーの色、進行状況インジケーターが既定の色である場合。  
  
### <a name="remarks"></a>コメント  
 `SetBarColor`メソッドは、進行状況バーの場合にのみ、色を設定、 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)][テーマ](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)は無効です。  
  
 このメソッドは、送信、 [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、赤、緑、青、または既定値を進行状況バーの色を変更します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor  
 進行状況バーの背景色を設定します。  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrNew`  
 A **COLORREF**新しい背景色を指定する値。 指定して、`CLR_DEFAULT`進行状況バーの既定の背景色を使用する値。  
  
### <a name="return-value"></a>戻り値  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)前の背景色を示す値または**とき**場合は、既定の色の背景色はします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee  
 現在の進行状況バー コントロールのスクロール文字モード オンまたはオフをオンにします。  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fMarqueeMode`|`true` マーキー モードをオンにするか、`false`マーキー モードをオフにします。|  
|[入力] `nInterval`|Marquee アニメーションの更新間隔 (ミリ秒) の時間です。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に `true` を返します。  
  
### <a name="remarks"></a>コメント  
 マーキーのモードがオンになっていると、進行状況バーがアニメーション化、ようにスクロール シアター marquee にサインインします。  
  
 このメソッドは、送信、 [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、開始時およびマーキー スクロール アニメーションを停止します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>  CProgressCtrl::SetPos  
 バーのコントロールの現在位置で指定された進行状況を設定`nPos`し、新しい位置を反映するためにバーを再描画します。  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 進行状況バー コントロールの新しい位置。  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの直前の位置。  
  
### <a name="remarks"></a>コメント  
 進行状況バー コントロールの位置が、画面上の物理的な場所ではありませんではなく、上部と下部の範囲に示されている[SetRange](#setrange)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>  CProgressCtrl::SetRange  
 進行状況バー コントロールの範囲の上限と下限を設定し、新しい範囲を反映するためにバーを再描画します。  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLower`  
 範囲の下限を指定します (既定値は 0) です。  
  
 `nUpper`  
 範囲の数の上限を指定します (既定値は 100)。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は`SetRange32`プログレス コントロールの 32 ビット範囲を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="setstate"></a>  CProgressCtrl::SetState  
 現在の進行状況バー コントロールの状態を設定します。  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iState`|進行状況バーに設定する状態。 次のいずれかの値を使用します。<br /><br /> - `PBST_NORMAL` 進行状況の<br />- `PBST_ERROR` -エラー<br />- `PBST_PAUSED` -一時停止|  
  
### <a name="return-value"></a>戻り値  
 現在の進行状況バー コントロールの直前の状態。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850) Windows SDK で説明するメッセージ。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例は、現在の進行状況バー コントロールの状態を一時停止または処理中に設定します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>  増分  
 進行状況バー コントロールのステップの増分値を指定します。  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStep*  
 新しいステップの増分します。  
  
### <a name="return-value"></a>戻り値  
 前のステップの増分します。  
  
### <a name="remarks"></a>コメント  
 ステップの増分値は、量への呼び出し`CProgressCtrl::StepIt`増加進行状況バーの現在の位置。  
  
 既定の増分は 10 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>  CProgressCtrl::StepIt  
 ステップの増分での進行状況バー コントロールの現在位置を進めます、新しい位置を反映するバーを再描画します。  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの直前の位置。  
  
### <a name="remarks"></a>コメント  
 によってステップの増分値を設定、`CProgressCtrl::SetStep`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


