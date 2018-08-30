---
title: CDebugReportHook クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
dev_langs:
- C++
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8de1f44b079b269d76054b1a221a8ec3e36daf5e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209326"
---
# <a name="cdebugreporthook-class"></a>CDebugReportHook クラス
このクラスを使用すると、名前付きパイプにデバッグ レポートを送信します。  
  
## <a name="syntax"></a>構文  
  
```
class CDebugReportHook
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](#cdebugreporthook)|呼び出し[SetPipeName](#setpipename)、 [SetTimeout](#settimeout)、および[SetHook](#sethook)します。|  
|[CDebugReportHook:: ~ CDebugReportHook](#dtor)|呼び出し[CDebugReportHook::RemoveHook](#removehook)します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](#cdebugreporthookproc)|(静的)C ランタイム デバッグ レポート プロセスにフックされます。 カスタム レポート関数。|  
|[CDebugReportHook::RemoveHook](#removehook)|名前付きパイプへのデバッグ レポートの送信を停止するには、このメソッドを呼び出すし、前のレポート用のフックを復元します。|  
|[CDebugReportHook::SetHook](#sethook)|名前付きパイプのデバッグ レポートの送信を開始するには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetPipeName](#setpipename)|コンピューターとは、デバッグ レポートを送信するパイプの名前を設定するには、このメソッドを呼び出します。|  
|[CDebugReportHook::SetTimeout](#settimeout)|このクラスで使用可能になる名前付きパイプが待機するミリ秒単位で時間を設定するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>Remarks  
 サービスまたは名前付きパイプにデバッグ レポートを送信するアプリケーションのデバッグ ビルドでは、このクラスのインスタンスを作成します。 デバッグ レポートが呼び出すことによって生成される[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)またはこの関数のラッパーをなどを使用して、 [ATLTRACE](debugging-and-error-reporting-macros.md#atltrace)と[ATLASSERT](debugging-and-error-reporting-macros.md#atlassert)マクロ。  
  
 このクラスの使用では、非対話型で実行されるコンポーネントを対話的にデバッグできます。[ウィンドウ ステーション](/windows/desktop/winstation/window-stations)します。  
  
 スレッドの基になるセキュリティ コンテキストを使用してデバッグ レポートを送信することに注意してください。 デバッグ レポートを低い特権のユーザーの権限の借用が行わなどの web アプリケーションでの状況で表示するように、権限借用が一時的に無効にします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="cdebugreporthook"></a>  CDebugReportHook::CDebugReportHook  
 呼び出し[SetPipeName](#setpipename)、 [SetTimeout](#settimeout)、および[SetHook](#sethook)します。  
  
```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *szMachineName*  
 デバッグ出力を送信するマシンの名前。 ローカル コンピューターに既定値です。  
  
 *szPipeName*  
 デバッグ出力の送信先となる名前付きパイプの名前。  
  
 *dwTimeout*  
 このクラスで使用可能になる名前付きパイプが待機するミリ秒単位の時間。  
  
##  <a name="dtor"></a>  CDebugReportHook:: ~ CDebugReportHook  
 呼び出し[CDebugReportHook::RemoveHook](#removehook)します。  
  
```
~CDebugReportHook() throw();
```  
  
##  <a name="cdebugreporthookproc"></a>  CDebugReportHook::CDebugReportHookProc  
 C ランタイム デバッグ レポート プロセスにフックされます。 カスタム レポート関数。  
  
```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *reportType*  
 (前述、_CRT_ERROR、または _CRT_ASSERT) レポートの種類。  
  
 *message*  
 メッセージ文字列。  
  
 *戻り値*  
 によって返される値[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)します。  
  
### <a name="return-value"></a>戻り値  
 かどうか、フックでメッセージを完全に処理さらにレポートを作成する必要はありませんようにに FALSE を返します。 場合に TRUE を返します`_CrtDbgReport`通常の方法でメッセージを報告する必要があります。  
  
### <a name="remarks"></a>Remarks  
 レポートの関数は、名前付きパイプを開くし、プロセスをもう一方の端との通信を試みます。 パイプがビジー状態の場合は、レポートの関数はパイプが無料か、タイムアウトが経過するまで待機します。 コンス トラクターまたはへの呼び出しによって、タイムアウトを設定できる[CDebugReportHook::SetTimeout](#settimeout)します。  
  
 この関数のコードが呼び出し元のスレッドの基になるセキュリティ コンテキストで実行される、この関数の実行中、権限借用は、無効になっています。  
  
##  <a name="removehook"></a>  CDebugReportHook::RemoveHook  
 名前付きパイプへのデバッグ レポートの送信を停止するには、このメソッドを呼び出すし、前のレポート用のフックを復元します。  
  
```
void RemoveHook() throw();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出し[_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)前のレポート用のフックを復元します。  
  
##  <a name="sethook"></a>  CDebugReportHook::SetHook  
 名前付きパイプのデバッグ レポートの送信を開始するには、このメソッドを呼び出します。  
  
```
void SetHook() throw();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出し[_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)デバッグ レポートを経由してルーティング[CDebugReportHookProc](#cdebugreporthookproc)名前付きパイプにします。 このクラスの追跡、前のレポート用のフックできるように復元するときに[RemoveHook](#removehook)が呼び出されます。  
  
##  <a name="setpipename"></a>  CDebugReportHook::SetPipeName  
 コンピューターとは、デバッグ レポートを送信するパイプの名前を設定するには、このメソッドを呼び出します。  
  
```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *szMachineName*  
 デバッグ出力を送信するマシンの名前。  
  
 *szPipeName*  
 デバッグ出力の送信先となる名前付きパイプの名前。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
##  <a name="settimeout"></a>  CDebugReportHook::SetTimeout  
 このクラスで使用可能になる名前付きパイプが待機するミリ秒単位で時間を設定するには、このメソッドを呼び出します。  
  
```
void SetTimeout(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeout*  
 このクラスで使用可能になる名前付きパイプが待機するミリ秒単位の時間。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../atl/reference/atl-classes.md)
