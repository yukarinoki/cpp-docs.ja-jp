---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHook
- ATLUTIL/ATL::CDebugReportHook::CDebugReportHookProc
- ATLUTIL/ATL::CDebugReportHook::RemoveHook
- ATLUTIL/ATL::CDebugReportHook::SetHook
- ATLUTIL/ATL::CDebugReportHook::SetPipeName
- ATLUTIL/ATL::CDebugReportHook::SetTimeout
helpviewer_keywords:
- CDebugReportHook class
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
ms.openlocfilehash: 8380556bbe007326156bf0ec0eefc23052e8e056
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747722"
---
# <a name="cdebugreporthook-class"></a>クラス

このクラスは、名前付きパイプにデバッグ レポートを送信するために使います。

## <a name="syntax"></a>構文

```
class CDebugReportHook
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[レポートフック::Cデバッグレポートフック](#cdebugreporthook)|を呼び出します[SetTimeout](#settimeout)[。](#setpipename) [SetHook](#sethook)|
|[レポートフック::~Cデバッグレポートフック](#dtor)|[を](#removehook)呼び出します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[レポートフック::Cデバッグレポートフックプロセッサ](#cdebugreporthookproc)|(静的)C ランタイム デバッグ レポート プロセスにフックされるカスタム レポート関数。|
|[レポートフックを実行します。](#removehook)|このメソッドを呼び出すと、名前付きパイプへのデバッグ レポートの送信を停止し、以前のレポート フックを復元します。|
|[レポートフック::セットフック](#sethook)|このメソッドを呼び出して、名前付きパイプへのデバッグ レポートの送信を開始します。|
|[レポートフック::セットパイプ名](#setpipename)|デバッグ レポートの送信先となるパイプのマシン名と名前を設定します。|
|[レポートフック::セットタイムアウト](#settimeout)|このクラスが名前付きパイプが使用可能になるまで待機する時間をミリ秒単位で設定します。|

## <a name="remarks"></a>解説

サービスまたはアプリケーションのデバッグ ビルドでこのクラスのインスタンスを作成し、名前付きパイプにデバッグ レポートを送信します。 デバッグ レポートは[、_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)呼び出すか[、ATLTRACE](debugging-and-error-reporting-macros.md#atltrace)マクロや[ATLASSERT](debugging-and-error-reporting-macros.md#atlassert)マクロなどのこの関数のラッパーを使用して生成されます。

このクラスを使用すると、非対話型[ウィンドウ ステーション](/windows/win32/winstation/window-stations)で実行されているコンポーネントを対話式にデバッグできます。

デバッグ レポートは、スレッドの基になるセキュリティ コンテキストを使用して送信されることに注意してください。 偽装は一時的に無効にされ、Web アプリケーションなどで特権の低いユーザーの偽装が行われている状況でデバッグ レポートを表示できます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="cdebugreporthookcdebugreporthook"></a><a name="cdebugreporthook"></a>レポートフック::Cデバッグレポートフック

を呼び出します[SetTimeout](#settimeout)[。](#setpipename) [SetHook](#sethook)

```
CDebugReportHook(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe",
    DWORD dwTimeout = 20000) throw();
```

### <a name="parameters"></a>パラメーター

*マシン名*<br/>
デバッグ出力の送信先のコンピューターの名前。 デフォルトはローカル マシンです。

*パイプ名*<br/>
デバッグ出力の送信先となる名前付きパイプの名前。

*タイムアウト*<br/>
このクラスが名前付きパイプが使用可能になるまで待機する時間 (ミリ秒単位)。

## <a name="cdebugreporthookcdebugreporthook"></a><a name="dtor"></a>レポートフック::~Cデバッグレポートフック

[を](#removehook)呼び出します。

```
~CDebugReportHook() throw();
```

## <a name="cdebugreporthookcdebugreporthookproc"></a><a name="cdebugreporthookproc"></a>レポートフック::Cデバッグレポートフックプロセッサ

C ランタイム デバッグ レポート プロセスにフックされるカスタム レポート関数。

```
static int __cdecl CDebugReportHookProc(
    int reportType,
    char* message,
    int* returnValue) throw();
```

### <a name="parameters"></a>パラメーター

*レポートタイプ*<br/>
レポートの種類 (_CRT_WARN、_CRT_ERROR、または_CRT_ASSERT)。

*message*<br/>
メッセージ文字列。

*Returnvalue*<br/>
[_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)によって返される値。

### <a name="return-value"></a>戻り値

フックが問題のメッセージを完全に処理し、それ以上の報告が必要ないようにする場合は、FALSE を返します。 通常の方法`_CrtDbgReport`でメッセージを報告する必要がある場合は TRUE を返します。

### <a name="remarks"></a>解説

レポート機能は、名前付きパイプを開き、もう一方の端のプロセスと通信しようとします。 パイプがビジー状態の場合、レポート機能は、パイプが空き状態になるか、タイムアウトが切れるまで待機します。 タイムアウトは、コンストラクターまたは[CDebugReportHook::SetTimeout](#settimeout)の呼び出しによって設定できます。

この関数のコードは、呼び出し元スレッドの基になるセキュリティ コンテキストで実行されます。

## <a name="cdebugreporthookremovehook"></a><a name="removehook"></a>レポートフックを実行します。

このメソッドを呼び出すと、名前付きパイプへのデバッグ レポートの送信を停止し、以前のレポート フックを復元します。

```cpp
void RemoveHook() throw();
```

### <a name="remarks"></a>解説

前のレポート フックを復元するために[_CrtSetReportHook2](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)を呼び出します。

## <a name="cdebugreporthooksethook"></a><a name="sethook"></a>レポートフック::セットフック

このメソッドを呼び出して、名前付きパイプへのデバッグ レポートの送信を開始します。

```cpp
void SetHook() throw();
```

### <a name="remarks"></a>解説

[cDebugReportHookProc](#cdebugreporthookproc)[を介](../../c-runtime-library/reference/crtsetreporthook2-crtsetreporthookw2.md)して名前付きパイプにルーティングされるデバッグ レポートを_CrtSetReportHook2呼び出します。 このクラスは[、RemoveHook](#removehook)が呼び出されたときに復元できるように、前のレポート フックを追跡します。

## <a name="cdebugreporthooksetpipename"></a><a name="setpipename"></a>レポートフック::セットパイプ名

デバッグ レポートの送信先となるパイプのマシン名と名前を設定します。

```
BOOL SetPipeName(
    LPCSTR szMachineName = ".",
    LPCSTR szPipeName = "AtlsDbgPipe") throw();
```

### <a name="parameters"></a>パラメーター

*マシン名*<br/>
デバッグ出力の送信先のコンピューターの名前。

*パイプ名*<br/>
デバッグ出力の送信先となる名前付きパイプの名前。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="cdebugreporthooksettimeout"></a><a name="settimeout"></a>レポートフック::セットタイムアウト

このクラスが名前付きパイプが使用可能になるまで待機する時間をミリ秒単位で設定します。

```cpp
void SetTimeout(DWORD dwTimeout);
```

### <a name="parameters"></a>パラメーター

*タイムアウト*<br/>
このクラスが名前付きパイプが使用可能になるまで待機する時間 (ミリ秒単位)。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)
