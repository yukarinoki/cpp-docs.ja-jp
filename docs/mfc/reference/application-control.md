---
title: アプリケーションの制御 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control [MFC]
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76d8ec079a7c3534211118e60c1d9d95a3a8510a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="application-control"></a>アプリケーションの制御
OLE には、アプリケーションとそれらのオブジェクトを十分に制御が必要です。 OLE システム Dll は、起動アプリケーションのリリースを自動的に、その運用環境と、オブジェクトの変更を調整し、できる必要があります。 このトピック内の関数は、それらの要件を満たしています。 に加えて、OLE システム Dll によって呼び出されるは、アプリケーションもによって、これらの関数を呼び出される場合がありますする必要があります。 
  
### <a name="application-control"></a>アプリケーションの制御  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|アプリケーションが終了できるかどうかを示します。|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|アプリケーションの現在のメッセージ フィルターを取得します。|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|現在のユーザー制御フラグを取得します。|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|設定またはユーザー コントロール フラグをクリアします。|  
|[AfxOleLockApp](#afxolelockapp)|フレームワークのグローバルなアプリケーションのアクティブなオブジェクトの数のカウントをインクリメントします。|  
|[AfxOleLockControl](#afxolelockcontrol)| 指定されたコントロールのクラス ファクトリをロックします。 |
|[Afxoleunlockapp を呼び出します](#afxoleunlockapp)|デクリメントするアプリケーションのアクティブなオブジェクトの数のフレームワークの数。| 
|[AfxOleUnlockControl](#afxoleunlockcontrol)| 指定されたコントロールのクラス ファクトリのロックを解除します。 |
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE システム レジストリのサーバーを登録します。|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|ユーザー インターフェイスを実装して、 *typename*コマンド オブジェクトです。|  

  
##  <a name="afxolecanexitapp"></a>  AfxOleCanExitApp  
 アプリケーションが終了できるかどうかを示します。  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、アプリケーションが終了することができます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 そのオブジェクトへの未解決の参照がある場合、アプリケーションを終了する必要があります。 グローバル関数`AfxOleLockApp`と`AfxOleUnlockApp`をインクリメントし、それぞれ、アプリケーションのオブジェクトへの参照カウンターをデクリメントします。 このカウンターが 0 以外の場合、アプリケーションを終了する必要があります。 カウンターが 0 以外の場合は、アプリケーションのメイン ウィンドウが非表示 (破棄されずに)、システム メニューまたは ファイル メニューからの終了を閉じるを選択するとします。 フレームワークこの関数が呼び出さ**CFrameWnd::OnClose**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation#2](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h 

##  <a name="afxolegetmessagefilter"></a>  AfxOleGetMessageFilter  
 アプリケーションの現在のメッセージ フィルターを取得します。  
  
```   
COleMessageFilter* AFXAPI AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージ フィルターへのポインター。  
  
### <a name="remarks"></a>コメント  
 現在にアクセスするには、この関数を呼び出す`COleMessageFilter`-呼び出しと同様に、オブジェクトを派生`AfxGetApp`現在のアプリケーション オブジェクトにアクセスします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation#3](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation#4](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxwin.h 

##  <a name="afxolegetuserctrl"></a>  AfxOleGetUserCtrl  
 現在のユーザー制御フラグを取得します。  
  
```   
BOOL AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーがアプリケーションのコントロールの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが明示的に開かれるか、新しいドキュメントを作成した場合、ユーザーは、アプリケーションのコントロールです。 ユーザーはコントロールにもが OLE システム Dll によって、アプリケーションが起動していない場合: つまり、ユーザーがシステムのシェルを使用してアプリケーションを起動した場合。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="afxolesetuserctrl"></a>  AfxOleSetUserCtrl  
 設定またはのリファレンスで説明されているユーザー制御フラグをクリア`AfxOleGetUserCtrl`です。  
  
```  
void AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>パラメーター  
 *bUserCtrl*  
 ユーザー制御フラグを設定またはクリアするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークからこの関数、ユーザーを作成するか、ドキュメントを読み込みますが、ドキュメントが読み込まれるまたはコンテナー アプリケーションからの埋め込みオブジェクトの読み込みなどの間接操作によって作成されたときではなくです。  
  
 アプリケーションの他の操作は、アプリケーションのコントロールにユーザーを配置する必要がある場合は、この関数を呼び出します。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="afxolelockapp"></a>  AfxOleLockApp  
 フレームワークのグローバルなアプリケーションのアクティブなオブジェクトの数のカウントをインクリメントします。  
  
```   
void AFXAPI AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、アプリケーションでアクティブなオブジェクトの数のカウントを保持します。 `AfxOleLockApp`と`AfxOleUnlockApp`関数はそれぞれ、インクリメントされ、このカウントをデクリメントします。  
  
 ユーザーがアクティブなオブジェクトを持つアプリケーションを終了しようとしたときに — アクティブなオブジェクトの数は 0 以外のアプリケーション-フレームワークには、完全にシャット ダウンではなく、ユーザーのビューから、アプリケーションが非表示にします。 `AfxOleCanExitApp`関数では、アプリケーションが終了できるかどうかを示します。  
  
 呼び出す`AfxOleLockApp`できない場合は、そのオブジェクトをクライアント アプリケーションによってまだ使用されているときに破棄することをお勧め OLE インターフェイスを公開する任意のオブジェクトからです。 呼び出しても`AfxOleUnlockApp`を呼び出す任意のオブジェクトのデストラクターで`AfxOleLockApp`コンス トラクターでします。 既定では、 `COleDocument` (と派生クラス) に自動的にロックおよびアプリケーションのロックを解除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation#5](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="afxoleunlockapp"></a>  Afxoleunlockapp を呼び出します  
 デクリメント、アプリケーションのアクティブなオブジェクトのフレームワークの数。  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>コメント  
 参照してください`AfxOleLockApp`についてさらにします。  
  
 アクティブなオブジェクトの数がゼロに達すると**AfxOleOnReleaseAllObjects**と呼びます。  
  
### <a name="example"></a>例  
 例を参照して[AfxOleLockApp](#afxolelockapp)です。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h  

 ## <a name="afxolelockcontrol"></a>AfxOleLockControl
コントロールに関連付けられている動的に作成されたデータはメモリに保持されるように指定されたコントロールのクラス ファクトリをロックします。  
   
### <a name="syntax"></a>構文    
```
BOOL AFXAPI AfxOleLockControl(  REFCLSID clsid  );  
BOOL AFXAPI AfxOleLockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>パラメーター  
 `clsid`  
 コントロールの一意のクラス ID。  
  
 `lpszProgID`  
 コントロールの一意なプログラム ID。  
   
### <a name="return-value"></a>戻り値  
 コントロールのクラス ファクトリが正常にロックされている場合は 0 以外。それ以外の場合 0 を返します。  
   
### <a name="remarks"></a>コメント  
 これは、大幅にコントロールの表示を高速化できます。 たとえば、1 回 ダイアログ ボックスでコントロールを作成してコントロールをロック`AfxOleLockControl`、作成し、もう一度ダイアログを表示するか破棄するたびに、強制終了する必要はありません。 ユーザーが開き、繰り返し ダイアログ ボックスを閉じる場合は、コントロールをロックが大幅にパフォーマンスが向上します。 コントロールを破棄する準備ができたら、呼び出す`AfxOleUnlockControl`です。  
   
### <a name="example"></a>例  
```cpp
// Starts and locks control's (Microsoft Calendar) class factory. 
// Control will remain in memory for lifetime of
// application or until AfxOleUnlockControl() is called.

AfxOleLockControl(_T("MSCAL.Calendar"));
```
   
### <a name="requirements"></a>要件  
 **ヘッダー:** < afxwin.h >  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
 [AfxOleUnlockControl](#afxoleunlockcontrol)
 
##  <a name="afxoleregisterserverclass"></a>  AfxOleRegisterServerClass  
 この関数では、OLE システム レジストリにサーバーを登録することができます。  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 サーバーの OLE クラス ID への参照  
  
 `lpszClassName`  
 サーバーのオブジェクトのクラス名を含む文字列へのポインター。  
  
 *lpszShortTypeName*  
 サーバーのオブジェクトの種類、"Chart"などの短い名前を含む文字列へのポインター  
  
 *lpszLongTypeName*  
 サーバーのオブジェクトの種類、"Microsoft Excel 5.0 Chart"などの長い名前を含む文字列へのポインター  
  
 `nAppType`  
 取得された、値、 **OLE_APPTYPE** OLE アプリケーションの種類を指定します。 使用可能な値は次のとおりです。  
  
- `OAT_INPLACE_SERVER` サーバーには、サーバー全体のユーザー インターフェイスがあります。  
  
- `OAT_SERVER` サーバーは、埋め込みだけをサポートします。  
  
- `OAT_CONTAINER` コンテナーは、埋め込みアイテムへのリンクをサポートします。  
  
- `OAT_DISPATCH_OBJECT` `IDispatch`-できるオブジェクト。  
  
 `rglpszRegister`  
 キーとキーの既存の値が見つからない場合は、OLE システム レジストリに追加する値を表す文字列へのポインターの配列です。  
  
 `rglpszOverwrite`  
 キーとレジストリに指定されたキーの既存の値が含まれている場合、OLE システム レジストリに追加する値を表す文字列へのポインターの配列です。  
  
### <a name="return-value"></a>戻り値  
 サーバー クラスが登録できた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ほとんどのアプリケーションが使用できる**COleTemplateServer::Register**をアプリケーションのドキュメントの種類を登録します。 使用することができる場合は、アプリケーションのシステム レジストリの形式は、一般的なパターンに一致しない、`AfxOleRegisterServerClass`詳細に制御します。  
  
 レジストリは、キーと値のセットで構成されます。 `rglpszRegister`と`rglpszOverwrite`引数文字列へのポインターの配列は、それぞれので構成される、キーと値で区切られた、 **NULL**文字 ( `'\0'`)。 これらの文字列の各文字のシーケンスで可能な置き換え可能パラメーターを持つことができます`%1`を通じて`%5`です。  
  
 シンボルは、ように入力します。  
  
|シンボル|[値]|  
|------------|-----------|  
|%1|クラスの ID を文字列として書式設定|  
|%2|クラス名|  
|%3|実行可能ファイルへのパス|  
|%4|Short 型の名前|  
|%5|Long 型の名前|  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="afxoleseteditmenu"></a>  AfxOleSetEditMenu  
 ユーザー インターフェイスを実装して、 *typename*コマンド オブジェクトです。  
  
```   
void AFXAPI AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pClient`  
 クライアント OLE アイテムへのポインター。  
  
 `pMenu`  
 更新するメニュー オブジェクトへのポインター。  
  
 *iMenuItem*  
 更新するメニュー項目のインデックス。  
  
 `nIDVerbMin`  
 主動詞に対応するコマンド ID。  
  
 *nIDVerbMax*  
 動詞の最後に対応するコマンド ID。  
  
 *nIDConvert*  
 変換のメニュー項目の ID。  
  
### <a name="remarks"></a>コメント  
 サーバーでは、プライマリの動詞だけで認識場合、メニュー項目は次のようになります。"動詞*typename*オブジェクト"と`nIDVerbMin`コマンドが送信されるのは、コマンドを選択するとします。 かどうか、サーバーは、いくつかの動詞を認識し、メニュー項目になります" *typename*オブジェクト"され、コマンドを選択すると、すべての動詞の一覧を表示するサブメニューが表示されます。 サブメニューの動詞を選択すると`nIDVerbMin`最初の動詞を選択したかどうかは送信`nIDVerbMin`+ 1 が 2 番目の動作は、選択した場合に送信されます。 既定値`COleDocument`の実装は、この機能を自動的に処理します。  
  
 次のステートメント、クライアントのアプリケーションのリソース スクリプトにする必要があります (です。RC) のファイル:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxole.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

## <a name="afxoleunlockcontrol"></a> AfxOleUnlockControl
指定されたコントロールのクラス ファクトリのロックを解除します。  
   
### <a name="syntax"></a>構文  
  ```
BOOL AFXAPI AfxOleUnlockControl( REFCLSID clsid );  
BOOL AFXAPI AfxOleUnlockControl( LPCTSTR lpszProgID );  
```
### <a name="parameters"></a>パラメーター  
 `clsid`  
 コントロールの一意のクラス ID。  
  
 `lpszProgID`  
 コントロールの一意なプログラム ID。  
   
### <a name="return-value"></a>戻り値  
 コントロールのクラス ファクトリが正常にロックできなかった場合は 0 以外。それ以外の場合 0 を返します。  
   
### <a name="remarks"></a>コメント  
 コントロールがロックされて`AfxOleLockControl`コントロールに関連付けられている動的に作成されたデータはメモリに保持されるようにします。 これが大幅に時間を短縮できますコントロールの表示コントロールが作成され破棄されるたびに表示されていない必要があるためです。 コントロールを破棄する準備ができたら、呼び出す`AfxOleUnlockControl`です。  
   
### <a name="example"></a>例  
 ```cpp
// Unlock control's (Microsoft Calendar Control) class factory.

AfxOleUnlockControl(_T("MSCAL.Calendar"));

```
   
### <a name="requirements"></a>要件  
 **ヘッダー:** < afxwin.h >  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)  
 [AfxOleLockControl](#afxolelockcontrol)

