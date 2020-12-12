---
description: 詳細情報:/SAFESEH (安全な例外ハンドラーがあるイメージ)
title: /SAFESEH (安全な例外ハンドラーがあるイメージ)
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 723b5503bca1d98d7df0c638df1dfc8101fc116f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224986"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (安全な例外ハンドラーがあるイメージ)

```
/SAFESEH[:NO]
```

**/Safeseh** を指定すると、イメージの安全な例外ハンドラーのテーブルも生成できる場合にのみ、リンカーによってイメージが生成されます。 このテーブルは、どの例外ハンドラーがイメージに対して有効であるかをオペレーティング システムに指定します。

**/Safeseh** は、x86 ターゲットにリンクする場合にのみ有効です。 例外ハンドラーが既に記載されているプラットフォームでは、 **/safeseh** はサポートされていません。 たとえば、x64 と ARM では、すべての例外ハンドラーが PDATA に記載されています。 ML64.exe には、コメントを追加して SEH 情報 (XDATA および PDATA) をイメージに出力する機能をサポートしているため、ml64 関数からのアンワインドが可能です。 詳細については、「 [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) 」を参照してください。

**/Safeseh** が指定されていない場合、すべてのモジュールが安全な例外処理機能と互換性がある場合、リンカーは安全な例外ハンドラーのテーブルを含むイメージを生成します。 いずれかのモジュールに安全な例外処理機能との互換性がない場合、生成されるイメージには安全な例外ハンドラーのテーブルが含まれません。 [/SUBSYSTEM](subsystem-specify-subsystem.md)が WINDOWSCE またはいずれかの EFI_ * オプションを指定すると、リンカーは安全な例外ハンドラーのテーブルを含むイメージの生成を試行しません。これらのサブシステムでは、情報を利用できないためです。

**/Safeseh: NO** を指定した場合、すべてのモジュールが安全な例外処理機能と互換性がある場合でも、リンカーは安全な例外ハンドラーのテーブルを含むイメージを生成しません。

リンカーがイメージを生成できない最も一般的な理由は、リンカーへの入力ファイル (モジュール) の 1 つ以上に、安全な例外ハンドラー機能との互換性がないためです。 モジュールに安全な例外ハンドラーとの互換性がない一般的な理由は、以前のバージョンの Visual C++ のコンパイラでそのモジュールが作成されているためです。

また、を使用して、関数を構造化例外ハンドラーとして登録することもでき [ます。SAFESEH](../../assembler/masm/dot-safeseh.md)。

既存のバイナリを、安全な例外ハンドラーがある、または例外ハンドラーがないものとしてマークすることはできません。安全な例外処理の情報は、ビルド時に追加する必要があります。

リンカーが安全な例外ハンドラーのテーブルを生成できるかどうかは、C ランタイム ライブラリを使用しているアプリケーションによって決まります。 [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md)とリンクし、安全な例外ハンドラーのテーブルが必要な場合は、Visual C++ に定義されているすべてのエントリを含む load config 構造体 (たとえば、loadcfg. c CRT ソースファイルにある) を指定する必要があります。 次に例を示します。

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

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション** ] ボックスにオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
