---
title: MSVC コンパイラ オプション
ms.date: 01/29/2018
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: 831aade72cd728ec42aee5ef1f320deb7bdf173d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816517"
---
# <a name="compiler-options"></a>コンパイラ オプション

cl.exe は、Microsoft Visual C (MSVC) C と C++ コンパイラとリンカーを制御するツールです。 cl.exe は、Microsoft Visual Studio for Windows をサポートするオペレーティング システムでのみ実行できます。

> [!NOTE]
> このツールは、Visual Studio 開発者コマンド プロンプトからのみ起動できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。 詳細については、次を参照してください。[コマンドラインから MSVC ツールセットを使用して](../building-on-the-command-line.md)します。

コンパイラは、COFF (Common Object File Format) 形式のオブジェクト (.obj) ファイルを生成します。 リンカーは、実行可能 (.exe) ファイルまたはダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) を生成します。

すべてのコンパイラ オプションで、大文字小文字を区別します。 いずれかにスラッシュを使用することがあります (`/`) またはダッシュ (`-`) コンパイラ オプションを指定します。

リンクなしでコンパイルを使用して、 [/c](c-compile-without-linking.md)オプション。

## <a name="find-a-compiler-option"></a>コンパイラ オプションを見つける

特定のコンパイラ オプションを見つけるには、次のいずれかの一覧を参照してください。

- [アルファベット順のコンパイラ オプション](compiler-options-listed-alphabetically.md)

- [カテゴリ別のコンパイラ オプション](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>コンパイラ オプションを指定します

開発環境での設定方法は、コンパイラの各オプションのトピックで説明します。 開発環境以外からオプションを指定する方法の詳細については、下記を参照してください。

- [MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)

- [CL コマンド ファイル](cl-command-files.md)

- [CL 環境変数](cl-environment-variables.md)

## <a name="related-build-tools"></a>関連するビルド ツール

[MSVC リンカー オプション](linker-options.md)プログラムの構築方法にも影響します。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](c-cpp-building-reference.md)<br/>
[リンカーを呼び出す CL](cl-invokes-the-linker.md)
