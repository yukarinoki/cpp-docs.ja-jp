---
title: C/C++ ビルドのリファレンス |Microsoft ドキュメント
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
ms.openlocfilehash: 2d26f729f660b3e51677303bb91b99e665a1a950
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375485"
---
# <a name="cc-building-reference"></a>C/C++ ビルドのリファレンス
Visual C には、C と C++ プログラムのビルドの 2 つの方法が用意されています。 最も簡単な (および最も一般的な) 方法を[Visual C 開発環境でビルド](../../ide/building-cpp-projects-in-visual-studio.md)です。 その他の方法を[コマンド ライン ツールを使用してコマンド プロンプトからビルド](../../build/building-on-the-command-line.md)です。 どちらの場合は、Visual C ソース エディターまたは任意のサード パーティ製のエディターを使用して、ソース ファイルを作成できます。  
  
 プログラムでは、.vcxproj ファイルではなく、メイクファイルを使用する場合でもビルドできることとして、開発環境で、[外部プロジェクト](../../ide/building-external-projects.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [C/C++ プログラムのコンパイル](../../build/reference/compiling-a-c-cpp-program.md)  
 マシン語コード、リンカー ディレクティブのセクションでは、外部参照、および関数/データの名前を含むオブジェクト ファイルを作成すると、コンパイラについて説明します。  
  
 [リンク](../../build/reference/linking.md)  
 リンカーは、静的にリンクされるライブラリと、コンパイラによって作成されたオブジェクト ファイルからコードを組み合わせると、について説明します、名前の参照を解決し、実行可能ファイルを作成します。  
  
 [リリース ビルド](../../build/reference/release-builds.md)  
 デバッグからに変更する理由とタイミングの情報が表示では、リリース ビルドをビルドし、いくつかのデバッグ、リリース ビルドを変更するときに発生する問題についても説明します。  
  
 [コードの最適化](../../build/reference/optimizing-your-code.md)  
 コードを最適化するためのメカニズムについて説明するトピックへのリンクを提供します。  
  
 [C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)  
 表示またはビルド出力を操作するためには、次のコマンド ライン ツールを提供します。  
  
 [C/C++ ビルド エラー](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 コンテンツのテーブルにビルド エラー セクションをについて説明します。  
  
## <a name="related-sections"></a>関連項目  
 [C/C++ プリプロセッサ リファレンス](../../preprocessor/c-cpp-preprocessor-reference.md)  
 マクロ、演算子、およびディレクティブを変換することによって、コンパイラのソース ファイルを準備すると、プリプロセッサについて説明します。  
  
 [カスタム ビルド ステップとビルド イベントについて](../../ide/understanding-custom-build-steps-and-build-events.md)  
 ビルド プロセスのカスタマイズについて説明します。  
  
 [C/C++ プログラムのビルド](../../build/building-c-cpp-programs.md)  
 コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。  
  
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
 開発環境で、またはコマンドラインでコンパイラ オプションの設定について説明します。  
  
 [コンパイラ オプション](../../build/reference/compiler-options.md)  
 コンパイラ オプションの使用について説明するトピックへのリンクを提供します。  
  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)  
 統合開発環境内外のリンカー オプションの設定について説明します。  
  
 [リンカー オプション](../../build/reference/linker-options.md)  
 リンカー オプションの使用について説明するトピックへのリンクを提供します。  
  
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)  
 Microsoft Browse 情報 Maintenance Utility (BSCMAKE をについて説明します。EXE)、どのビルド ブラウザー情報ファイル (.bsc) .sbr からファイルのコンパイル時に作成します。  
  
 [LIB リファレンス](../../build/reference/lib-reference.md)  
 作成して、オブジェクト ファイル形式 COFF (Common) オブジェクト ファイルのライブラリを管理する Microsoft ライブラリ マネージャー (LIB.exe) について説明します。  
  
 [EDITBIN リファレンス](../../build/reference/editbin-reference.md)  
 Microsoft COFF Binary ファイル エディター (EDITBIN 説明します。オブジェクト ファイル形式 COFF (Common) のバイナリ ファイルを変更する EXE)、します。  
  
 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)  
 Microsoft COFF Binary File Dumper (DUMPBIN をについて説明します。EXE)、オブジェクト ファイル形式 COFF (Common) のバイナリ ファイルに関する情報を表示します。  
  
 [NMAKE リファレンス](../../build/nmake-reference.md)  
 Microsoft Program Maintenance Utility (NMAKE をについて説明します。プロジェクトをビルドするツールは EXE)、記述ファイルに含まれるコマンドに基づきます。