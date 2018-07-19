---
title: CMFCRibbonCustomizePropertyPage クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 542c34fc02eca1f090072f49b9688d3edd4d78e6
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040676"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage クラス
カスタム ページを実装して、**カスタマイズ**リボン ベースのアプリケーション ダイアログ ボックス。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|カスタム カテゴリを追加、**コマンド**コンボ ボックス。|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|ユーザーがクリックすると、システムによって呼び出されます**OK**上、**カスタマイズ** ダイアログ ボックス。|  
  
## <a name="remarks"></a>Remarks  
 カスタム コマンドを追加する場合、**カスタマイズ**ダイアログ ボックスで、AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理する必要があります。 メッセージ ハンドラーでインスタンス化、`CMFCRibbonCustomizePropertyPage`スタック上のオブジェクト。 カスタムのコマンドの一覧を作成し、呼び出す`AddCustomCategory`に新しいページを追加する、**カスタマイズ** ダイアログ ボックス。  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCRibbonCustomizePropertyPage`オブジェクトと、カスタム カテゴリを追加します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribboncustomizedialog.h  
  
##  <a name="addcustomcategory"></a>  CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 カスタム カテゴリを追加、**コマンド**コンボ ボックス。  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*lpszName*|カスタムのカテゴリの名前を指定します。|  
|[in]*lstIDS*|カスタムのカテゴリに表示されるリボン コマンド Id が含まれています。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、という名前のカテゴリを追加*lpszName*を**コマンド**コンボ ボックス。 コマンドがで指定されたユーザーは、カテゴリを選択するときに*lstIDS*コマンドの一覧に表示されます。  
  
##  <a name="cmfcribboncustomizepropertypage"></a>  CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 `CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pRibbonBar*  
 対象のリボン コントロールへのポインターをカスタマイズするオプションです。  
  
##  <a name="onok"></a>  CMFCRibbonCustomizePropertyPage::OnOK  
 ユーザーがクリックしたときに、システムによって Calleld **ok**上、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Remarks  
 既定の実装で選択したオプションの適用、**カスタマイズ**クイック アクセス ツールバーに ダイアログ ボックス。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
