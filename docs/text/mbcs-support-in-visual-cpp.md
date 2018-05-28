---
title: Visual C における MBCS のサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41d075edb01fc139660d8e72a7fe53f03ee9e80b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++ における MBCS のサポート
実行すると、mbcs バージョンの Windows で、Visual C 開発システムの (統合ソース コード エディター、デバッガー、およびコマンド ライン ツールを含む) が mbcs、[メモリ] ウィンドウを除く。  
  
 [メモリ] ウィンドウに ANSI または Unicode 文字として解釈できる場合でも、データのバイト数を MBCS 文字として解釈されません。 ANSI 文字は 1 バイトのサイズと、Unicode 文字は、サイズが 2 バイト。 Mbcs の場合、1 つまたは 2 バイトの列に使用できる文字とその解釈が使用されているコード ページに依存します。 このため、[メモリ] ウィンドウを確実に MBCS 文字を表示するは困難です。 [メモリ] ウィンドウでは、どのバイトが文字の開始を知ることはできません。 開発者では、[メモリ] ウィンドウで、バイト値を表示でき、文字表現を判断するテーブルで値を検索することができます。 これには、開発者は、ソース コードに基づく文字列の開始アドレスを認識しているためです。  
  
 Visual C は、これを行うには適切である限り、2 バイト文字を受け入れます。 ダイアログ ボックスと、Visual C リソース エディター (たとえば、ダイアログ エディターで静的なテキスト) とアイコン エディターでの静的なテキスト エントリ内のエントリのテキストのパス名とファイル名が含まれます。 プリプロセッサはさらに、一部の 2 バイト ディレクティブを認識する — たとえば、ファイル名`#include`ステートメント、およびへの引数として、 **code_seg**と**data_seg**プラグマ。 ソース コード エディターでコメントや文字列リテラル内の 2 バイト文字が受け入れられたら、C と C++ 言語要素 (変数名など) にします。  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> サポート用の入力方式エディター (IME)  
 MBCS (たとえば、日本語) を使用して通常東アジアの市場向け両方の 1 つと 2 バイト文字を入力するための Windows IME のサポート用に記述されたアプリケーション。 Visual C 開発環境には、IME の完全なサポートが含まれています。 詳細については、次を参照してください。 [IME サンプル: コントロールの IME モードと IME レベル 3 の実装方法を示します](http://msdn.microsoft.com/en-us/87ebdf65-cef0-451d-a6fc-d5fb64178b14)です。  
  
 日本語キーボードの漢字が直接サポートしていません。 IME では、その漢字表記、日本語のアルファベット (ローマ字やカタカナをひらがな) のいずれかで入力した、ルビの文字列に変換します。 あいまいさがある場合は、いくつかの選択肢からを選択することができます。 目的の漢字を選択すると、2 つを渡します IME`WM_CHAR`メッセージを制御するアプリケーション。  
  
 ALT + によってアクティブ化、IME\`キーの組み合わせ、一連のボタン (インジケーター) および変換ウィンドウとして表示されます。 アプリケーションでは、テキスト挿入ポイントでウィンドウを配置します。 アプリケーションで処理する必要があります`WM_MOVE`と`WM_SIZE`conversion ウィンドウの位置を変更して、新しい場所またはターゲット ウィンドウのサイズに準拠するメッセージ。  
  
 漢字の文字を入力できるように、アプリケーションのユーザーにする場合は、アプリケーションは Windows IME メッセージを処理する必要があります。 IME プログラミングの詳細については、次を参照してください。[入力方式エディター](https://msdn.microsoft.com/en-us/library/ms776145.aspx)です。  
  
## <a name="visual-c-debugger"></a>Visual C デバッガー  
 Visual C デバッガーには、IME メッセージにブレークポイントを設定する機能が用意されています。 さらに、[メモリ] ウィンドウでは、2 バイト文字を表示できます。  
  
## <a name="command-line-tools"></a>コマンド ライン ツール  
 コンパイラ、(nmake の)、リソース コンパイラ (RC など、Visual C のコマンド ライン ツール。EXE)、MBCS が有効にします。 リソース コンパイラの/c オプションを使用すると、アプリケーションのリソースをコンパイルするときに、既定のコード ページを変更します。  
  
 ソース コードのコンパイル時に既定のロケールを変更するには、使用[#pragma setlocale、_wsetlocale](../preprocessor/setlocale.md)です。  
  
## <a name="graphical-tools"></a>グラフィカルなツール  
 Visual C の Windows ベースのツール、spy++ と編集ツール、リソースなどは、IME の文字列を完全にサポートします。  
  
## <a name="see-also"></a>関連項目  
 [マルチバイト文字セット (Mbcs) のサポート](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)