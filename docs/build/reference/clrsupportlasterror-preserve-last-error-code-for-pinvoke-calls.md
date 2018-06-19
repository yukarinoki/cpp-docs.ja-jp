---
title: -CLRSUPPORTLASTERROR (Preserve 最終エラー コードの PInvoke 呼び出し) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRSUPPORTLASTERROR
dev_langs:
- C++
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 297414aa71e9d871da795c2ffe567573237c7e0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378637"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (PInvoke 呼び出しの最終エラー コードの保持)
**/CLRSUPPORTLASTERROR**、既定でオンになっている、DLL 内のコードからネイティブ関数を呼び出すことができる P/invoke 機構を通じて呼び出された関数の最後のエラー コードを保持してコンパイルした **/clr**です。  
  
## <a name="syntax"></a>構文  
  
```  
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}  
```  
  
## <a name="remarks"></a>コメント  
 最後のエラー コードを保持するには、パフォーマンスの低下が含まれます。  最後のエラー コードを維持するためのパフォーマンスに与える影響が発生しないようにする場合とリンク **/CLRSUPPORTLASTERROR:NO**です。  
  
 リンクして、パフォーマンスに与える影響を最小限に抑えることができます **/CLRSUPPORTLASTERROR:SYSTEMDLL**、システム Dll の関数の最後のエラー コードだけが保護されます。  システム DLL は、次のいずれかとして定義されます。  
  
|||||  
|-|-|-|-|  
|ACLUI です。DLL|ACTIVEDS です。DLL|ADPTIF です。DLL|ADVAPI32 です。DLL|  
|ASYCFILT です。DLL|AUTHZ です。DLL|AVICAP32 です。DLL|AVIFIL32 です。DLL|  
|キャビネットします。DLL|CLUSAPI です。DLL|COMCTL32 です。DLL|COMDLG32 です。DLL|  
|COMSVCS です。DLL|CREDUI です。DLL|CRYPT32 です。DLL|CRYPTNET です。DLL|  
|CRYPTUI です。DLL|D3D8THK です。DLL|DBGENG です。DLL|DBGHELP です。DLL|  
|DCIMAN32 です。DLL|DNSAPI です。DLL|DSPROP です。DLL|DSUIEXT です。DLL|  
|GDI32 です。DLL|GLU32 です。DLL|HLINK です。DLL|ICM32 です。DLL|  
|IMAGEHLP です。DLL|IMM32 です。DLL|IPHLPAPI です。DLL|IPROP です。DLL|  
|KERNEL32 です。DLL|KSUSER です。DLL|「LOADPERF」です。DLL|LZ32 です。DLL|  
|MAPI32 です。DLL|MGMTAPI です。DLL|MOBSYNC です。DLL|MPR です。DLL|  
|MPRAPI です。DLL|MQRT です。DLL|MSACM32 です。DLL|MSCMS です。DLL|  
|MSI です。DLL|MSIMG32 です。DLL|MSRATING です。DLL|MSTASK です。DLL|  
|MSVFW32 です。DLL|MSWSOCK です。DLL|MTXEX です。DLL|NDDEAPI です。DLL|  
|NETAPI32 です。DLL|NPPTOOLS です。DLL|NTDSAPI です。DLL|NTDSBCLI です。DLL|  
|NTMSAPI です。DLL|ODBC32 です。DLL|ODBCBCP です。DLL|OLE32 です。DLL|  
|OLEACC です。DLL|OLEAUT32 です。DLL|OLEDLG です。DLL|OPENGL32 です。DLL|  
|PDH です。DLL|POWRPROF です。DLL|QOSNAME です。DLL|クエリを実行します。DLL|  
|RASAPI32 です。DLL|RASDLG です。DLL|RASSAPI です。DLL|RESUTILS です。DLL|  
|RICHED20 です。DLL|RPCNS4 です。DLL|RPCRT4 です。DLL|RTM です。DLL|  
|RTUTILS です。DLL|SCARDDLG です。DLL|SECUR32 です。DLL|SENSAPI です。DLL|  
|SETUPAPI です。DLL|SFC です。DLL|SHELL32 です。DLL|SHFOLDER です。DLL|  
|SHLWAPI です。DLL|SISBKUP です。DLL|SNMPAPI です。DLL|SRCLIENT です。DLL|  
|STI です。DLL|TAPI32 です。DLL|トラフィック。DLL|URL です。DLL|  
|URLMON です。DLL|USER32 です。DLL|USERENV です。DLL|USP10 です。DLL|  
|UXTHEME です。DLL|VDMDBG です。DLL|バージョン。DLL|WINFAX です。DLL|  
|WINHTTP です。DLL|WININET の基礎です。DLL|WINMM です。DLL|WINSCARD です。DLL|  
|WINTRUST です。DLL|WLDAP32 です。DLL|WOW32 です。DLL|WS2_32.DLL|  
|WSNMP32 です。DLL|WSOCK32.DLL|WTSAPI32 です。DLL|XOLEHLP です。DLL|  
  
> [!NOTE]
>  最後のエラーを保持するは、同じモジュールでの CLR コードで使用されるアンマネージ関数ではサポートされていません。  
  
-   詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、最後のエラーを修正する 1 つのエクスポートされた関数をネイティブ DLL を定義します。  
  
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
 次の例を使用する方法を示す、DLL を消費する **/CLRSUPPORTLASTERROR**です。  
  
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
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)