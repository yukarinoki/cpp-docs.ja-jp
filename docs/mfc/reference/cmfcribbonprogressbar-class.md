---
title: CMFCRibbonProgressBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b9d0d1ab9722b14caddc3935d820301ae229f5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369337"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar クラス
時間のかかる操作の進行状況を視覚的に示すコントロールを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|`CMFCRibbonProgressBar` オブジェクトを構築して初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|現在の進行状況を返します。|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|現在の範囲の最大値を返します。|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|現在の範囲の最小値を返します。|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します。 (上書き[cmfcribbonbaseelement::getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize))。|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|進行状況バーが無限のモードで動作しているかどうかを指定します。|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 (上書き[cmfcribbonbaseelement::ondraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw))。|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|無限のモードで動作する進行状況バーを設定します。|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|現在の進行状況を設定します。|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|最小値と最大値を設定します。|  
  
## <a name="remarks"></a>コメント  
 A `CMFCRibbonProgressBar` 2 つのモードで動作できます。 標準と無限です。 通常モードでは、進行状況バーが左から右に入力され、最大値に達すると停止します。 無限のモードでは、進行状況バーが繰り返し最小値から最大値に入力されます。 操作が進行中であるが、完了時刻が不明であるを示すために無限モードを使用する可能性があります。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCRibbonProgressBar`クラスです。 例は、進行状況バーの最小値と最大値を設定し、進行状況バーの現在の位置を設定 (ここで、操作の完了時間が不明) 無限モードで動作する進行状況バーを設定する方法を示します。 このコード スニペットの一部である、 [MS Office 2007 デモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 構築して初期化、 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)オブジェクト。  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 リボンの進行状況バーのコマンド ID を指定します。  
  
 [入力] `nWidth`  
 リボンの進行状況バーのピクセル単位の幅を指定します。  
  
 [入力] `nHeight`  
 リボンの進行状況バーのピクセル単位の高さを指定します。  
  
##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos  
 進行状況バーの現在の位置を返します。  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バーの現在の位置を表す値。  
  
### <a name="remarks"></a>コメント  
 設定されている範囲がで指定された範囲内である必要があります、 [CMFCRibbonProgressBar::SetRange](#setrange)メソッドです。  
  
##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax  
 返します、進行状況バーの現在の最大値。  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の範囲の最大値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin  
 返します、進行状況バーの現在の最小範囲値です。  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在の範囲の最小値。  
  
##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode  
 進行状況バーが無限のモードで動作しているかどうかを指定します。  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 進行状況バーが無限モードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 無限のモードでは、進行状況バーは、最小値から最大値に繰り返し塗りつぶされます。 操作が進行中であるが、完了時刻が不明であるを示すために無限モードを使用する可能性があります。  
  
##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode  
 無限のモードで動作する進行状況バーを設定します。  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 `TRUE` 進行状況バーが無限モードであることを指定するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 通常、進行状況バーが無限モードである場合は、それをユーザーに通知操作が進行中であるが、完了時刻が不明であります。 したがって、進行状況バー繰り返し塗りつぶさ最小値から最大値にします。  
  
##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos  
 進行状況バーの現在の位置を設定します。  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nPos`  
 進行状況バーが設定されている位置を指定します。  
  
 [入力] `bRedraw`  
 進行状況バーを再描画されるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 設定されている範囲がで指定された範囲内である必要があります、 [CMFCRibbonProgressBar::SetRange](#setrange)メソッドです。  
  
##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange  
 進行状況バーの最小値と最大値を設定します。  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMin`  
 範囲の最小値を指定します。  
  
 [入力] `nMax`  
 範囲の最大値を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、最小値と最大値を設定して、進行状況バーの範囲を定義します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
