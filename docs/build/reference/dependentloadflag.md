---
title: /DEPENDENTLOADFLAG (既定の依存ロード フラグの設定)
description: /Dependentloadflag オプションは、このモジュールによって読み込まれる Dll に対して、既定の依存読み込みフラグを設定します。
ms.date: 01/22/2020
f1_keywords:
- dependentloadflag
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
ms.openlocfilehash: 8d0f53ed13143ed7ff5c507df73937a86c07b5b8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924203"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/DEPENDENTLOADFLAG (既定の依存ロード フラグの設定)

::: moniker range="msvc-140"

**/Dependentloadflag** オプションには、Visual Studio 2017 以降が必要です。

::: moniker-end

::: moniker range=">=msvc-150"

オペレーティングシステムが、静的にリンクされたモジュールのインポートを解決するときに使用される既定の読み込みフラグを設定します。

## <a name="syntax"></a>Syntax

> **/Dependentloadflag** [ __:__*load_flags* ]

### <a name="arguments"></a>引数

*load_flags*<br/>
モジュールの静的にリンクされたインポート依存関係を解決するときに適用する読み込みフラグを指定する、省略可能な整数値。 既定値は 0 です。 サポートされているフラグ値の一覧については、 `LOAD_LIBRARY_SEARCH_*` [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)のエントリを参照してください。

## <a name="remarks"></a>注釈

オペレーティングシステムによって、静的にリンクされたモジュールのインポートが解決されると、 [既定の検索順序](/windows/win32/dlls/dynamic-link-library-search-order)が使用されます。 **/Dependentloadflag** オプションを使用して、これらのインポートの解決に使用される検索パスを変更する *load_flags* 値を指定します。 サポートされているオペレーティングシステムでは、パラメーターを使用する場合の [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexa) の場合と同様に、静的なインポートの解決の検索順序が変更され `LOAD_LIBRARY_SEARCH` ます。 *Load_flags* による検索順序の詳細については、「 [LOAD_LIBRARY_SEARCH フラグを使用し](/windows/win32/dlls/dynamic-link-library-search-order#search-order-using-load_library_search-flags)た検索順序」を参照してください。

このフラグを使用すると、1つの [DLL 植栽攻撃](/windows/win32/dlls/dynamic-link-library-security) ベクトルをより困難にすることができます。 たとえば、DLL を静的にリンクしたアプリについて考えてみましょう。

- 攻撃者は、アプリケーションディレクトリなど、インポート解決の検索パスで前に同じ名前の DLL をプラントに送り込むことができます。 保護されたディレクトリは、攻撃者が変更するのが困難ですが、不可能ではありません。

- アプリケーション、%windows%\system32、および% windows% ディレクトリに DLL がない場合、インポートの解決は現在のディレクトリに分類されます。 攻撃者は、そこに DLL を送り込むことができます。

どちらの場合も、link オプション `/DEPENDENTLOADFLAG:0x800` (フラグの値) を指定すると、 `LOAD_LIBRARY_SEARCH_SYSTEM32` モジュールの検索パスは%windows%\system32 ディレクトリに制限されます。 他のディレクトリに対する植栽攻撃からの保護を提供します。 詳細については、「 [ダイナミックリンクライブラリのセキュリティ](/windows/win32/dlls/dynamic-link-library-security)」を参照してください。

任意の DLL の **/dependentloadflag** オプションによって設定された値を表示するには、 [DUMPBIN](dumpbin-reference.md) コマンドを使用して、 [/loadconfig](loadconfig.md) オプションです。

**/Dependentloadflag** オプションは、Visual Studio 2017 の新機能です。 これは、Windows 10 RS1 以降のバージョンで実行されているアプリにのみ適用されます。 このオプションは、アプリを実行する他のオペレーティングシステムでは無視されます。

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境で DEPENDENTLOADFLAG リンカーオプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** > **[リンカー]** > **[コマンド ライン]** プロパティ ページを選択します。

1. [ **追加オプション** ] にオプションを入力します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>こちらもご覧ください

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
- [実行可能ファイルを DLL に暗黙的にリンクする](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [リンク方式の使い分け](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)
- [ダイナミックリンク ライブラリの検索順序](/windows/win32/Dlls/dynamic-link-library-search-order)
- [ダイナミックリンクライブラリのセキュリティ](/windows/win32/dlls/dynamic-link-library-security)

::: moniker-end
