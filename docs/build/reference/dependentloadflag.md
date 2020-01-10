---
title: /DEPENDENTLOADFLAG (既定の依存ロード フラグの設定)
description: /Dependentloadflag オプションは、LoadLibrary を使用して読み込まれた Dll の既定のフラグを設定します。
ms.date: 12/22/2018
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 3a403f22c88ccd3e25ba95c183656ad2ffafd05a
ms.sourcegitcommit: ef34a11cb04511221bf5c7b9f4f55ad91a7a603f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/23/2019
ms.locfileid: "75329999"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (既定の依存ロード フラグの設定)

`LoadLibrary` が Dll の読み込みに使用されるときに使用される既定の読み込みフラグを設定します。

## <a name="syntax"></a>構文

> **/Dependentloadflag**[ __:__ *load_flags*]

### <a name="arguments"></a>引数

*load_flags*<br/>
すべての [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) 呼び出しに適用する依存読み込みフラグを指定する、省略可能な "C" スタイルの16ビット整数値`0x`(10 進数)、8進数 (先行ゼロ付き)、または先頭を持つ16進数。 既定値は 0 です。

## <a name="remarks"></a>コメント

このオプションは、Visual Studio 2017 の新機能です。 これは、Windows 10 RS1 以降のバージョンで実行されているアプリにのみ適用されます。 このオプションは、アプリを実行する他のオペレーティングシステムでは無視されます。

サポートされているオペレーティングシステムでは、このオプションは、`LoadLibrary("dependent.dll")` の呼び出しを `LoadLibraryEx("dependent.dll", 0, load_flags)`と同等のものに変更した場合の効果があります。 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)への呼び出しは影響を受けません。 このオプションは、アプリによって読み込まれる Dll には再帰的には適用されません。

このフラグは、 [DLL 植栽攻撃](/windows/win32/dlls/dynamic-link-library-security)をより困難にするために使用できます。 たとえば、アプリが `LoadLibrary` を使用して依存 DLL を読み込む場合、攻撃者は、現在のディレクトリなど、`LoadLibrary`で使用される検索パスに同じ名前の DLL を送り込むことができます。これは、安全な DLL 検索モードが無効になっている場合に、システムディレクトリの前にチェックされる可能性があります。 セーフ DLL 検索モードでは、ユーザーの現在のディレクトリが検索順序の後に配置され、Windows XP SP2 以降のバージョンでは既定で有効になります。 詳細については、「[ダイナミックリンクライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)」を参照してください。

`/DEPENDENTLOADFLAG:0xA00` リンクオプション (結合されたフラグの値 `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`) を指定した場合、ユーザーのコンピューターで安全な DLL 検索モードが無効になっていても、DLL 検索パスはアプリケーションディレクトリに限定され、その後に%windows%\system32 ディレクトリが続きます。 `/DEPENDENTLOADFLAG:0x800` のオプションは、%windows%\system32 ディレクトリに対する検索を制限して、さらに制限があります。 保護されたディレクトリは、攻撃者が変更するのが困難ですが、不可能ではありません。 使用可能なフラグ、およびそれらのシンボル値と数値については、 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)の「 *dwFlags*パラメーターの説明」を参照してください。 さまざまな依存する読み込みフラグが使用されている場合に使用される検索順序の詳細については、「 [LOAD_LIBRARY_SEARCH フラグを使用した検索順序](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags)」を参照してください。

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で DEPENDENTLOADFLAG リンカーオプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[リンカー]**  >  **[コマンド ライン]** プロパティ ページを選択します。

1. **[追加オプション]** にオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
- [実行可能ファイルと DLL のリンク](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [実行可能ファイルと DLL のリンク](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [ダイナミックリンクライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)
