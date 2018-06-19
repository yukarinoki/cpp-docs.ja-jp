---
title: CAtlExeModuleT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
dev_langs:
- C++
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d22510da8c1377411b289b940e1b8e196533c93a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364964"
---
# <a name="catlexemodulet-class"></a>CAtlExeModuleT クラス
このクラスは、アプリケーションのモジュールを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlExeModuleT`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlExeModuleT::CAtlExeModuleT](#catlexemodulet)|コンストラクターです。|  
|[CAtlExeModuleT:: ~ CAtlExeModuleT](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[する](#initializecom)|COM を初期化します。|  
|[CAtlExeModuleT::ParseCommandLine](#parsecommandline)|コマンドラインを解析し、必要な場合は、登録を実行します。|  
|[CAtlExeModuleT::PostMessageLoop](#postmessageloop)|このメソッドは、メッセージ ループが終了した直後後に呼び出されます。|  
|[CAtlExeModuleT::PreMessageLoop](#premessageloop)|このメソッドは、メッセージ ループに入る直前に呼び出されます。|  
|[CAtlExeModuleT::RegisterClassObjects](#registerclassobjects)|クラスのオブジェクトを登録します。|  
|[で](#revokeclassobjects)|クラスのオブジェクトを取り消します。|  
|[CAtlExeModuleT::Run](#run)|このメソッドは、EXE モジュールを初期化するには、メッセージ ループの実行でコードを実行してクリーンアップします。|  
|[CAtlExeModuleT::RunMessageLoop](#runmessageloop)|このメソッドは、メッセージ ループを実行します。|  
|[CAtlExeModuleT::UninitializeCom](#uninitializecom)|COM. の初期化を解除します。|  
|[CAtlExeModuleT::Unlock](#unlock)|モジュールのロック カウントをデクリメントします。|  
|[CAtlExeModuleT::WinMain](#winmain)|このメソッドは、EXE の実行に必要なコードを実装します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)|モジュールをシャット ダウンの遅延が存在するかを示すフラグです。|  
|[CAtlExeModuleT::m_dwPause](#m_dwpause)|シャット ダウンする前にすべてのオブジェクトが解放されることを確認するために使用する一時停止の値です。|  
|[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)|モジュールのアンロードを遅延させるためのタイムアウト値。|  
  
## <a name="remarks"></a>コメント  
 `CAtlExeModuleT` アプリケーション (EXE) のモジュールを表し、終了時に、EXE の作成、コマンドラインの処理、クラス オブジェクトを登録して、メッセージ ループの実行およびクリーンアップをサポートするコードが含まれています。  
  
 このクラスは、exe ファイル サーバーの COM オブジェクトの継続的に作成および破棄される場合にパフォーマンスを向上させるために設計されています。 指定した期間の exe ファイルが待機する最後の COM オブジェクトが解放された後、 [CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)データ メンバーです。 この期間中にアクティビティがない場合 (つまり、COM オブジェクトは作成されません)、シャット ダウン プロセスが開始します。  
  
 [CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)データ メンバーは、exe ファイルが上記で定義された機構を使用する必要があるかどうかを決定するためのフラグ。 False に設定されている場合、モジュールはすぐに終了します。  
  
 ATL でモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catlexemodulet"></a>  CAtlExeModuleT::CAtlExeModuleT  
 コンストラクターです。  
  
```
CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 EXE モジュールを初期化できなかった場合 WinMain はさらに処理することがなく即座に返します。  
  
##  <a name="dtor"></a>  CAtlExeModuleT:: ~ CAtlExeModuleT  
 デストラクターです。  
  
```
~CAtlExeModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="initializecom"></a>  する  
 COM を初期化します。  
  
```
static HRESULT InitializeCom() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コンス トラクターから呼び出され、既定の実装とは異なる形式で COM を初期化するためにオーバーライドすることができます。 既定の実装を呼び出すか、 **CoInitializeEx (NULL、COINIT_MULTITHREADED)** または**CoInitialize(NULL)** プロジェクト構成によって異なります。  
  
 通常、このメソッドをオーバーライドするには、オーバーライドする必要があります[CAtlExeModuleT::UninitializeCom](#uninitializecom)です。  
  
##  <a name="m_bdelayshutdown"></a>  CAtlExeModuleT::m_bDelayShutdown  
 モジュールをシャット ダウンの遅延が存在するかを示すフラグです。  
  
```
bool m_bDelayShutdown;
```  
  
### <a name="remarks"></a>コメント  
 参照してください、 [CAtlExeModuleT 概要](../../atl/reference/catlexemodulet-class.md)詳細についてはします。  
  
##  <a name="m_dwpause"></a>  CAtlExeModuleT::m_dwPause  
 シャット ダウンする前にすべてのオブジェクトを削除することを確認するために使用する一時停止の値です。  
  
```
DWORD m_dwPause;
```  
  
### <a name="remarks"></a>コメント  
 この値を呼び出した後に変更[する](#initializecom)サーバーをシャット ダウンの一時停止の値として使用されるミリ秒単位の数を設定します。 既定値は、1000 ミリ秒です。  
  
##  <a name="m_dwtimeout"></a>  CAtlExeModuleT::m_dwTimeOut  
 モジュールのアンロードを遅延させるためのタイムアウト値。  
  
```
DWORD m_dwTimeOut;
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後、この値を変更[する](#initializecom)サーバーをシャット ダウンのタイムアウト値として使用されるミリ秒単位の数を定義します。 既定値は 5000 ミリ秒です。 参照してください、 [CAtlExeModuleT 概要](../../atl/reference/catlexemodulet-class.md)詳細についてはします。  
  
##  <a name="parsecommandline"></a>  CAtlExeModuleT::ParseCommandLine  
 コマンドラインを解析し、必要な場合は、登録を実行します。  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCmdLine`  
 アプリケーションをコマンドラインに渡されます。  
  
 `pnRetCode`  
 (これが、行われた) 場合は、登録に対応する HRESULT。  
  
### <a name="return-value"></a>戻り値  
 アプリケーションが実行を続ける場合、それ以外の場合は false、true を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出した[CAtlExeModuleT::WinMain](#winmain)コマンド ライン スイッチの処理をオーバーライドするとします。 既定の実装 **/RegServer**と **/UnRegServer**コマンドライン引数し、登録または登録解除を実行します。  
  
##  <a name="postmessageloop"></a>  CAtlExeModuleT::PostMessageLoop  
 このメソッドは、メッセージ ループが終了した直後後に呼び出されます。  
  
```
HRESULT PostMessageLoop() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 カスタム アプリケーションのクリーンアップを実行するには、このメソッドをオーバーライドします。 既定の実装[で](#revokeclassobjects)です。  
  
##  <a name="premessageloop"></a>  CAtlExeModuleT::PreMessageLoop  
 このメソッドは、メッセージ ループに入る直前に呼び出されます。  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 渡された値、 `nShowCmd` WinMain のパラメーターです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションのカスタムの初期化コードを追加するには、このメソッドをオーバーライドします。 既定の実装では、クラス オブジェクトを登録します。  
  
##  <a name="registerclassobjects"></a>  CAtlExeModuleT::RegisterClassObjects  
 他のアプリケーションが接続できるように、クラス オブジェクトを OLE に登録します。  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwClsContext*  
 クラスのオブジェクトが実行されるコンテキストを指定します。 使用可能な値は CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、または CLSCTX_LOCAL_SERVER です。  
  
 `dwFlags`  
 クラスのオブジェクトへの接続の種類を決定します。 使用可能な値は REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_FALSE を登録するクラスが存在しなかった場合または失敗した場合にエラー HRESULT は S_OK を返します。  
  
##  <a name="revokeclassobjects"></a>  で  
 クラスのオブジェクトを削除します。  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_FALSE を登録するクラスが存在しなかった場合または失敗した場合にエラー HRESULT は S_OK を返します。  
  
##  <a name="run"></a>  CAtlExeModuleT::Run  
 このメソッドは、EXE モジュールを初期化するには、メッセージ ループの実行でコードを実行してクリーンアップします。  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターで説明した値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。 既定値は SW_HIDE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドすることができます。 ただし、実際には、改善をオーバーライドする[CAtlExeModuleT::PreMessageLoop](#premessageloop)、 [CAtlExeModuleT::RunMessageLoop](#runmessageloop)、または[CAtlExeModuleT::PostMessageLoop](#postmessageloop)その代わりに。  
  
##  <a name="runmessageloop"></a>  CAtlExeModuleT::RunMessageLoop  
 このメソッドは、メッセージ ループを実行します。  
  
```
void RunMessageLoop() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドすると、メッセージ ループの動作を変更します。  
  
##  <a name="uninitializecom"></a>  CAtlExeModuleT::UninitializeCom  
 COM. の初期化を解除します。  
  
```
static void UninitializeCom() throw();
```  
  
### <a name="remarks"></a>コメント  
 既定ではこのメソッドを呼び出すだけ[CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715)デストラクターから呼び出されるとします。 オーバーライドする場合は、このメソッドをオーバーライド[する](#initializecom)です。  
  
##  <a name="unlock"></a>  CAtlExeModuleT::Unlock  
 モジュールのロック カウントをデクリメントします。  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役に立たず、テストされる値を返します。  
  
##  <a name="winmain"></a>  CAtlExeModuleT::WinMain  
 このメソッドは、EXE の実行に必要なコードを実装します。  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターで説明した値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。  
  
### <a name="return-value"></a>戻り値  
 実行可能ファイルの戻り値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドすることができます。 オーバーライドする場合[CAtlExeModuleT::PreMessageLoop](#premessageloop)、 [CAtlExeModuleT::PostMessageLoop](#postmessageloop)、または[CAtlExeModuleT::RunMessageLoop](#runmessageloop)十分な柔軟性を提供しませんをオーバーライドすることは、`WinMain`このメソッドを使用して機能します。  
  
## <a name="see-also"></a>関連項目  
 [ATLDuck サンプル](../../visual-cpp-samples.md)   
 [CAtlModuleT クラス](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT クラス](../../atl/reference/catldllmodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
