---
title: CMFCRibbonSeparator クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bed63f6752f0335e3c1917e6597e7f8b096c8df6
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039797"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator クラス
リボンの区分線を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|`CMFCRibbonSeparator` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|区切り文字を追加、**コマンド**一覧に、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox))。|  
|`CMFCRibbonSeparator::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonSeparator::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|別のオブジェクトから区切り記号のメンバー変数を設定するコピー メソッドです。|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|区切り記号のサイズを返します。|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|これは、区切り記号であるかどうかを示します。|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|これは、タブの停止するかどうかを示します。|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|リボンまたはクイック アクセス ツールバーのいずれかの区分線を描画する、システムによって呼び出されます。|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|区分線を描画するためにシステムと呼ばれる、**コマンド** ボックスの一覧です。|  
  
## <a name="remarks"></a>Remarks  
 垂直または水平方向の行を論理的に離職リボン要素がリボンの区切り記号です。 リボン コントロール、アプリケーションのメイン メニューのリボン ステータス バー、およびクイック アクセス ツールバーの区分線を描画できます。  
  
 区切り記号を使用して、アプリケーションで、新しいオブジェクトを構築し、次に示すように、アプリケーションのメイン メニューに追加。  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
呼び出す[CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator)リボン パネルに区切り記号を追加します。 区切り記号が割り当てられ、内部で追加、`AddSeparator`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxbaseribbonelement.h  
  
##  <a name="addtolistbox"></a>  CMFCRibbonSeparator::AddToListBox  
 区切り文字を追加、**コマンド**一覧に、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWndListBox*  
 ポインター、**コマンド**区切り記号が追加された一覧です。  
  
 [in]*パラメーター bDeep*  
 無視されます。  
  
### <a name="return-value"></a>戻り値  
 0 から始まるインデックスで指定された、リスト ボックス内の文字列に*pWndListBox*です。  
  
##  <a name="cmfcribbonseparator"></a>  CMFCRibbonSeparator::CMFCRibbonSeparator  
 `CMFCRibbonSeparator` オブジェクトを構築します。  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bIsHoriz*  
 場合`TRUE`、区切り記号は横方向以外の場合は`FALSE`、区切り記号は縦方向です。  
  
### <a name="remarks"></a>Remarks  
 水平方向の区切り記号は、アプリケーションのメニューで使用されます。 垂直方向の区切り記号は、ツールバーで使用されます。  
  
### <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCRibbonSeparator`クラスです。  
  
 [!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCRibbonSeparator::CopyFrom  
 別のオブジェクトから区切り記号のメンバー変数を設定するコピー メソッドです。  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*Src*  
 コピーするソース リボン要素。  
  
##  <a name="getregularsize"></a>  CMFCRibbonSeparator::GetRegularSize  
 区切り記号のサイズを返します。  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイスのコンテンツへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたデバイス コンテキストで区切り記号のサイズ。  
  
##  <a name="isseparator"></a>  CMFCRibbonSeparator::IsSeparator  
 これは、区切り記号であるかどうかを示します。  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に`TRUE`このクラスにします。  
  
##  <a name="istabstop"></a>  CMFCRibbonSeparator::IsTabStop  
 これは、タブの停止するかどうかを示します。  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に`FALSE`このクラスにします。  
  
### <a name="remarks"></a>Remarks  
 リボンの区切り記号は、タブ ストップではないです。  
  
##  <a name="ondraw"></a>  CMFCRibbonSeparator::OnDraw  
 リボンまたはクイック アクセス ツールバーのいずれかの区分線を描画する、システムによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
##  <a name="ondrawonlist"></a>  CMFCRibbonSeparator::OnDrawOnList  
 区分線を描画するためにシステムと呼ばれる、**コマンド** ボックスの一覧です。  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pDC*|デバイス コンテキストへのポインター。|  
|[in]*strText*|一覧に表示されるテキストです。|  
|[in]*nTextOffset*|テキストと外接する四角形の左側にある間のスペースです。|  
|[in]*rect*|外接する四角形を指定します。|  
|[in]*bIsSelected*|無視されます。|  
|[in]*bHighlighted*|無視されます。|  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
