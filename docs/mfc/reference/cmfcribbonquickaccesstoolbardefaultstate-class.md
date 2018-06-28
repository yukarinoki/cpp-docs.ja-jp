---
title: CMFCRibbonQuickAccessToolBarDefaultState クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9fd8c983e0133644b6531e87f5fc1dec0fdc7b7
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041806"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState クラス
リボン バー上に配置されるクイック アクセス ツールバーの既定の状態を管理するヘルパー クラス ( [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md))。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonQuickAccessToolBarDefaultState  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|`CMFCRibbonQuickAccessToolbarDefaultState` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)|既定の状態をクイック アクセス ツールバーのコマンドを追加します。 これは、ツールバー自体を変更するものではありません。|  
|[CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom](#copyfrom)|クイック アクセス ツールバーの 1 つのプロパティを別にコピーします。|  
|[CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll](#removeall)|クイック アクセス ツールバーからすべてのコマンドを削除します。 これは、ツールバー自体を変更するものではありません。|  
  
## <a name="remarks"></a>Remarks  
 呼び出すことによって、既定の状態を設定することをお勧め、アプリケーションのクイック アクセス ツールバーを作成した後[CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)です。 ユーザーがクリックしたときに、この既定の状態が復元された、**リセット**ボタンをクリックして、**カスタマイズ**、アプリケーションのページ**オプション** ダイアログ ボックス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)  
  
## <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCRibbonQuickAccessToolbarDefaultState`クラスと既定の状態をクイック アクセス ツールバーのコマンドを追加する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribbonquickaccesstoolbar.h  
  
##  <a name="addcommand"></a>  CMFCRibbonQuickAccessToolBarDefaultState::AddCommand  
 既定の状態をクイック アクセス ツールバーのコマンドを追加します。  
  
```  
void AddCommand(
    UINT uiCmd,  
    BOOL bIsVisible=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *[in] uiCmd*  
 コマンド ID を指定します  
  
 *[in] bIsVisible*  
 クイック アクセス ツールバーが既定の状態のときは、コマンドの可視性を設定します。  
  
### <a name="remarks"></a>Remarks  
 CMFCRibbonQuickAccessToolBarDefaultState にコマンドを追加するには、3 つの結果が実現しています。 最初に、追加した各コマンドは、クイック アクセス ツールバーの右側にあるドロップダウン リストに表示されます。 この方法で、ユーザーが簡単に追加またはクイック アクセス ツールバーからコマンドを削除できます。 記載されているコマンドのみ表示するよう既定の状態のときに表示する、ユーザーがクリックしたクイック アクセス ツールバーをリセットする 2 番目に、**リセット**ボタンをクリックして、**カスタマイズ** ダイアログ ボックス。 3 番目、いないを呼び出した場合[CMFCRibbonBar::SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)、クイック アクセス ツールバーを使用してこの一覧から表示されるコマンド既定の表示コマンドと初めてユーザーがアプリケーションを実行します。 使用するすべてのコマンドを追加した後に呼び出す[CMFCRibbonBar::SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)リボン バーのクイック アクセス ツールバーの既定の状態としてこのインスタンスを設定します。  
  
##  <a name="copyfrom"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom  
 クイック アクセス ツールバーの 1 つのプロパティを別にコピーします。  
  
```  
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*src*  
 ソースへの参照を`CMFCRibbonQuickAccessToolBarDefaultState`からコピー先のオブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドでは、各コマンドをコピー元の`CMFCRibbonQuickAccessToolBarDefaultState`オブジェクトをこのオブジェクトを使用して、 [CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)メソッドです。  
  
##  <a name="cmfcribbonquickaccesstoolbardefaultstate"></a>  CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState  
 クイック アクセス ツールバーの既定の状態オブジェクトを構築します。  
  
```  
CMFCRibbonQuickAccessToolBarDefaultState();
```  
  
### <a name="remarks"></a>Remarks  
 既定では、一連のコマンドの新しいインスタンス[CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)が含まれていますが空です。  
  
##  <a name="removeall"></a>  CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll  
 クイック アクセス ツールバーの既定のコマンドの一覧をクリアします。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Remarks  
 この関数がこのインスタンスからすべてのコマンドを削除する前の呼び出し[CMFCRibbonQuickAccessToolBarDefaultState::AddCommand](#addcommand)を追加します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
