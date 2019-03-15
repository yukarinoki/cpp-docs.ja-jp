---
title: C/C++ ビルドのリファレンス - Visual Studio
description: Visual Studio で C/C++ プロジェクト システムとビルド ツールの参照コンテンツです。
ms.date: 12/10/2018
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
ms.openlocfilehash: 4c3f7aa598a9c43af04c148ed0d4b3f555566ec7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812487"
---
# <a name="cc-building-reference"></a>C/C++ ビルドのリファレンス

Visual C には、C/C++ プログラムのビルドの 2 つの方法が用意されています。 最も簡単な (および最も一般的な) 方法は、する[Visual Studio IDE 内でビルド](../creating-and-managing-visual-cpp-projects.md)します。 その他の方法は、する[コマンド ライン ツールを使用してコマンド プロンプトからビルド](../building-on-the-command-line.md)します。 どちらの場合は、作成し、Visual Studio または任意のサード パーティ製エディターを使用してソース ファイルを編集します。

## <a name="in-this-section"></a>このセクションの内容

[C++ プロジェクトの MSBuild のリファレンス](msbuild-visual-cpp-overview.md)

[MSVC コンパイラ リファレンス](compiling-a-c-cpp-program.md)<br/>
マシン語コード、リンカー ディレクティブ、セクションでは、外部参照、および関数/データの名前を格納しているオブジェクト ファイルを作成、MSVC コンパイラをについて説明します。

[MSVC リンカーの参照](linking.md)<br/>
リンカーは、コンパイラによって作成されたオブジェクト ファイルと静的にリンクされたライブラリからコードを組み合わせると、について説明しますと、名前の参照を解決し、実行可能ファイルを作成します。

[コンパイラおよびリンカーでの Unicode のサポート](unicode-support-in-the-compiler-and-linker.md)

[追加の MSVC ビルド ツール](c-cpp-build-tools.md)<br/>
C++ 用のコマンド ライン ツールを追加します。

[C/C++ ビルド エラー](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
テーブルの内容のビルド エラー セクションをについて説明します。

## <a name="related-sections"></a>関連項目

[C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
マクロ、演算子、およびディレクティブを変換することによって、コンパイラのソース ファイルを準備すると、プリプロセッサについて説明します。

[カスタム ビルド ステップとビルド イベントについて](../understanding-custom-build-steps-and-build-events.md)<br/>
ビルド プロセスのカスタマイズについて説明します。

[C/C++ プログラムのビルド](../projects-and-build-systems-cpp.md)<br/>
コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。

[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)<br/>
開発環境またはコマンドラインでコンパイラ オプションの設定について説明します。

[MSVC コンパイラ オプション](compiler-options.md)<br/>
コンパイラ オプションの使用について説明するトピックへのリンクを提供します。

[MSVC リンカーの参照](linking.md)<br/>
統合開発環境内外のリンカー オプションの設定について説明します。

[MSVC リンカー オプション](linker-options.md)<br/>
リンカー オプションの使用について説明するトピックへのリンクを提供します。

[BSCMAKE リファレンス](bscmake-reference.md)<br/>
Microsoft Browse 情報 Maintenance Utility (BSCMAKE をについて説明します。EXE)、.sbr からブラウザー情報ファイル (.bsc) をビルドするファイルのコンパイル時に作成します。

[LIB リファレンス](lib-reference.md)<br/>
Microsoft ライブラリ マネージャー (LIB.exe) を作成し、一般的なオブジェクト ファイル形式 (COFF) オブジェクト ファイルのライブラリを管理するについて説明します。

[EDITBIN リファレンス](editbin-reference.md)<br/>
Microsoft COFF バイナリ ファイル エディター (EDITBIN について説明します。EXE) では、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルが変更されます。

[DUMPBIN リファレンス](dumpbin-reference.md)<br/>
Microsoft COFF Binary File Dumper (DUMPBIN をについて説明します。EXE) では、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルに関する情報が表示されます。

[NMAKE リファレンス](nmake-reference.md)<br/>
Microsoft Program Maintenance Utility (NMAKE をについて説明します。EXE)、プロジェクトをビルドするツールは記述ファイルに含まれるコマンドに基づいて。
