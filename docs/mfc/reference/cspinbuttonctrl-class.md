---
title: CSpinButtonCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ddf8e6530530552a4ef7b811698c816352f7719c
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122968"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl クラス
Windows コモン スピン ボタン コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|`CSpinButtonCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|スピン ボタン コントロールを作成し、それにアタッチ、`CSpinButtonCtrl`オブジェクト。|  
|[CSpinButtonCtrl::CreateEx](#createex)|指定された Windows 拡張スタイルでスピン ボタン コントロールを作成しにアタッチ、`CSpinButtonCtrl`オブジェクト。|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|スピン ボタン コントロールのアクセラレータの情報を取得します。|  
|[CSpinButtonCtrl::GetBase](#getbase)|スピン ボタン コントロールの現在の基数を取得します。|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|現在の連動ウィンドウへのポインターを取得します。|  
|[CSpinButtonCtrl::GetPos](#getpos)|スピン ボタン コントロールの現在の位置を取得します。|  
|[CSpinButtonCtrl::GetRange](#getrange)|スピン ボタン コントロールの上限と下限制限 (範囲) を取得します。|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|スピン ボタン コントロールのアクセラレータを設定します。|  
|[CSpinButtonCtrl::SetBase](#setbase)|スピン ボタン コントロールの基本クラスを設定します。|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|スピン ボタン コントロールの連動ウィンドウを設定します。|  
|[CSpinButtonCtrl::SetPos](#setpos)|コントロールの現在の位置を設定します。|  
|[上限値と下限](#setrange)|スピン ボタン コントロールの上限と下限制限 (範囲) を設定します。|  
  
## <a name="remarks"></a>Remarks  
 「スピン ボタン コントロール」(アップダウン コントロールとも呼ばれます) は、ユーザーがスクロール位置または横にあるコントロールに表示される番号など、値を増減するクリックしてできる矢印ボタンのペアです。 スピン ボタン コントロールに関連付けられている値には、現在の位置が呼び出されます。 スピン ボタン コントロールは、「buddy ウィンドウ」と呼ばれる、横にあるコントロールでよく使用されます。  
  
 このコントロール (したがって、`CSpinButtonCtrl`クラス) は、Windows 95/98 および Windows NT 3.51 の下で実行されているプログラムにのみ使用可能な以降。  
  
 スピン ボタン コントロールとその関連ウィンドウは、ユーザーに、多くの場合、1 つのコントロールのようになります。 スピン ボタン コントロールを自動的に配置自体の連動ウィンドウの横にあると、現在の位置を関連ウィンドウのキャプションは自動的に設定するを指定することができます。 エディット コントロールでスピン ボタン コントロールを使用すると、数値入力するプロンプトが表示されます。  
  
 最大に向かって現在の位置を移動上矢印をクリックし、最小に向かって現在の位置を移動、下矢印をクリックします。 既定では、最小値は 100 と最大値は 0 です。 最小値の設定が (たとえば、ときに、既定の設定が使用されます) を設定し、上向きの矢印増減をクリックすると最大値より大きい場合は位置の値と下向きの矢印をクリックすると増大にします。  
  
 関連ウィンドウなしのスピン ボタン コントロールは、簡略化されたスクロール バーの一種として機能します。 たとえば、タブ コントロールでは、スピン ボタン コントロールを追加のタブをスクロールして表示するユーザーを有効にする場合がありますが表示されます。  
  
 使用する方法について`CSpinButtonCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="create"></a>  CSpinButtonCtrl::Create  
 スピン ボタン コントロールを作成し、それにアタッチ、`CSpinButtonCtrl`オブジェクト.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロールのスタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルが説明されている[アップダウン コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb759885)Windows SDK に含まれています。  
  
 *rect*  
 スピン ボタン コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体  
  
 *pParentWnd*  
 スピン ボタン コントロールの親ウィンドウを通常へのポインター、`CDialog`です。 NULL は指定できません。  
  
 *nID*  
 スピン ボタン コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築する、`CSpinButtonCtrl`まずオブジェクトの 2 つの手順で、コンス トラクターを呼び出しておよびを呼び出す`Create`、スピン ボタン コントロールを作成しにアタッチする、`CSpinButtonCtrl`オブジェクト。  
  
 拡張ウィンドウ スタイルを使用して、スピン ボタン コントロールを作成するには、呼び出す[CSpinButtonCtrl::CreateEx](#createex)の代わりに`Create`です。  
  
##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成しに関連付けます、`CSpinButtonCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 *dwStyle*  
 スピン ボタン コントロールのスタイルを指定します。 スピン ボタン コントロールのスタイルの任意の組み合わせをコントロールに適用されます。 これらのスタイルが説明されている[アップダウン コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb759885)Windows SDK に含まれています。  
  
 *rect*  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するウィンドウの位置とサイズを記述する構造体*pParentWnd*です。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`CreateEx`の代わりに[作成](#create)Windows 拡張スタイル preface WS_EX で指定された、Windows の拡張スタイルを適用します。  
  
##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl  
 `CSpinButtonCtrl` オブジェクトを構築します。  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel  
 スピン ボタン コントロールのアクセラレータの情報を取得します。  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nAccel*  
 指定された配列の要素数*pAccel*です。  
  
 *pAccel*  
 配列を指すポインター [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897)アクセラレータの情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 アクセラレータの構造体の数を取得します。  
  
##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase  
 スピン ボタン コントロールの現在の基数を取得します。  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の基本値。  
  
##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy  
 現在の連動ウィンドウへのポインターを取得します。  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の連動ウィンドウへのポインター。  
  
##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos  
 スピン ボタン コントロールの現在の位置を取得します。  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpbError*  
 値の場合は 0 に設定されているブール値へのポインターは、正常に取得されたか、0 以外のエラーが発生した場合です。 このパラメーターが NULL に設定されている場合、エラーは報告されません。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンでは、下位ワードに 16 ビットの現在位置を返します。 上位ワードは、エラーが発生した場合は 0 以外です。  
  
 2 番目のバージョンでは、32 ビットの位置を返します。  
  
### <a name="remarks"></a>Remarks  
 返される値を処理するとき、コントロールが連動ウィンドウのキャプションに基づく現在の位置を更新します。 コントロールは、関連ウィンドウがない場合、またはキャプションを無効または範囲外の値を指定する場合に、エラーを返します。  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 スピン ボタン コントロールの上限と下限制限 (範囲) を取得します。  
  
```  
DWORD GetRange() const;  
  
void GetRange(
    int& lower,  
    int& upper) const;  
  
void GetRange32(
    int& lower,  
    int &upper) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *低い*  
 コントロールの下限値を受け取る整数への参照。  
  
 *上限*  
 コントロールの数の上限を受け取る整数への参照。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンでは、上限と下限を表す 32 ビット値を返します。 下位ワードは、コントロールの数の上限で、上位ワードは下限です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は`GetRange32`32 ビット整数値として、スピン ボタン コントロールの範囲を取得します。  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 スピン ボタン コントロールのアクセラレータを設定します。  
  
```  
BOOL SetAccel(
    int nAccel,  
    UDACCEL* pAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 *nAccel*  
 数[UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897)構造体で指定された*pAccel*です。  
  
 *pAccel*  
 アクセラレータの情報を含む UDACCEL 構造体の配列へのポインター。 要素がに基づいて昇順で並べ替えられます、`nSec`メンバー。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 スピン ボタン コントロールの基本クラスを設定します。  
  
```  
int SetBase(int nBase);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBase*  
 コントロールの新しい基本値。 10 は 10 進数または 16 の 16 進数を指定できます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、前の基本値または 0 の場合は、無効な base を指定します。  
  
### <a name="remarks"></a>Remarks  
 ベース値は、関連ウィンドウが 10 進数または 16 進数の桁の数値を表示するかを判断します。 16 進数は、常に符号付きです。10 進数は署名されます。  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 スピン ボタン コントロールの連動ウィンドウを設定します。  
  
```  
CWnd* SetBuddy(CWnd* pWndBuddy);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndBuddy*  
 新しい関連ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 以前の連動ウィンドウへのポインター。  
  
### <a name="remarks"></a>Remarks  
 スピン コントロールが、編集コントロールは、一部のコンテンツを表示するなど、別のウィンドウに関連付けではほとんどの場合です。 この他のウィンドウは、スピン コントロールの「メンバー」と呼ばれます。  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 スピン ボタン コントロールの現在位置を設定します。  
  
```  
int SetPos(int nPos);  
int SetPos32(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPos*  
 コントロールの新しい位置。 この値は、コントロールの上限と下限で指定された範囲である必要があります。  
  
### <a name="return-value"></a>戻り値  
 前の位置 (16 ビット単位の精度`SetPos`、32 ビットの有効桁数`SetPos32`)。  
  
### <a name="remarks"></a>Remarks  
 `SetPos32` 32 ビットの位置を設定します。  
  
##  <a name="setrange"></a>  上限値と下限  
 スピン ボタン コントロールの上限と下限制限 (範囲) を設定します。  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 *上限値*と*下限*  
 コントロールの上限と下限です。 `SetRange`どちらの制限は UD_MAXVAL より長くすること、または UD_MINVAL; より小さいさらに、2 つの制限の違いできません ud_maxval です。 `SetRange32` 制限内での制限は配置なし任意の整数を使用します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は`SetRange32`スピン ボタン コントロールの 32 ビット範囲を設定します。  
  
> [!NOTE]
>  スピン ボタンの既定の範囲は、ゼロ (0) に設定した最大値、最小値が 100 に設定します。 最大値は最小値よりも小さいため、上向きの矢印をクリックすると低下し、は、位置、下矢印をクリックすると向上します。 使用して`CSpinButtonCtrl::SetRange`をこれらの値を調整します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl クラス](../../mfc/reference/csliderctrl-class.md)
