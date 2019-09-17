---
title: /DEPENDENTLOADFLAG (既定の依存ロード フラグの設定)
description: /Dependentloadflag オプションは、LoadLibrary を使用して読み込まれた Dll の既定のフラグを設定します。
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 072fa1103d049c7d5c395ae88d268f3b47e20b4f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492951"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (既定の依存ロード フラグの設定)

が dll の読み込みに使用さ`LoadLibrary`れるときに使用される既定の読み込みフラグを設定します。

## <a name="syntax"></a>構文

> **/DEPENDENTLOADFLAG**[ **:** _loadflags_]

### <a name="arguments"></a>引数

*loadflags*<br/>
すべての [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) 呼び出しに適用する依存読み込みフラグを指定する、省略可能な "C" スタイルの16ビット整数値`0x`(10 進数)、8進数 (先行ゼロ付き)、または先頭を持つ16進数。 既定値は 0 です。

## <a name="remarks"></a>Remarks

このオプションは Visual Studio 2017 の新機能であり、Windows 10 RS1 以降のバージョンで実行されているアプリにのみ適用されます。 このオプションは、アプリを実行する他のオペレーティングシステムでは無視されます。

サポートされているオペレーティングシステムでは、このオプションはの`LoadLibrary("dependent.dll")`呼び出しをの`LoadLibraryEx("dependent.dll", 0, loadflags)`同等のに変更した場合の効果があります。 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)への呼び出しは影響を受けません。 このオプションは、アプリによって読み込まれる Dll には再帰的には適用されません。

このフラグは、DLL の植栽攻撃を防ぐために使用できます。 たとえば、アプリでを使用`LoadLibrary`して依存 dll を読み込む場合、攻撃者は、現在のディレクトリなど、で`LoadLibrary`使用される検索パスに同じ名前の dll を送り込むことができます。これは、安全な dll 検索モードが実行されている場合、システムディレクトリの前にチェックされる可能性があります。無効に. セーフ DLL 検索モードでは、ユーザーの現在のディレクトリが検索順序の後に配置され、Windows XP SP2 以降のバージョンでは既定で有効になります。 詳細については、「[ダイナミックリンクライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)」を参照してください。

リンクオプション`/DEPENDENTLOADFLAG:0xA00` (結合されたフラグ`LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`の値) を指定した場合、ユーザーのコンピューターで安全な dll 検索モードが無効になっていても、dll 検索パスは保護されたディレクトリに制限され、攻撃者による攻撃を受けにくくなります。変更. 使用可能なフラグ、およびそれらのシンボル値と数値については、 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)の「 *dwFlags*パラメーターの説明」を参照してください。

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で DEPENDENTLOADFLAG リンカーオプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ** > ] [**リンカー** > **コマンドライン**] プロパティページを選択します。

1. **[追加オプション]** にオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
- [実行可能ファイルと DLL のリンク](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [実行可能ファイルと DLL のリンク](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [ダイナミックリンクライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)
