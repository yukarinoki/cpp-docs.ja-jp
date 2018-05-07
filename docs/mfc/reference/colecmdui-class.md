---
title: COleCmdUI クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCmdUI
- AFXDOCOBJ/COleCmdUI
- AFXDOCOBJ/COleCmdUI::COleCmdUI
- AFXDOCOBJ/COleCmdUI::Enable
- AFXDOCOBJ/COleCmdUI::SetCheck
- AFXDOCOBJ/COleCmdUI::SetText
dev_langs:
- C++
helpviewer_keywords:
- COleCmdUI [MFC], COleCmdUI
- COleCmdUI [MFC], Enable
- COleCmdUI [MFC], SetCheck
- COleCmdUI [MFC], SetText
ms.assetid: a2d5ce08-6657-45d3-8673-2a9f32d50eec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e6195735c25bb188449638750f6100869a44f082
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="colecmdui-class"></a>COleCmdUI クラス
アプリケーションの `IOleCommandTarget`ドリブンの機能に関連するユーザー インターフェイス オブジェクトの状態を更新するメソッドを MFC に提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleCmdUI : public CCmdUI  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleCmdUI::COleCmdUI](#colecmdui)|`COleCmdUI` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleCmdUI::Enable](#enable)|設定または有効にするコマンド フラグをクリアします。|  
|[COleCmdUI::SetCheck](#setcheck)|オン/オフ切り替えの状態を設定コマンド。|  
|[COleCmdUI::SetText](#settext)|コマンドのテキストの名前または状態文字列を返します。|  
  
## <a name="remarks"></a>コメント  
 有効になっていない DocObjects、ユーザーが、アプリケーションでは、MFC のプロセスで、メニューを表示すると、アプリケーションで**UPDATE_COMMAND_UI**通知します。 各通知、 [CCmdUI](../../mfc/reference/ccmdui-class.md)特定のコマンドの状態を反映するように操作できるオブジェクト。 ただし、アプリケーションは DocObjects の有効な場合、MFC 処理**UPDATE_OLE_COMMAND_UI**通知および割り当てます`COleCmdUI`オブジェクト。  
  
 `COleCmdUI` コマンド (など、という名前、開く、印刷、およびなど)、そのコンテナーのユーザー インターフェイスを受信する DocObject をでき、DocObject のユーザー インターフェイスに送られたコマンドを受信するためのコンテナーです。 `IDispatch` 、同じコマンドをディスパッチすることできます`IOleCommandTarget`クエリを実行し、標準的な一連の引数を指定せずに通常のコマンドに依存していると、型情報は必要ありませんので、実行する簡単な方法を提供します。 `COleCmdUI` 有効にする、更新、および DocObject ユーザー インターフェイスのコマンドの他のプロパティを設定するために使用します。 コマンドを呼び出す場合は、呼び出す[COleServerDoc::OnExecOleCmd](../../mfc/reference/coleserverdoc-class.md#onexecolecmd)です。  
  
 DocObjects については、次を参照してください。[関数](../../mfc/reference/cdocobjectserver-class.md)と[CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)です。 参照してください[インターネットの最初の手順: Active ドキュメント](../../mfc/active-documents-on-the-internet.md)と[アクティブ ドキュメント](../../mfc/active-documents-on-the-internet.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CCmdUI](../../mfc/reference/ccmdui-class.md)  
  
 `COleCmdUI`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdocobj.h  
  
##  <a name="colecmdui"></a>  COleCmdUI::COleCmdUI  
 構築、`COleCmdUI`特定のユーザー インターフェイスのコマンドに関連付けられているオブジェクト。  
  
```  
COleCmdUI(
    OLECMD* rgCmds,  
    ULONG cCmds,  
    const GUID* m_pGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `rgCmds`  
 指定された GUID に関連付けられている、サポートされているコマンドの一覧。 **OLECMD**構造体は、コマンド フラグを使ってコマンドを関連付けます。  
  
 *cCmds*  
 コマンド数`rgCmds`です。  
  
 `pGroup`  
 コマンドのセットを識別する GUID を指すポインター。  
  
### <a name="remarks"></a>コメント  
 `COleCmdUI`オブジェクトは、メニュー項目またはコントロール バー ボタンなどのユーザー インターフェイス オブジェクトを DocObject を更新するためのプログラム インターフェイスを提供します。 ユーザー インターフェイス オブジェクトを有効になっている、無効になっている、チェック、およびをオフになって、`COleCmdUI`オブジェクト。  
  
##  <a name="enable"></a>  COleCmdUI::Enable  
 コマンド フラグを設定するには、この関数を呼び出す、`COleCmdUI`オブジェクトを**OLECOMDF_ENABLED**、これによりは、インターフェイスのコマンドは、利用可能で、有効になっている、またはコマンド フラグをクリアします。  
  
```  
virtual void Enable(BOOL bOn);
```  
  
### <a name="parameters"></a>パラメーター  
 `bOn`  
 コマンドに関連付けられているかどうかを示す、`COleCmdUI`オブジェクトを有効または無効にする必要があります。 0 以外を有効にコマンド。0 は、コマンドを無効にします。  
  
##  <a name="setcheck"></a>  COleCmdUI::SetCheck  
 オン/オフ切り替えの状態を設定するには、この関数を呼び出すコマンド。  
  
```  
virtual void SetCheck(int nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCheck`  
 オン/オフ切り替えを設定する状態を決定する値コマンド。 値は次のとおりです。  
  
|[値]|説明|  
|-----------|-----------------|  
|**1**|コマンドを on に設定します。|  
|**2**|不確定; コマンドを設定します。このコマンドの属性は、両方の内外で関連する選択項目の状態では、状態を特定できません。|  
|その他の値|コマンドをオフに設定します。|  
  
##  <a name="settext"></a>  COleCmdUI::SetText  
 この関数では、コマンドのテキストの名前または状態文字列を取得します。  
  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 コマンドで使用されるテキストへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



