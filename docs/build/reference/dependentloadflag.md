---
title: /DEPENDENTLOADFLAG (既定依存読み込みフラグを設定します)
description: /DEPENDENTLOADFLAG オプションは、LoadLibrary を使用して読み込まれた Dll の既定のフラグを設定します。
ms.date: 05/18/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 94998e06f23a7e70524221d3cb75166b5d3f2c44
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815971"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (既定依存読み込みフラグを設定します)

既定の負荷のフラグを設定するときに使用`LoadLibrary`Dll を読み込むために使用します。

## <a name="syntax"></a>構文

> **/DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>引数

*loadflags*<br/>
10 進数、先行ゼロの場合は、8 進数または先頭の 16 進数のオプション"C"スタイル 16 ビット整数値`0x`、すべてに適用する依存読み込みフラグを指定する[LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)呼び出し。 既定値は 0 です。

## <a name="remarks"></a>Remarks

このオプションは、Visual Studio 2017 の新機能は、Windows 10 RS1 以降で実行されているアプリにのみ適用されます。 このオプションは、アプリを実行するその他のオペレーティング システムで無視されます。

サポートされるオペレーティング システムでは、このオプションがへの呼び出しを変更した効果`LoadLibrary("dependent.dll")`を同等の`LoadLibraryEx("dependent.dll", 0, loadflags)`します。 呼び出す[LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)は影響を受けません。 このオプションでは、アプリを読み込んだ Dll を再帰的には適用されません。

このフラグは、攻撃を仕掛ける DLL を防ぐために使用できます。 たとえば、アプリで使用`LoadLibrary`依存 DLL を読み込むには、攻撃者で使用される検索パスに同じ名前の DLL を工場でした`LoadLibrary`、現在のディレクトリなどセーフ DLL の検索モードがある場合、システムのディレクトリの前にするチェック可能性があります無効になります。 セーフ DLL の検索モードでは、検索の順序で後で、ユーザーの現在のディレクトリに配置し、Windows XP SP2 以降では既定で有効にします。 詳細については、[ダイナミック リンク ライブラリの検索順序](/windows/desktop/Dlls/dynamic-link-library-search-order)を参照してください。

リンク オプションを指定する場合`/DEPENDENTLOADFLAG:0xA00`(結合フラグの値`LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`)、DLL 検索パスは、攻撃者がより困難である保護されたディレクトリに制限ユーザーのコンピューターに安全な DLL の検索モードが無効の場合でも変更します。 使用可能なフラグと、そのシンボリックと数値の値は、、 *dwFlags*パラメーターの説明を[LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)を参照してください。

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で DEPENDENTLOADFLAG リンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**構成プロパティ** > **リンカー** > **コマンドライン**プロパティ ページ。

1. オプションを入力して**追加オプション**します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

- [MSVC リンカーの参照](linking.md)
- [MSVC リンカー オプション](linker-options.md)
- [実行可能ファイルと DLL のリンク](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [実行可能ファイルと DLL のリンク](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa)
- [ダイナミック リンク ライブラリの検索順序](/windows/desktop/Dlls/dynamic-link-library-search-order)
