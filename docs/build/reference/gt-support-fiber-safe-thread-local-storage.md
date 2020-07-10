---
title: /GT (スレッド ローカル ストレージを使用したファイバー保護のサポート)
description: MSVC コンパイラオプション/GT は、スレッドローカルストレージデータの安全な最適化を有効にします。
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 1b1d9f6514cec8c3d247f86be063f2ac3e0dfe72
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180813"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>`/GT`(ファイバーセーフスレッドローカルストレージをサポートします)

は、静的スレッドローカルストレージを使用して割り当てられたデータ (つまり、で割り当てられたデータ) のファイバー安全をサポート `__declspec(thread)` します。

## <a name="syntax"></a>構文

> **`/GT`**

## <a name="remarks"></a>解説

で宣言 `__declspec(thread)` されたデータは、スレッドローカルストレージ (TLS) 配列を介して参照されます。 TLS 配列は、システムが各スレッドに対して保持するアドレスの配列です。 この配列の各アドレスによって、スレッドローカルストレージデータの場所が指定されます。

ファイバーは、スタックとレジスタコンテキストで構成される軽量オブジェクトであり、さまざまなスレッドでスケジュールできます。 ファイバーは任意のスレッドで実行できます。 ファイバーはスワップアウトされ、後で別のスレッドで再起動される可能性があるため、コンパイラは TLS 配列のアドレスをしないにキャッシュするか、関数呼び出し全体で共通の部分式として最適化します。 **`/GT`** このような最適化を防止します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **最適化**] プロパティページを選択します。

1. [**ファイバーセーフ最適化を有効にする**] プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
