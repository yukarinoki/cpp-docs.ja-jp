---
title: CMouseManager クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
dev_langs:
- C++
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1788e5f3938cc496e66aa24d6d1b6a37603e7d7b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039948"
---
# <a name="cmousemanager-class"></a>CMouseManager クラス
により、ユーザーは、さまざまなコマンドを関連付ける特定[CView](../../mfc/reference/cview-class.md)オブジェクトのビューの内側をダブルクリックします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMouseManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMouseManager::AddView](#addview)|追加、`CView`オブジェクトを**カスタマイズ** ダイアログ ボックス。 **カスタマイズ** ダイアログ ボックスに表示されているビューの各コマンドでダブルクリックを関連付けるには、ユーザーを有効にします。|  
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|指定されたビュー内のユーザーをダブルクリックしたときに実行されるコマンドを返します。|  
|[CMouseManager::GetViewIconId](#getviewiconid)|指定されたビューの ID に関連付けられているアイコンを返します|  
|[CMouseManager::GetViewIdByName](#getviewidbyname)|指定されたビュー名に関連付けられたビュー ID を返します。|  
|[CMouseManager::GetViewNames](#getviewnames)|すべての追加のビュー名の一覧を取得します。|  
|[CMouseManager::LoadState](#loadstate)|読み込み、 `CMouseManager` Windows レジストリから状態です。|  
|[CMouseManager::SaveState](#savestate)|書き込みます、 `CMouseManager` Windows レジストリに状態です。|  
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|指定されたコマンドと、指定されたビューを関連付けます。|  
  
## <a name="remarks"></a>Remarks  
 `CMouseManager`クラスのコレクションを保持する`CView`オブジェクト。 各ビューは ID と名前によって識別されます。 これらのビューが示すように、**カスタマイズ** ダイアログ ボックス。 ユーザーが経由の任意のビューに関連付けられているコマンドを変更できる、**カスタマイズ** ダイアログ ボックス。 ビューにユーザーをダブルクリックすると、関連付けられたコマンドが実行されます。 これをサポートするコーディングの面から、したメッセージと呼び出しを処理する必要があります、 [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick)をコード内の関数`CView`オブジェクト.  
  
 作成しないようにする、`CMouseManager`手動でのオブジェクトします。 アプリケーションのためにフレームワークによって作成されます。 これも破棄されます自動的にユーザーがアプリケーションを終了するときにします。 アプリケーションのマウス マネージャーへのポインターを取得、呼び出す[CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMouseManager`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxmousemanager.h  
  
##  <a name="addview"></a>  CMouseManager::AddView  
 登録、 [CView](../../mfc/reference/cview-class.md)オブジェクトを[CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)マウスのカスタム動作をサポートします。  
  
```  
BOOL AddView(
    int iViewId,  
    UINT uiViewNameResId,  
    UINT uiIconId = 0);

 
BOOL AddView(
    int iId,  
    LPCTSTR lpszViewName,  
    UINT uiIconId = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iViewId*  
 ビューの id です。  
  
 [in]*uiViewNameResId*  
 ビュー名を参照するリソースの文字列 ID。  
  
 [in]*uiIconId*  
 ビューのアイコンの id です。  
  
 [in]*iId*  
 ビューの id です。  
  
 [in]*lpszViewName*  
 ビューの名前。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 マウスをカスタムの動作をサポートするためには、ビューに登録する必要があります、`CMouseManager`オブジェクト。 派生した任意のオブジェクト、`CView`クラスは、マウス マネージャーに登録することができます。 文字列と、ビューに関連付けられているアイコンで表示されます、**マウス**のタブ、**カスタマイズ** ダイアログ ボックス。  
  
 作成およびようにビューの Id を管理するプログラマの責任である*iViewId*と*iId*です。  
  
 マウスのカスタム動作を提供する方法の詳細については、次を参照してください。[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)です。  
  
### <a name="example"></a>例  
 次の例へのポインターを取得する方法を示します、`CMouseManager`オブジェクトを使用して、`CWinAppEx::GetMouseManager`メソッドおよび`AddView`メソッドで、`CMouseManager`クラスです。 このコード スニペットの一部である、[状態コレクションのサンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]  
  
##  <a name="getviewdblclickcommand"></a>  CMouseManager::GetViewDblClickCommand  
 指定されたビュー内のユーザーをダブルクリックしたときに実行されるコマンドを返します。  
  
```  
UINT GetViewDblClickCommand(int iId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iId*  
 ビューの id です。  
  
### <a name="return-value"></a>戻り値  
 ビューがコマンドに関連付けられた場合は、コマンド識別子それ以外の場合 0 を返します。  
  
##  <a name="getviewiconid"></a>  CMouseManager::GetViewIconId  
 ビューの ID に関連付けられたアイコンを取得します  
  
```  
UINT GetViewIconId(int iViewId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iViewId*  
 ビューの id です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、アイコン リソースの識別子それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して、ビューが最初に登録されていない場合、このメソッドは失敗[CMouseManager::AddView](#addview)です。  
  
##  <a name="getviewidbyname"></a>  CMouseManager::GetViewIdByName  
 ビュー名に関連付けられたビュー ID を取得します。  
  
```  
int GetViewIdByName(LPCTSTR lpszName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszName*  
 ビューの名前。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、ビュー IDそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは検索を使用して登録されているビューを通じて[CMouseManager::AddView](#addview)です。  
  
##  <a name="getviewnames"></a>  CMouseManager::GetViewNames  
 すべての登録済みのビュー名の一覧を取得します。  
  
```  
void GetViewNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*listOfNames*  
 参照を`CStringList`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、パラメーター、塗りつぶします`listOfNames`を使用して登録されているすべてのビューの名前を持つ[CMouseManager::AddView](#addview)です。  
  
##  <a name="loadstate"></a>  CMouseManager::LoadState  
 状態を読み込み、 [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)レジストリからです。  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 レジストリ キーのパス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レジストリから読み込まれた状態の情報には、登録済みのビュー、ビュー識別子、および関連付けられたコマンドが含まれています。 場合、パラメーター *lpszProfileName*は`NULL`、この関数は読み込みます、`CMouseManager`によって制御される既定のレジストリの場所からデータを[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)です。  
  
 ほとんどの場合、この関数を直接呼び出すにはありません。 ワークスペースの初期化プロセスの一部として呼び出されます。 ワークスペースの初期化処理の詳細については、次を参照してください。 [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate)です。  
  
##  <a name="savestate"></a>  CMouseManager::SaveState  
 状態を書き込み、 [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)をレジストリにします。  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 レジストリ キーのパス。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 レジストリに書き込まれる状態情報には、登録されているすべてのビュー、ビュー識別子、および関連するコマンドが含まれています。 場合、パラメーター *lpszProfileName*は`NULL`、この関数を書き込みます、`CMouseManager`によって制御される既定のレジストリの場所へのデータ、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)です。  
  
 ほとんどの場合、この関数を直接呼び出すにはありません。 ワークスペースのシリアル化プロセスの一部として呼び出されます。 ワークスペースのシリアル化プロセスの詳細については、次を参照してください。 [CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)です。  
  
##  <a name="setcommandfordblclk"></a>  CMouseManager::SetCommandForDblClk  
 カスタム コマンドをマウス マネージャーに最初に登録されているビューに関連付けます。  
  
```  
void SetCommandForDblClk(
    int iViewId,  
    UINT uiCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iViewId*  
 ビューの識別子です。  
  
 [in]*uiCmd*  
 コマンドの識別子です。  
  
### <a name="remarks"></a>Remarks  
 ビューとカスタム コマンドを関連付けるためにする必要があります最初、ビューを使用して登録[CMouseManager::AddView](#addview)です。 `AddView`メソッドには、入力パラメーターとしてビュー識別子が必要です。 ビューを登録した後は、呼び出す`CMouseManager::SetCommandForDblClk`を同じビュー識別子入力パラメーターに指定した`AddView`です。 その後、ユーザーをダブルクリックすると、登録済みのビューで、マウス、アプリケーションはコマンドを実行、によって示される*uiCmd です。* マウスのカスタム動作をサポートするためには、マウス マネージャーに登録されているビューをカスタマイズする必要があります。 マウスのカスタム動作の詳細については、次を参照してください。[キーボードとマウスのカスタマイズ](../keyboard-and-mouse-customization.md)です。  
  
 場合*uiCmd*設定は 0 に、指定されたビューは、コマンドを使用して関連付けられなくです。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)



