---
description: '詳細情報: コンパイラオプション'
title: MSVC コンパイラオプション
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: a6b124fa5fce68844d53c1324da48c17ef5a9ccf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197024"
---
# <a name="compiler-options"></a>コンパイラ オプション

cl.exe は、Microsoft C++ (MSVC) C および C++ コンパイラとリンカーを制御するツールです。 cl.exe は、Windows の Microsoft Visual Studio をサポートするオペレーティングシステムでのみ実行できます。

> [!NOTE]
> このツールは Visual Studio 開発者コマンド プロンプトからのみ起動できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。 詳細については、「[コマンド ラインから MSVC ツールセットを使用する](../building-on-the-command-line.md)」を参照してください。

コンパイラは、COFF (Common Object File Format) 形式のオブジェクト (.obj) ファイルを生成します。 リンカーは、実行可能 (.exe) ファイルまたはダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) を生成します。

すべてのコンパイラ オプションで、大文字小文字を区別します。 スラッシュ () またはダッシュ () のいずれかを使用して、コンパイラオプションを指定することができ `/` `-` ます。

リンクせずにコンパイルするには、 [/c](c-compile-without-linking.md) オプションを使用します。

## <a name="find-a-compiler-option"></a>コンパイラオプションの検索

特定のコンパイラ オプションを見つけるには、次のいずれかの一覧を参照してください。

- [アルファベット順のコンパイラ オプション](compiler-options-listed-alphabetically.md)

- [カテゴリ別のコンパイラオプションの一覧](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>コンパイラオプションの指定

開発環境での設定方法は、コンパイラの各オプションのトピックで説明します。 開発環境以外からオプションを指定する方法の詳細については、下記を参照してください。

- [MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)

- [CL コマンドファイル](cl-command-files.md)

- [CL 環境変数](cl-environment-variables.md)

## <a name="related-build-tools"></a>関連するビルドツール

[MSVC リンカーオプション](linker-options.md) は、プログラムの構築方法にも影響します。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)<br/>
[CL がリンカーを呼び出します。](cl-invokes-the-linker.md)
