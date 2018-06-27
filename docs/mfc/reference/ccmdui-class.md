---
title: CCmdUI クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
dev_langs:
- C++
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3dd417872ab4009a9e0f6c06fc0958f5780de477
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954153"
---
# <a name="ccmdui-class"></a>CCmdUI クラス
内でのみ使用されて、`ON_UPDATE_COMMAND_UI`ハンドラー、 `CCmdTarget`-クラスを派生します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCmdUI  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdUI::ContinueRouting](#continuerouting)|コマンド ルーティング メカニズム ハンドラーのチェーンに現在のメッセージのルーティングを続行するように指示します。|  
|[関数](#enable)|有効またはこのコマンドのユーザー インターフェイスの項目を無効にします。|  
|[CCmdUI::SetCheck](#setcheck)|このコマンドのユーザー インターフェイスの項目のチェックの状態を設定します。|  
|[CCmdUI::SetRadio](#setradio)|同様に、`SetCheck`メンバー関数は、オプション ボタン グループが動作します。|  
|[CCmdUI::SetText](#settext)|このコマンドのユーザー インターフェイスの項目のテキストを設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCmdUI::m_nID](#m_nid)|ユーザー インターフェイス オブジェクトの ID。|  
|[CCmdUI::m_nIndex](#m_nindex)|ユーザー インターフェイス オブジェクトのインデックス。|  
|[CCmdUI::m_pMenu](#m_pmenu)|によって表される、メニューが指す、`CCmdUI`オブジェクト。|  
|[CCmdUI::m_pOther](#m_pother)|通知を送信したウィンドウ オブジェクトへのポインター。|  
|[CCmdUI::m_pSubMenu](#m_psubmenu)|によって表される包含のサブメニューを指す、`CCmdUI`オブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 `CCmdUI` 基本クラスはありません。  
  
 ときに、アプリケーションのユーザーをプル ダウン メニューの各メニュー項目いる必要があるかどうかを表示することが有効になっている、または無効になっています。 メニュー コマンドのターゲットが実装することでこの情報を提供する`ON_UPDATE_COMMAND_UI`ハンドラー。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、各ハンドラーのメッセージ マップ エントリと関数プロトタイプを作成するのに [プロパティ] ウィンドウを使用します。  
  
 フレームワークを検索し、それぞれを呼び出して、メニューを取り出した、ときに`ON_UPDATE_COMMAND_UI`ハンドラー、それぞれのハンドラーを呼び出す`CCmdUI`などのメンバー関数`Enable`と`Check`、し、そのフレームワーク適切に、各メニュー項目を表示します。  
  
 メニュー項目は、内のコードを変更することがなくコントロール バーのボタンやその他のコマンドのユーザー インターフェイス オブジェクトに置き換えることが、`ON_UPDATE_COMMAND_UI`ハンドラー。  
  
 次の表に、影響`CCmdUI`'s さまざまなコマンドのユーザー インターフェイスのアイテムがのメンバー関数。  
  
|ユーザー インターフェイス項目|[有効化]|SetCheck|SetRadio|SetText|  
|--------------------------|------------|--------------|--------------|-------------|  
|メニュー項目|有効または無効|オンまたはオフに|ドットを使用してチェック|項目テキストの設定|  
|ツール バー ボタン|有効または無効|選択し、この選択を解除すると、または不確定|`SetCheck` と同じ|(適用なし)|  
|ステータス バー ペイン|表示または非表示テキストは、します。|セットのポップアウトまたは通常の境界線|`SetCheck` と同じ|ウィンドウのテキストを設定します。|  
|[標準] ボタン `CDialogBar`|有効または無効|オンまたはオフにチェック ボックス|`SetCheck` と同じ|ボタン テキストの設定|  
|通常の制御 `CDialogBar`|有効または無効|(適用なし)|(適用なし)|ウィンドウのテキストを設定します。|  
  
 このクラスの使用に関する詳細は、次を参照してください。[ユーザー インターフェイス オブジェクトの更新方法](../../mfc/how-to-update-user-interface-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CCmdUI`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="continuerouting"></a>  CCmdUI::ContinueRouting  
 ハンドラーのチェーンに現在のメッセージのルーティングを続行するコマンド ルーティング メカニズムを確認するには、このメンバー関数を呼び出します。  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>Remarks  
 これは、高度なメンバー関数と組み合わせて使用する、`ON_COMMAND_EX`返すハンドラー **FALSE**です。 詳細については、次を参照してください。[テクニカル ノート 6](../../mfc/tn006-message-maps.md)です。  
  
##  <a name="enable"></a>  関数  
 有効にするにまたは、このコマンドのユーザー インターフェイスの項目を無効にするには、このメンバー関数を呼び出します。  
  
```  
virtual void Enable(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *お*  
 **TRUE** 、項目を有効にする**FALSE**を無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]  
  
##  <a name="m_nid"></a>  CCmdUI::m_nID  
 メニュー項目、ツール バー ボタンまたはによって表されるその他のユーザー インターフェイス オブジェクトの ID、`CCmdUI`オブジェクト。  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_nindex"></a>  CCmdUI::m_nIndex  
 メニュー項目、ツール バー ボタンまたはによって表されるその他のユーザー インターフェイス オブジェクトのインデックス、`CCmdUI`オブジェクト。  
  
```  
UINT m_nIndex;  
```  
  
##  <a name="m_pmenu"></a>  CCmdUI::m_pMenu  
 ポインター (の`CMenu`型) で表されるメニューに、`CCmdUI`オブジェクト。  
  
```  
CMenu* m_pMenu;  
```  
  
### <a name="remarks"></a>Remarks  
 **NULL**場合は、アイテムは、メニューではありません。  
  
##  <a name="m_psubmenu"></a>  CCmdUI::m_pSubMenu  
 ポインター (の`CMenu`型) で表される包含サブメニュー、`CCmdUI`オブジェクト。  
  
```  
CMenu* m_pSubMenu;  
```  
  
### <a name="remarks"></a>Remarks  
 **NULL**場合は、アイテムは、メニューではありません。 Sub メニュー場合は、ポップアップ*サブメニュー*ポップアップ メニューの最初の項目の ID が含まれています。 詳細については、次を参照してください。[テクニカル ノート 21](../../mfc/tn021-command-and-message-routing.md)です。  
  
##  <a name="m_pother"></a>  CCmdUI::m_pOther  
 ポインター (型の`CWnd`)、ツールバーやステータス バーなど、ウィンドウ オブジェクトへの通知を送信しました。  
  
```  
CWnd* m_pOther;  
```  
  
### <a name="remarks"></a>Remarks  
 **NULL** 、項目がメニューや以外`CWnd`オブジェクト。  
  
##  <a name="setcheck"></a>  CCmdUI::SetCheck  
 このコマンドのユーザー インターフェイスの項目を適切なチェックの状態に設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetCheck(int nCheck = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 *nCheck*  
 設定する状態の確認を指定します。 場合は 0、オフにします。場合 1 をチェックです。2 の場合、不確定な設定とします。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、メニュー項目とツール バー ボタンの動作します。 中間の状態は、ツール バー ボタンにのみ適用されます。  
  
##  <a name="setradio"></a>  CCmdUI::SetRadio  
 このコマンドのユーザー インターフェイスの項目を適切なチェックの状態に設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetRadio(BOOL bOn = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bOn`  
 **TRUE** ; 項目を有効にするそれ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数のように動作する`SetCheck`オプション グループの一部として機能しているユーザー インターフェイス項目上で動作する点を除いて、します。 項目自体、オプション ボタン グループの動作を維持する場合、グループ内の他の項目をオフにする自動はありません。  
  
##  <a name="settext"></a>  CCmdUI::SetText  
 このコマンドのユーザー インターフェイスの項目のテキストを設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 文字列へのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
