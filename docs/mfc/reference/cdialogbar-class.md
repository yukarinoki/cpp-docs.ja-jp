---
title: CDialogBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogBar
- AFXEXT/CDialogBar
- AFXEXT/CDialogBar::CDialogBar
- AFXEXT/CDialogBar::Create
dev_langs:
- C++
helpviewer_keywords:
- CDialogBar [MFC], CDialogBar
- CDialogBar [MFC], Create
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7dbb2d8202e9b87d2825b7d40a0dde4323246aa0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdialogbar-class"></a>CDialogBar クラス
コントロール バー内の Windows のモードレス ダイアログ ボックスの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDialogBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](#cdialogbar)|`CDialogBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogBar::Create](#create)|Windows ダイアログ バーを作成し、それにアタッチ、`CDialogBar`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 ダイアログ バーでは、tab キーでの間で標準の Windows コントロールを持つという点で ダイアログ ボックスに似ています。 別の類似性は、ダイアログ バーを表すためのダイアログ テンプレートを作成することです。  
  
 作成したり、ダイアログ バーを使用して作成および使用法と似ています、`CFormView`オブジェクト。 まず、使用して、[ダイアログ エディター](../../windows/dialog-editor.md)スタイルでダイアログ テンプレートを定義する**WS_CHILD**およびその他のスタイルはありません。 テンプレートは、スタイル**WS_VISIBLE**です。 構築するコンス トラクターの呼び出し、アプリケーション コードで、`CDialogBar`オブジェクト、し、呼び出す**作成**ダイアログ バー ウィンドウを作成し、アタッチして、`CDialogBar`オブジェクト。  
  
 詳細については`CDialogBar`、記事を参照して[ダイアログ バー](../../mfc/dialog-bars.md)と[テクニカル ノート 31](../../mfc/tn031-control-bars.md)、コントロール バーです。  
  
> [!NOTE]
>  現在のリリースで、`CDialogBar`オブジェクトは、Windows フォーム コントロールをホストできません。 Visual C での Windows フォーム コントロールの詳細については、次を参照してください。 [MFC における Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="cdialogbar"></a>  CDialogBar::CDialogBar  
 `CDialogBar` オブジェクトを構築します。  
  
```  
CDialogBar();
```  
  
##  <a name="create"></a>  CDialogBar::Create  
 指定されたダイアログ ボックス リソース テンプレートを読み込みます`lpszTemplateName`または`nIDTemplate`、ダイアログ バーのウィンドウを作成、そのスタイルを設定およびに関連付けます、`CDialogBar`オブジェクト。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
virtual BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 親へのポインター`CWnd`オブジェクト。  
  
 `lpszTemplateName`  
 名前へのポインター、`CDialogBar`オブジェクトのダイアログ ボックス リソース テンプレート。  
  
 `nStyle`  
 ツールバーのスタイル。 追加のスタイルは次のとおりです。  
  
- `CBRS_TOP` フレーム ウィンドウの上部には、コントロール バーです。  
  
- `CBRS_BOTTOM` フレーム ウィンドウの下部には、コントロール バーです。  
  
- `CBRS_NOALIGN` 親のサイズが変更されるときにコントロール バーの位置を変更できません。  
  
- `CBRS_TOOLTIPS` コントロール バーには、ツール ヒントが表示されます。  
  
- **CBRS_SIZE_DYNAMIC**コントロール バーは動的です。  
  
- **CBRS_SIZE_FIXED**コントロール バーを固定します。  
  
- **CBRS_FLOATING**コントロール バーがフローティング状態です。  
  
- `CBRS_FLYBY` ステータス バーには、ボタンについての情報が表示されます。  
  
- **CBRS_HIDE_INPLACE**コントロール バーは、ユーザーに表示されません。  
  
 `nID`  
 ダイアログ バーのコントロール ID。  
  
 `nIDTemplate`  
 リソース ID、`CDialogBar`オブジェクトのダイアログ ボックスのテンプレートです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 指定した場合、`CBRS_TOP`または`CBRS_BOTTOM`配置スタイル ダイアログ バーの幅は、フレーム ウィンドウのその高さで指定されたリソースの`nIDTemplate`します。 指定した場合、`CBRS_LEFT`または`CBRS_RIGHT`配置スタイル ダイアログ バーの高さのフレーム ウィンドウのその幅で指定されたリソースの`nIDTemplate`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCMessageMaps#13](../../mfc/reference/codesnippet/cpp/cdialogbar-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLBARS](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
