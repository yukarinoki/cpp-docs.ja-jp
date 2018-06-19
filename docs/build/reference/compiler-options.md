---
title: コンパイラ オプション |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler
- x86 Visual C++ compiler
- ARM Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bea07361a292ee5e7cde99cedad2d5ac4c8a53aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374278"
---
# <a name="compiler-options"></a>コンパイラ オプション

cl.exe は、Microsoft Visual C++ (MSVC) C と C++ コンパイラおよびリンカーを制御するツールです。 cl.exe は、Microsoft Visual Studio for Windows をサポートするオペレーティング システムでのみ実行できます。

> [!NOTE]  
> このツールは、Visual Studio 開発者コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。 詳細については、次を参照してください。[コマンドラインでビルドの c/c++ コード](../building-on-the-command-line.md)です。

コンパイラは、COFF (Common Object File Format) 形式のオブジェクト (.obj) ファイルを生成します。 リンカーは、実行可能 (.exe) ファイルまたはダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) を生成します。

すべてのコンパイラ オプションで、大文字小文字を区別します。 いずれかにスラッシュを使用する場合があります (`/`) またはダッシュ (`-`) コンパイラ オプションを指定します。

リンクなしでコンパイルを使用して、 [/c](../../build/reference/c-compile-without-linking.md)オプション。

## <a name="find-a-compiler-option"></a>コンパイラ オプションを見つける

特定のコンパイラ オプションを見つけるには、次のいずれかの一覧を参照してください。

- [アルファベット順のコンパイラ オプション](../../build/reference/compiler-options-listed-alphabetically.md)

- [カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>コンパイラ オプションを指定します

開発環境での設定方法は、コンパイラの各オプションのトピックで説明します。 開発環境以外からオプションを指定する方法の詳細については、下記を参照してください。

- [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)

- [CL コマンド ファイル](../../build/reference/cl-command-files.md)

- [CL 環境変数](../../build/reference/cl-environment-variables.md)

## <a name="related-build-tools"></a>関連ビルド ツール

[リンカー オプション](../../build/reference/linker-options.md)プログラムのビルド方法にも影響します。

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
[高速コンパイル](../../build/reference/fast-compilation.md)  
[リンカーを呼び出す CL](../../build/reference/cl-invokes-the-linker.md)  
