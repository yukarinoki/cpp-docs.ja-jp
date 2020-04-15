---
title: Visual C++ における MBCS のサポート
ms.date: 11/04/2016
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
ms.openlocfilehash: 404fcee5e48d8db28e56a005f24f8cac5892240e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375794"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++ における MBCS のサポート

MBCS 対応の Windows で実行する場合、Visual C++ 開発システム (統合ソース コード エディター、デバッガー、およびコマンド ライン ツールを含む) は MBCS 対応です。

メモリ ウィンドウでは、データのバイト数を MBCS 文字として解釈しませんが、ANSI 文字または Unicode 文字として解釈できます。 ANSI 文字は常に 1 バイトのサイズで、Unicode 文字のサイズは 2 バイトです。 MBCS では、文字のサイズは 1 バイトまたは 2 バイトで、その解釈は使用されているコード ページによって異なります。 このため、メモリ ウィンドウで MBCS 文字を確実に表示することは困難です。 メモリ ウィンドウは、文字の先頭のバイトを認識できません。 開発者は、メモリ ウィンドウでバイト値を表示し、テーブル内の値を検索して文字表現を決定できます。 これは、ソース コードに基づいて文字列の開始アドレスを開発者が認識しているために可能です。

Visual C++ では、適切な場所であれば、2 バイト文字を使用できます。 これには、ダイアログ ボックスのパス名とファイル名、Visual C++ リソース エディタのテキスト エントリ (ダイアログ エディターの静的テキスト、アイコン エディタの静的テキスト エントリなど) が含まれます。 さらに、プリプロセッサは、いくつかの 2 バイト ディレクティブを認識します ( たとえば、`#include`ステートメントのファイル名や、`code_seg`および`data_seg`プラグマの引数として) 。 ソース コード エディターでは、C/C++ 言語要素 (変数名など) には含まれませんが、コメントとリテラル文字列の 2 バイト文字は受け入れられます。

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>入力方式エディター (IME) のサポート

MBCS (日本など) を使用する東アジア市場向けに作成されたアプリケーションは、通常、Windows IME をサポートして、1 バイト文字と 2 バイト文字の両方を入力します。 Visual C++ 開発環境には、IME の完全なサポートが含まれています。

日本語キーボードは漢字を直接サポートしていません。 IME は、他の日本語のアルファベット (ローマ字、カタカナ、ひらがな) のいずれかで入力されたふりがな文字列を、可能な漢字表現に変換します。 あいまいさがある場合は、いくつかの選択肢から選択できます。 目的の漢字文字を選択すると、IME は 2`WM_CHAR`つのメッセージを制御アプリケーションに渡します。

Alt +\`キーの組み合わせによってアクティブ化された IME は、ボタンのセット (インジケータ) と変換ウィンドウとして表示されます。 アプリケーションは、テキスト挿入ポイントにウィンドウを配置します。 アプリケーションは、`WM_SIZE`変換`WM_MOVE`ウィンドウの位置を変更して、ターゲット ウィンドウの新しい位置またはサイズに合わせてメッセージを処理する必要があります。

アプリケーションのユーザーに漢字文字を入力できるようにする場合は、アプリケーションで Windows IME メッセージを処理する必要があります。 IME プログラミングの詳細については、「[入力方式マネージャ](/windows/win32/intl/input-method-manager)」を参照してください。

## <a name="visual-c-debugger"></a>ビジュアル C++ デバッガー

Visual C++ デバッガーは、IME メッセージにブレークポイントを設定する機能を提供します。 さらに、メモリ ウィンドウには 2 バイト文字を表示できます。

## <a name="command-line-tools"></a>コマンド ライン ツール

コンパイラ、NMAKE、およびリソース コンパイラ (RC.EXE)は MBCS 対応です。 リソース コンパイラの /c オプションを使用すると、アプリケーションのリソースをコンパイルするときに既定のコード ページを変更できます。

ソース コードのコンパイル時に既定のロケールを変更するには、 [setlocale #pragma](../preprocessor/setlocale.md)使用します。

## <a name="graphical-tools"></a>グラフィカルツール

Spy++ やリソース編集ツールなどの Visual C++ Windows ベースのツールは、IME 文字列を完全にサポートします。

## <a name="see-also"></a>関連項目

[マルチバイト文字セット (MBCS) のサポート](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS のプログラミングについて](../text/mbcs-programming-tips.md)
