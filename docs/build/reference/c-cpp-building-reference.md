---
title: C/C++ ビルドのリファレンス
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], additional information
- cl.exe compiler [C++], building programs
- linker [C++], building reference
- builds [C++], additional information
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
ms.openlocfilehash: 36f261ee993932d1a08d5cdb02e2d4681ae60f0c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481732"
---
# <a name="cc-building-reference"></a>C/C++ ビルドのリファレンス

Visual C には、C/C++ プログラムのビルドの 2 つの方法が用意されています。 最も簡単な (および最も一般的な) 方法は、する[Visual C 開発環境でビルド](../../ide/building-cpp-projects-in-visual-studio.md)します。 その他の方法は、する[コマンド ライン ツールを使用してコマンド プロンプトからビルド](../../build/building-on-the-command-line.md)します。 どちらの場合は、Visual C のソース エディターまたは任意のサード パーティ製エディターを使用して、ソース ファイルを作成できます。

プログラムでは、.vcxproj ファイルではなく、メイクファイルを使用する場合でもビルドできることとして、開発環境で、[外部プロジェクト](../../ide/building-external-projects.md)します。

## <a name="in-this-section"></a>このセクションの内容

[C/C++ プログラムのコンパイル](../../build/reference/compiling-a-c-cpp-program.md)<br/>
マシン語コード、リンカー ディレクティブ、セクションでは、外部参照、および関数/データの名前を格納しているオブジェクト ファイルを作成すると、コンパイラがについて説明します。

[リンク](../../build/reference/linking.md)<br/>
リンカーは、コンパイラによって作成されたオブジェクト ファイルと静的にリンクされたライブラリからコードを組み合わせると、について説明しますと、名前の参照を解決し、実行可能ファイルを作成します。

[リリース ビルド](../../build/reference/release-builds.md)<br/>
デバッグを変更する理由とタイミングの情報が表示されますはリリース ビルドをビルドし、デバッグからリリース ビルドに変更するときに発生する問題のいくつかについても説明します。

[コードの最適化](../../build/reference/optimizing-your-code.md)<br/>
コードを最適化するためのメカニズムを説明するトピックへのリンクを示します。

[C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)<br/>
表示またはビルド出力を操作するためには、次のコマンド ライン ツールを提供します。

[C/C++ ビルド エラー](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)<br/>
テーブルの内容のビルド エラー セクションをについて説明します。

## <a name="related-sections"></a>関連項目

[C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)<br/>
マクロ、演算子、およびディレクティブを変換することによって、コンパイラのソース ファイルを準備すると、プリプロセッサについて説明します。

[カスタム ビルド ステップとビルド イベントについて](../../ide/understanding-custom-build-steps-and-build-events.md)<br/>
ビルド プロセスのカスタマイズについて説明します。

[C/C++ プログラムのビルド](../../build/building-c-cpp-programs.md)<br/>
コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
開発環境またはコマンドラインでコンパイラ オプションの設定について説明します。

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
コンパイラ オプションの使用について説明するトピックへのリンクを提供します。

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
統合開発環境内外のリンカー オプションの設定について説明します。

[リンカー オプション](../../build/reference/linker-options.md)<br/>
リンカー オプションの使用について説明するトピックへのリンクを提供します。

[BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)<br/>
Microsoft Browse 情報 Maintenance Utility (BSCMAKE をについて説明します。EXE)、.sbr からブラウザー情報ファイル (.bsc) をビルドするファイルのコンパイル時に作成します。

[LIB リファレンス](../../build/reference/lib-reference.md)<br/>
Microsoft ライブラリ マネージャー (LIB.exe) を作成し、一般的なオブジェクト ファイル形式 (COFF) オブジェクト ファイルのライブラリを管理するについて説明します。

[EDITBIN リファレンス](../../build/reference/editbin-reference.md)<br/>
Microsoft COFF バイナリ ファイル エディター (EDITBIN について説明します。EXE) では、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルが変更されます。

[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)<br/>
Microsoft COFF Binary File Dumper (DUMPBIN をについて説明します。EXE) では、一般的なオブジェクト ファイル形式 (COFF) のバイナリ ファイルに関する情報が表示されます。

[NMAKE リファレンス](../../build/nmake-reference.md)<br/>
Microsoft Program Maintenance Utility (NMAKE をについて説明します。EXE)、プロジェクトをビルドするツールは記述ファイルに含まれるコマンドに基づいて。