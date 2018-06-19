---
title: -SAFESEH (イメージは、安全な例外ハンドラーを持つ) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54d13e6922650f0193d4bbc3469d4acf25904234
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377910"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (安全な例外ハンドラーがあるイメージ)
```  
/SAFESEH[:NO]  
```  
  
 ときに **/SAFESEH**が指定されている、リンカーはイメージの安全な例外ハンドラーのテーブルも生成できる場合、イメージ生成のみです。 このテーブルは、どの例外ハンドラーがイメージに対して有効であるかをオペレーティング システムに指定します。  
  
 **/SAFESEH**のみが有効では x86 のものをリンクするときのターゲットです。 **/SAFESEH**例外ハンドラーが既にあるプラットフォームでサポートされていません。 たとえば、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] および ARM では、すべての例外ハンドラーは PDATA にコメントされています。 ML64.exe には、コメントを追加して SEH 情報 (XDATA および PDATA) をイメージに出力する機能をサポートしているため、ml64 関数からのアンワインドが可能です。 参照してください[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)詳細についてはします。  
  
 場合 **/SAFESEH**が指定されていない、リンカーはイメージを生成および安全な例外ハンドラーのテーブルのすべてのモジュールに安全な例外処理機能との互換性がある場合。 いずれかのモジュールに安全な例外処理機能との互換性がない場合、生成されるイメージには安全な例外ハンドラーのテーブルが含まれません。 場合[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) WINDOWSCE または efi _ *、オプションのいずれかを示すサブシステムを行えるよう、リンカーはイメージおよび安全な例外ハンドラーのテーブルを生成を試行しません情報を使用します。  
  
 場合 **/SAFESEH:NO**が指定されている、リンカーは場合でも、すべてのモジュールが安全な例外処理機能と互換性のある安全な例外ハンドラーのテーブルを使用してイメージを生成しません。  
  
 リンカーがイメージを生成できない最も一般的な理由は、リンカーへの入力ファイル (モジュール) の 1 つ以上に、安全な例外ハンドラー機能との互換性がないためです。 モジュールに安全な例外ハンドラーとの互換性がない一般的な理由は、以前のバージョンの Visual C++ のコンパイラでそのモジュールが作成されているためです。  
  
 使用して、構造化例外ハンドラーとして関数を登録することも[します。SAFESEH](../../assembler/masm/dot-safeseh.md)です。  
  
 既存のバイナリを、安全な例外ハンドラーがある、または例外ハンドラーがないものとしてマークすることはできません。安全な例外処理の情報は、ビルド時に追加する必要があります。  
  
 リンカーが安全な例外ハンドラーのテーブルを生成できるかどうかは、C ランタイム ライブラリを使用しているアプリケーションによって決まります。 リンクする場合[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)いて安全な例外ハンドラーのテーブル、読み込み構成構造体 (loadcfg.c CRT ソース ファイルで見つかりますなど) を指定する必要があります。 Visual c に対して定義されているすべてのエントリを格納しています。 例えば:  
  
```  
#include <windows.h>  
extern DWORD_PTR __security_cookie;  /* /GS security cookie */  
  
/*  
 * The following two names are automatically created by the linker for any  
 * image that has the safe exception table present.  
*/  
  
extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */  
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is  
                                           the count of table entries */  
typedef struct {  
    DWORD       Size;  
    DWORD       TimeDateStamp;  
    WORD        MajorVersion;  
    WORD        MinorVersion;  
    DWORD       GlobalFlagsClear;  
    DWORD       GlobalFlagsSet;  
    DWORD       CriticalSectionDefaultTimeout;  
    DWORD       DeCommitFreeBlockThreshold;  
    DWORD       DeCommitTotalFreeThreshold;  
    DWORD       LockPrefixTable;            // VA  
    DWORD       MaximumAllocationSize;  
    DWORD       VirtualMemoryThreshold;  
    DWORD       ProcessHeapFlags;  
    DWORD       ProcessAffinityMask;  
    WORD        CSDVersion;  
    WORD        Reserved1;  
    DWORD       EditList;                   // VA  
    DWORD_PTR   *SecurityCookie;  
    PVOID       *SEHandlerTable;  
    DWORD       SEHandlerCount;  
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;  
  
const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {  
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    0,  
    &__security_cookie,  
    __safe_se_handler_table,  
    (DWORD)(DWORD_PTR) &__safe_se_handler_count  
};  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  オプションを入力して、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)