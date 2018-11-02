---
title: /CLRSUPPORTLASTERROR (PInvoke 呼び出しの最終エラー コードの保持)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: e813966367b4349a95c174c59340204592b81b74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660914"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (PInvoke 呼び出しの最終エラー コードの保持)

**/CLRSUPPORTLASTERROR**、既定でオンになっているでコンパイルされた関数の最終エラー コードは、DLL のコードからネイティブ関数を呼び出すことができる P/invoke 機構を通じてと呼ばれる保持 **/clr**します。

## <a name="syntax"></a>構文

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Remarks

最後のエラー コードを維持し、パフォーマンスの低下を意味します。  最後のエラー コードの維持のパフォーマンスに与える影響が発生しない場合とリンク **/CLRSUPPORTLASTERROR:NO**します。

リンクすることによってパフォーマンスに与える影響を最小限に抑えることができます **/CLRSUPPORTLASTERROR:SYSTEMDLL**、システム Dll で関数の最後のエラー コードだけが保護されます。  システム DLL は、次のいずれかとして定義されます。

|||||
|-|-|-|-|
|ACLUI します。DLL|ACTIVEDS します。DLL|ADPTIF します。DLL|ADVAPI32 します。DLL|
|ASYCFILT します。DLL|AUTHZ します。DLL|AVICAP32 します。DLL|AVIFIL32 します。DLL|
|キャビネットします。DLL|CLUSAPI します。DLL|COMCTL32 します。DLL|COMDLG32 します。DLL|
|COMSVCS します。DLL|CREDUI します。DLL|CRYPT32 します。DLL|CRYPTNET します。DLL|
|CRYPTUI します。DLL|D3D8THK します。DLL|DBGENG します。DLL|DBGHELP します。DLL|
|DCIMAN32 します。DLL|DNSAPI します。DLL|DSPROP します。DLL|DSUIEXT します。DLL|
|GDI32 します。DLL|GLU32 します。DLL|HLINK します。DLL|ICM32 します。DLL|
|IMAGEHLP します。DLL|IMM32 します。DLL|IPHLPAPI します。DLL|IPROP します。DLL|
|KERNEL32 します。DLL|KSUSER します。DLL|「LOADPERF」。DLL|LZ32 します。DLL|
|MAPI32 します。DLL|MGMTAPI します。DLL|MOBSYNC します。DLL|MPR します。DLL|
|MPRAPI します。DLL|MQRT します。DLL|MSACM32 します。DLL|MSCMS します。DLL|
|MSI です。DLL|MSIMG32 します。DLL|MSRATING します。DLL|MSTASK します。DLL|
|MSVFW32 します。DLL|MSWSOCK します。DLL|MTXEX します。DLL|NDDEAPI します。DLL|
|NETAPI32 します。DLL|NPPTOOLS します。DLL|NTDSAPI します。DLL|NTDSBCLI します。DLL|
|NTMSAPI します。DLL|ODBC32 します。DLL|ODBCBCP します。DLL|OLE32 対応します。DLL|
|OLEACC します。DLL|OLEAUT32 します。DLL|OLEDLG します。DLL|OPENGL32 します。DLL|
|PDH します。DLL|POWRPROF します。DLL|QOSNAME します。DLL|クエリを実行します。DLL|
|RASAPI32 します。DLL|RASDLG します。DLL|RASSAPI します。DLL|RESUTILS します。DLL|
|RICHED20 します。DLL|RPCNS4 します。DLL|RPCRT4 します。DLL|RTM します。DLL|
|RTUTILS します。DLL|SCARDDLG します。DLL|SECUR32 します。DLL|SENSAPI します。DLL|
|SETUPAPI します。DLL|SFC します。DLL|SHELL32 します。DLL|SHFOLDER します。DLL|
|SHLWAPI します。DLL|SISBKUP します。DLL|SNMPAPI します。DLL|SRCLIENT します。DLL|
|STI します。DLL|TAPI32 します。DLL|トラフィック。DLL|URL。DLL|
|URLMON します。DLL|USER32 します。DLL|USERENV します。DLL|USP10 します。DLL|
|UXTHEME します。DLL|VDMDBG します。DLL|バージョン。DLL|WINFAX します。DLL|
|WINHTTP します。DLL|WININET の基礎です。DLL|WINMM します。DLL|WINSCARD します。DLL|
|WINTRUST します。DLL|WLDAP32 します。DLL|WOW32 します。DLL|WS2_32.DLL|
|WSNMP32 します。DLL|WSOCK32.DLL|WTSAPI32 します。DLL|XOLEHLP します。DLL|

> [!NOTE]
>  最後のエラーの保持は、同じモジュールでの CLR コードで使用されるアンマネージ関数ではサポートされていません。

- 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. をクリックして、**リンカー**フォルダー。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. オプションを入力、**追加オプション**ボックス。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="example"></a>例

次の例では、最後のエラーを修正する 1 つのエクスポートされた関数を使用して、ネイティブ DLL を定義します。

```
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>例

次の例を使用する方法を示す、DLL を消費する **/CLRSUPPORTLASTERROR**します。

```
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)