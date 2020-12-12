---
description: 詳細については、「Visual C++ での MBCS のサポート」を参照してください。
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
ms.openlocfilehash: f216e381db8111c54f30b2c2fe326f4914024956
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207138"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++ における MBCS のサポート

MBCS が有効になっているバージョンの Windows で実行する場合、Visual C++ 開発システム (統合ソースコードエディター、デバッガー、およびコマンドラインツールを含む) は、[メモリ] ウィンドウを除き、MBCS が有効になります。

[メモリ] ウィンドウでは、データを ANSI または Unicode 文字として解釈できる場合でも、データのバイトは MBCS 文字として解釈されません。 ANSI 文字のサイズは常に1バイトで、Unicode 文字のサイズは2バイトです。 MBCS では、文字数は1または2バイトで、その解釈は使用中のコードページによって異なります。 このため、[メモリ] ウィンドウで MBCS 文字を確実に表示することは困難です。 [メモリ] ウィンドウは、どのバイトが文字の先頭であるかを認識できません。 開発者は、[メモリ] ウィンドウでバイト値を表示し、テーブルの値を参照して文字表現を決定できます。 これが可能なのは、開発者がソースコードに基づいて文字列の開始アドレスを知っているためです。

Visual C++ は、適切であればどこでも2バイト文字を受け入れます。 これには、Visual C++ リソースエディターのダイアログボックスやテキストエントリ内のパス名とファイル名 (たとえば、ダイアログエディターの静的テキストとアイコンエディターの静的テキストエントリ) が含まれます。 また、プリプロセッサは、ステートメント内のファイル名 `#include` やプラグマの引数として、いくつかの2バイトディレクティブを認識し `code_seg` `data_seg` ます。 ソースコードエディターでは、C/c + + 言語要素 (変数名など) ではなく、コメントおよび文字列リテラル内の2バイト文字が許容されます。

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a> 入力方式エディター (IME) のサポート

MBCS (たとえば日本) を使用する東アジア市場向けに作成されたアプリケーションでは、通常、1バイト文字と2バイト文字の両方を入力するための Windows IME がサポートされています。 Visual C++ 開発環境には、IME の完全なサポートが含まれています。

日本語のキーボードは、漢字を直接サポートしていません。 IME は、他の日本語のアルファベット (Romaji、カタカナ、ひらがな) のいずれかに入力された発音文字列を、可能な漢字表現に変換します。 あいまいさがある場合は、いくつかの代替手段から選択できます。 目的の漢字文字を選択すると、IME は `WM_CHAR` 制御アプリケーションに2つのメッセージを渡します。

ALT + キーの組み合わせによってアクティブ化される IME は、 \` 一連のボタン (インジケーター) と変換ウィンドウとして表示されます。 アプリケーションは、テキストの挿入ポイントにウィンドウを配置します。 アプリケーションでは `WM_MOVE` 、 `WM_SIZE` ターゲットウィンドウの新しい位置またはサイズに合わせて変換ウィンドウを再配置することによって、メッセージとメッセージを処理する必要があります。

アプリケーションのユーザーが漢字の文字を入力できるようにするには、アプリケーションで Windows IME メッセージを処理する必要があります。 IME プログラミングの詳細については、「 [Input Method Manager](/windows/win32/intl/input-method-manager)」を参照してください。

## <a name="visual-c-debugger"></a>Visual C++ デバッガー

Visual C++ デバッガーは、IME メッセージにブレークポイントを設定する機能を提供します。 さらに、[メモリ] ウィンドウには2バイト文字が表示されます。

## <a name="command-line-tools"></a>コマンド ライン ツール

コンパイラ、NMAKE、リソースコンパイラ (RC.EXE) などの Visual C++ コマンドラインツールは、MBCS が有効になっています。 リソースコンパイラの/c オプションを使用して、アプリケーションのリソースをコンパイルするときに既定のコードページを変更できます。

ソースコードのコンパイル時に既定のロケールを変更するには、 [#pragma setlocale](../preprocessor/setlocale.md)を使用します。

## <a name="graphical-tools"></a>グラフィックツール

Spy + + やリソース編集ツールなどの Windows ベースのツール Visual C++ は、IME 文字列を完全にサポートしています。

## <a name="see-also"></a>関連項目

[マルチバイト文字セットのサポート (MBCSs)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS のプログラミングに関するヒント](../text/mbcs-programming-tips.md)
