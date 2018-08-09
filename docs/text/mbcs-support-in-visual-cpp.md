---
title: Visual C における MBCS のサポート |Microsoft Docs
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
ms.openlocfilehash: 1d00495f95b3c67e4a6fc3613b949b8ae2946bd6
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010387"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++ における MBCS のサポート
を、mbcs バージョンの Windows で実行時に (統合されたソース コード エディター、デバッガー、およびコマンド ライン ツールを含む)、Visual C 開発システムが mbcs、[メモリ] ウィンドウを除く。  
  
 [メモリ] ウィンドウに ANSI または Unicode 文字として解釈できる場合でも、データのバイトを MBCS 文字として解釈しません。 ANSI 文字が 1 バイトのサイズでは常に、Unicode 文字は、サイズが 2 バイト。 MBCS の文字はサイズが 1 つまたは 2 バイトを使用でき、その解釈が使用されているコード ページに依存します。 このためには、メモリ ウィンドウが確実に MBCS 文字を表示するが困難です。 [メモリ] ウィンドウでは、どのバイトが文字の開始を知ることはできません。 開発者は、[メモリ] ウィンドウで、バイト値を表示し、文字表現を判断するテーブルで値を検索できます。 開発者は、ソース コードに基づく文字列の開始アドレスを知っているため可能です。  
  
 そのためには適切な場所を問わず、visual C は 2 バイト文字を受け入れます。 ダイアログ ボックスおよび Visual C リソース エディター (ダイアログ エディターでの静的テキストなど) とアイコン エディター内の静的テキスト エントリで、テキスト エントリにパス名とファイル名が含まれます。 プリプロセッサはさらに、いくつかの 2 バイトのディレクティブを認識する — たとえば、ファイル名`#include`ステートメント、およびへの引数として、`code_seg`と`data_seg`プラグマ。 ソース コード エディターで C/C++ 言語要素 (変数名) などに、コメントと文字列リテラルで 2 バイト文字は受け入れられます。  
  
##  <a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> サポートの入力方式エディター (IME)  
 MBCS (たとえば、日本語) を使用して、通常東アジアの市場向け両方の 1 つと 2 バイト文字を入力するための Windows IME のサポート用に記述されたアプリケーション。 Visual C の開発環境には、IME の完全なサポートが含まれています。 詳細については、次を参照してください。 [IME のサンプル: コントロールの IME モードと IME レベル 3 の実装方法を示します](http://msdn.microsoft.com/87ebdf65-cef0-451d-a6fc-d5fb64178b14)します。  
  
 日本語キーボードでは、漢字は直接サポートしていません。 IME では、その漢字表記に、日本語のアルファベット (ローマ字やカタカナをひらがな) のいずれかで入力、音声の文字列に変換します。 あいまいさがある場合は、いくつかの選択肢から選択できます。 目的の漢字を選択すると、2 つを渡します IME`WM_CHAR`メッセージを制御するアプリケーション。  
  
 ALT + によってアクティブ化、IME\`キーの組み合わせ、一連のボタン (評価指標) と変換ウィンドウとして表示されます。 アプリケーションでは、テキストのカーソル位置にウィンドウを配置します。 アプリケーションを処理する必要があります`WM_MOVE`と`WM_SIZE`変換ウィンドウの位置を変更してメッセージを新しい場所またはターゲット ウィンドウのサイズに準拠するようにします。  
  
 漢字の文字を入力する機能があれば、アプリケーションのユーザーを設定する場合、アプリケーションは、IME の Windows メッセージを処理する必要があります。 IME のプログラミングの詳細については、次を参照してください。[入力方式エディター](https://msdn.microsoft.com/library/ms776145.aspx)します。  
  
## <a name="visual-c-debugger"></a>Visual C デバッガー  
 Visual C デバッガーには、IME のメッセージにブレークポイントを設定する機能が用意されています。 さらに、[メモリ] ウィンドウでは、2 バイト文字を表示できます。  
  
## <a name="command-line-tools"></a>コマンド ライン ツール  
 コンパイラ、NMAKE、リソース コンパイラ (RC など、Visual C コマンド ライン ツール。EXE)、MBCS が有効にします。 アプリケーションのリソースをコンパイルするときに、既定のコード ページを変更するのには、リソース コンパイラの/c オプションを使用することができます。  
  
 ソース コードのコンパイル時に既定のロケールを変更する[#pragma setlocale](../preprocessor/setlocale.md)します。  
  
## <a name="graphical-tools"></a>グラフィカルなツール  
 ビジュアルの C++ の Windows ベースのツール、spy++ と編集ツール、リソースなどは、IME の文字列を完全にサポートします。  
  
## <a name="see-also"></a>関連項目  
 [マルチバイト文字セット (Mbcs) のサポート](../text/support-for-multibyte-character-sets-mbcss.md)   
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)