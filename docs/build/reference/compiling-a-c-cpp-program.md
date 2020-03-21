---
title: MSVC C/C++コンパイラリファレンス-Visual Studio
description: MSVC コンパイラツールセットのオプション。
ms.date: 12/10/2018
helpviewer_keywords:
- cl.exe compiler
- cl.exe compiler, setting options
ms.assetid: f3eef5ab-d0be-4fb2-90f9-927e6ed58736
ms.openlocfilehash: c75176b139895d7b00d88aca1c58604b47386894
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077372"
---
# <a name="compiling-a-cc-project"></a>C/C++プロジェクトのコンパイル

C およびC++コンパイラオプションは、VISUAL Studio IDE またはコマンドラインで設定できます。

## <a name="in-visual-studio"></a>Visual Studio で使用する

Visual Studio の **[プロパティページ]** ダイアログボックスで、各プロジェクトのコンパイラオプションを設定できます。 左側のウィンドウで、 **[構成プロパティ]** 、 **[C/C++ ]** の順に選択し、[コンパイラオプション] カテゴリを選択します。 各コンパイラ オプションのトピックで、開発環境でオプションを設定する方法と、そのオプションがどこにあるかを説明します。 完全な一覧については、「 [MSVC Compiler Options](compiler-options.md) 」を参照してください。

## <a name="from-the-command-line"></a>コマンド ラインから

コンパイラ (CL.exe) オプションは、次のいずれかで設定できます。

- [コマンドラインで](compiler-command-line-syntax.md)

- [コマンドファイル内](cl-command-files.md)

- [CL 環境変数内](cl-environment-variables.md)

環境変数 CL で指定したオプションは、CL を起動するたびに使用されます。 環境変数 CL またはコマンド ラインでコマンド ファイルを指定すると、そのコマンド ファイルに指定されているオプションが使用されます。 コマンド ラインまたは環境変数 CL ではオプションとファイル名を 1 行しか指定できませんが、コマンド ファイルでは複数行指定できます。

コンパイラ オプションは、"左から右" に処理されます。オプションが競合する場合は、最後の、つまり一番右のオプションが優先されます。 CL とコマンド ラインが競合した場合は、コマンド ラインが優先されます。環境変数 CL の処理後にコマンド ラインが処理されるからです。

## <a name="additional-compiler-topics"></a>コンパイラに関するその他のトピック

- [MSVC コンパイラ オプション](compiler-options.md)

- [プリコンパイル済みヘッダー ファイル](../creating-precompiled-header-files.md)

- [リンカーを呼び出す CL](cl-invokes-the-linker.md)

コンパイラホストとターゲットアーキテクチャの選択の詳細については、「 [64 ビット、x64 ターゲットのプロジェクトを構成するC++ ](../configuring-programs-for-64-bit-visual-cpp.md)」を参照してください。

## <a name="see-also"></a>参照

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)
