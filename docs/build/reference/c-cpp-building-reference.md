---
title: C/C++ ビルドのリファレンス |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 116ddca6ed9f5e0b3ea02652958931f88cc8fc13
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703223"
---
# <a name="cc-building-reference"></a>C/C++ ビルドのリファレンス

Visual C には、C/C++ プログラムのビルドの 2 つの方法が用意されています。 最も簡単な (および最も一般的な) 方法は、する[Visual C 開発環境でビルド](../../ide/building-cpp-projects-in-visual-studio.md)します。 その他の方法は、する[コマンド ライン ツールを使用してコマンド プロンプトからビルド](../../build/building-on-the-command-line.md)します。 どちらの場合は、Visual C のソース エディターまたは任意のサード パーティ製エディターを使用して、ソース ファイルを作成できます。

プログラムでは、.vcxproj ファイルではなく、メイクファイルを使用する場合でもビルドできることとして、開発環境で、[外部プロジェクト](../../ide/building-external-projects.md)します。

## <a name="in-this-section"></a>このセクションの内容

[C/C++ プログラムのコンパイル](../../build/reference/compiling-a-c-cpp-program.md)マシン語コード、リンカー ディレクティブ、セクションでは、外部参照、および関数/データの名前を格納しているオブジェクト ファイルを作成すると、コンパイラについて説明します。

[リンク](../../build/reference/linking.md)名の参照を解決し、実行可能ファイルを作成、リンカーは、コンパイラによって作成されたオブジェクト ファイルと静的にリンクされたライブラリからコードを組み合わせると、について説明します。

[リリース ビルド](../../build/reference/release-builds.md)デバッグ ビルドからリリース ビルドに変更する理由とタイミングの情報を表示し、デバッグからリリース ビルドに変更するときに発生する問題のいくつかについても説明します。

[コードの最適化](../../build/reference/optimizing-your-code.md)コードを最適化するためのメカニズムについて説明するトピックへのリンクを提供します。

[C/C++ ビルド ツール](../../build/reference/c-cpp-build-tools.md)を表示またはビルド出力を操作するために、次のコマンド ライン ツールを提供します。

[C/C++ ビルド エラー](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)内容の表にビルド エラー セクションが導入されています。

## <a name="related-sections"></a>関連項目

[C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)マクロ、演算子、およびディレクティブを変換することによって、コンパイラのソース ファイルを準備すると、プリプロセッサについて説明します。

[カスタム ビルド ステップとビルド イベント](../../ide/understanding-custom-build-steps-and-build-events.md)ビルド プロセスのカスタマイズについて説明します。

[C/C++ プログラムのビルド](../../build/building-c-cpp-programs.md)コマンドラインからまたは Visual Studio の統合開発環境からプログラムをビルドについて説明するトピックへのリンクを提供します。

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)開発環境またはコマンドラインでコンパイラ オプションの設定について説明します。

[コンパイラ オプション](../../build/reference/compiler-options.md)コンパイラ オプションの使用について説明するトピックへのリンクを提供します。

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)統合開発環境内外のリンカー オプションの設定について説明します。

[リンカー オプション](../../build/reference/linker-options.md)リンカー オプションの使用について説明するトピックへのリンクを提供します。

[BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)Microsoft Browse 情報 Maintenance Utility (BSCMAKE について説明します。EXE)、.sbr からブラウザー情報ファイル (.bsc) をビルドするファイルのコンパイル時に作成します。

[LIB リファレンス](../../build/reference/lib-reference.md)を作成し、一般的なオブジェクト ファイル形式 (COFF) オブジェクト ファイルのライブラリを管理する Microsoft ライブラリ マネージャー (LIB.exe) について説明します。

[EDITBIN リファレンス](../../build/reference/editbin-reference.md)Microsoft COFF バイナリ ファイル エディター (EDITBIN について説明します。EXE) では、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルが変更されます。

[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)Microsoft COFF Binary File Dumper (DUMPBIN について説明します。EXE) では、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルに関する情報が表示されます。

[NMAKE リファレンス](../../build/nmake-reference.md)Microsoft Program Maintenance Utility (NMAKE について説明します。EXE)、プロジェクトをビルドするツールは記述ファイルに含まれるコマンドに基づいて。