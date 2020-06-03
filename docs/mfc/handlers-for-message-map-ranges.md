---
title: 範囲内のメッセージのハンドラー
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
ms.openlocfilehash: fc33df6957beab6e4e8de3093dfc00cf2651780e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370509"
---
# <a name="handlers-for-message-map-ranges"></a>範囲内のメッセージのハンドラー

この記事では、1 つのメッセージを 1 つの関数だけにマップするのではなく、メッセージの範囲を単一のメッセージ ハンドラー関数にマップする方法について説明します。

複数のメッセージまたはコントロールの通知をまったく同じ方法で処理する必要がある場合があります。 このような場合は、すべてのメッセージを単一のハンドラー関数にマップする必要があります。 メッセージ マップ範囲を使用すると、連続するメッセージ範囲に対してこれを行うことができます。

- コマンド ID の範囲をマップして、次のことができます。

  - コマンド ハンドラー関数。

  - コマンド更新ハンドラー関数。

- 一連のコントロール ID に対するコントロール通知メッセージをメッセージ ハンドラー関数にマップできます。

この記事で扱うトピックは次のとおりです。

- [メッセージ・マップ項目の書き込み](#_core_writing_the_message.2d.map_entry)

- [ハンドラー関数の宣言](#_core_declaring_the_handler_function)

- [コマンド ID の範囲の例](#_core_example_for_a_range_of_command_ids)

- [コントロール ID の範囲の例](#_core_example_for_a_range_of_control_ids)

## <a name="writing-the-message-map-entry"></a><a name="_core_writing_the_message.2d.map_entry"></a>メッセージ マップ エントリの書き込み

の。CPP ファイルを追加するには、次の例に示すように、メッセージ マップ エントリを追加します。

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

メッセージ マップ エントリは、次の項目で構成されます。

- メッセージ マップ範囲マクロ:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- マクロへのパラメータ:

  最初の 2 つのマクロは、3 つのパラメーターを受け取ります。

  - 範囲を開始するコマンド ID

  - 範囲を終了するコマンド ID

  - メッセージ ハンドラ関数の名前

  コマンド ID の範囲は連続している必要があります。

  3 番目の`ON_CONTROL_RANGE`マクロは、最初のパラメータとして、コントロール通知メッセージ **(EN_CHANGE**など) を追加します。

## <a name="declaring-the-handler-function"></a><a name="_core_declaring_the_handler_function"></a>ハンドラ関数の宣言

ハンドラー関数宣言を に追加します。H ファイル。 次のコードは、次に示すように、この動作を示しています。

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

単一コマンドのハンドラー関数は、通常、パラメーターを受け取らない。 更新ハンドラ関数を除き、メッセージ マップ範囲のハンドラ関数には **、UINT**型の追加パラメータ*nID*が必要です。 このパラメーターは、最初のパラメーターです。 追加のパラメーターは、ユーザーが実際に選択したコマンドを指定するために必要な追加コマンド ID を収容します。

ハンドラ関数を更新するためのパラメータ要件の詳細については、「コマンド[ID の範囲の例](#_core_example_for_a_range_of_command_ids)」を参照してください。

## <a name="example-for-a-range-of-command-ids"></a><a name="_core_example_for_a_range_of_command_ids"></a>コマンド ID の範囲の例

範囲を使用する場合 MFC サンプル[HIERSVR](../overview/visual-cpp-samples.md)の [ズーム] コマンドのようなコマンドの処理の例を示します。 このコマンドはビューを拡大し、通常のサイズの 25% から 300% の範囲で拡大縮小します。 HIERSVR のビュー クラスは、次に示すメッセージ マップ エントリを使用して、Zoom コマンドを処理するために範囲を使用します。

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

メッセージ マップ エントリを記述する場合は、次の項目を指定します。

- 連続する範囲の開始と終了の 2 つのコマンド ID。

   ここでは、彼らは**ID_VIEW_ZOOM25**と**ID_VIEW_ZOOM300**です.

- コマンドのハンドラー関数の名前。

   ここは`OnZoom`.

関数の宣言は次のようになります。

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

更新ハンドラ関数の場合は似ており、より広く役に立つ可能性があります。 多くのコマンドのハンドラを記述`ON_UPDATE_COMMAND_UI`して、同じコードを何度も書いたりコピーしたりすることは非常に一般的です。 解決策は、マクロを使用してコマンド ID の範囲を 1 つの更新`ON_UPDATE_COMMAND_UI_RANGE`ハンドラー関数にマップすることです。 コマンド ID は連続する範囲を形成する必要があります。 例については、HIERSVR`OnUpdateZoom`サンプルの`ON_UPDATE_COMMAND_UI_RANGE`ビュー クラスでのハンドラーとそのメッセージ マップ エントリを参照してください。

単一のコマンドの更新ハンドラー関数は、通常、型の 1 つのパラメーター `CCmdUI*` *pCmdUI*を受け取ります。 ハンドラ関数とは異なり、メッセージ マップ範囲の更新ハンドラ関数には **、UINT**型の追加パラメータ*nID*は必要ありません。 ユーザーが実際に選択したコマンドを指定するために必要なコマンド ID がオブジェクト内にあります`CCmdUI`。

## <a name="example-for-a-range-of-control-ids"></a><a name="_core_example_for_a_range_of_control_ids"></a>コントロール ID の範囲の例

もう 1 つの興味深いケースは、コントロール ID の範囲のコントロール通知メッセージを単一のハンドラーにマップすることです。 ユーザーが 10 個のボタンのいずれかをクリックできるとします。 10 個のボタンすべてを 1 つのハンドラーにマップするには、メッセージ マップエントリは次のようになります。

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

メッセージ マップに`ON_CONTROL_RANGE`マクロを記述する場合は、次の項目を指定します。

- 特定のコントロール通知メッセージ。

   ここは**BN_CLICKED**です。

- 連続するコントロールの範囲に関連付けられているコントロール ID 値。

   ここでは、これらは**IDC_BUTTON1**と**IDC_BUTTON10**です.

- メッセージ ハンドラー関数の名前。

   ここは`OnButtonClicked`.

ハンドラー関数を記述する場合は、次に示すように、追加**の UINT**パラメーターを指定します。

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

単`OnButtonClicked`一の**BN_CLICKED**メッセージのハンドラーはパラメーターを受け取らない。 ボタンの範囲に対して同じハンドラが 1 つの**UINT**を受け取ります。 追加パラメータを使用すると **、BN_CLICKED**メッセージの生成を担当する特定のコントロールを識別できます。

例に示すコードは、典型的な例です: メッセージ範囲`int`内のに渡された値を変換し、これが当てはまることをアサートします。 その後、クリックされたボタンに応じて、いくつかの異なるアクションを実行する場合があります。

## <a name="see-also"></a>関連項目

[メッセージ ハンドラ関数の宣言](../mfc/declaring-message-handler-functions.md)
