---
title: CMFCRibbonLabel クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 36b2d78bb3f1ffaefa67a062c6498c195d46336f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37042496"
---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel クラス
リボンのクリックできないテキスト ラベルを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|構築して初期化、`CMFCRibbonLabel`指定されたテキスト文字列を持つオブジェクト。|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonLabel::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|現在のリボン label 要素のアクセシビリティ データを決定します。 (上書き[cmfcribbonbutton::setaccdata](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata))。|  
  
### <a name="remarks"></a>Remarks  
 リボンのラベルを作成した後に追加パネルを呼び出して[cmfcribbonpanel::add](../../mfc/reference/cmfcribbonpanel-class.md#add)です。  
  
 クイック アクセス ツールバーをリボンのラベルを追加することはできません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxRibbonLabel.h  
  
##  <a name="cmfcribbonlabel"></a>  CMFCRibbonLabel::CMFCRibbonLabel  
 構築して初期化、 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)を指定した文字列を表示するオブジェクト。  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszText*  
 ラベルに表示されるテキストです。  
  
 [in]*bIsMultiLine*  
 `TRUE` ラベルが、複数行のラベルであることを指定するにはそれ以外の場合、`FALSE`です。  
  
##  <a name="setaccdata"></a>  CMFCRibbonLabel::SetACCData  
 現在のリボン label 要素のアクセシビリティ データを決定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParent*  
 現在のリボンのラベルの親ウィンドウを表します。  
  
 [out]*データ*  
 型のオブジェクト`CAccessibilityData`を現在のリボンのラベルのアクセシビリティ データが格納されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合、*データ*パラメーターが正常に設定された状態でリボン ラベルを現在のユーザー補助データです。 それ以外の場合、`FALSE`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)
