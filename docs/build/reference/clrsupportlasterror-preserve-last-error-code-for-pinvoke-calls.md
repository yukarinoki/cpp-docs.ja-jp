---
title: /CLRSUPPORTLASTERROR (PInvoke 呼び出しの最終エラー コードの保持)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 19930591c2d0406c68b1a408622a49c9e8b1d551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322276"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (PInvoke 呼び出しの最終エラー コードの保持)

**/CLRSUPPORTLASTERROR**は、既定でオンになって **、/clr**でコンパイルされたコードから DLLS のネイティブ関数を呼び出すことができる P/Invoke 機構を通じて呼び出される関数の最後のエラー コードを保持します。

## <a name="syntax"></a>構文

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>解説

最後のエラー コードを保持すると、パフォーマンスが低下します。  最後のエラー コードを保持することによるパフォーマンスへの影響を受けたくない場合は **、/CLRSUPPORTLASTERROR:NO**を使用してください。

**/CLRSUPPORTLASTERROR:SYSTEMDLL**を使用してリンクすると、パフォーマンスへの影響を最小限に抑えることができます。  システム DLL は、次のいずれかとして定義されます。

|||||
|-|-|-|-|
|ACLUI.Dll|アクティブド。Dll|アドプティフ。Dll|ADVAPI32.Dll|
|アシクフィルトDll|認証されます。Dll|AVICAP32.Dll|AVIFIL32.Dll|
|キャビネット。Dll|クリュサピ。Dll|COMCTL32.Dll|COMDLG32.Dll|
|コンスVCS。Dll|クレドイ。Dll|クリプト32。Dll|クリプトネット。Dll|
|クリプトイ。Dll|D3D8THK.Dll|DBGENG.Dll|DBGHELP.Dll|
|DCIMAN32.Dll|DNSAPI。Dll|DSPROP.Dll|スイエクスタDll|
|GDI32.Dll|GLU32.Dll|HLINK.Dll|ICM32.Dll|
|イメージHLP.Dll|IMM32.Dll|イフプアピ。Dll|IPROP。Dll|
|カーネル32。Dll|KSUSER。Dll|ロードパーフ。Dll|LZ32.Dll|
|MAPI32。Dll|MGMTAPI.Dll|モブシンク。Dll|Mpr。Dll|
|MPRAPI.Dll|MQRT.Dll|MSACM32.Dll|MSCMS.Dll|
|Msi。Dll|MSIMG32.Dll|MSRATING。Dll|MSTASK.Dll|
|MSVFW32.Dll|MSWSOCK.Dll|MTXEX.Dll|NDDEAPI.Dll|
|NETAPI32.Dll|NPPツール。Dll|を使用します。Dll|をクリックします。Dll|
|を実行します。Dll|ODBC32.Dll|ODBCBCP.Dll|OLE32.Dll|
|オレACC。Dll|オレオート32。Dll|オレドグ。Dll|オープングル32。Dll|
|Pdh。Dll|ポワープロ。Dll|QOSNAME.Dll|クエリ。Dll|
|RASAPI32.Dll|ラスドアルグ。Dll|ラッサピ。Dll|リセチルDll|
|豊か20。Dll|RPCNS4.Dll|RPCRT4.Dll|Rtm。Dll|
|RTUTILS.Dll|スカードルグ。Dll|SECUR32.Dll|センサピ。Dll|
|Setupapi。Dll|Sfc。Dll|Shell32。Dll|シュフォルダ。Dll|
|SHLWAPI.Dll|シスブクップ。Dll|SNMPAPI.Dll|SRクライアント。Dll|
|Sti。Dll|TAPI32.Dll|トラフィック。Dll|Url。Dll|
|URLMON.Dll|User32。Dll|Userenv。Dll|USP10.Dll|
|UXTHEME.Dll|VDMDBG.Dll|バージョン。Dll|ウィンファックス。Dll|
|WINHTTP。Dll|Wininet。Dll|ウィンMM。Dll|WINSカード。Dll|
|ウィントラスト。Dll|WLDAP32.Dll|WOW32.Dll|WS2_32.DLL|
|WSNMP32.Dll|WSOCK32.DLL|WTSAPI32.Dll|1000Dll|

> [!NOTE]
> 最後のエラーを保持することは、同じモジュール内の CLR コードで使用されるアンマネージ関数ではサポートされていません。

- 詳細については、「 [/clr (共通言語ランタイムのコンパイル)」](clr-common-language-runtime-compilation.md)を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加オプション] ボックスに**オプション**を入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="example"></a>例

次のサンプルでは、最後のエラーを変更する 1 つのエクスポート関数を持つネイティブ DLL を定義します。

```cpp
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

次のサンプルでは、DLL を使用して **、/CLRSUPPORTLASTERROR**の使用方法を示します。

```cpp
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

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
