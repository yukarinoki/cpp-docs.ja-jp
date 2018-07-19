---
title: メッセージ マップの範囲内のハンドラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 896977da8ca57cc17a9fa3b7864e1744ee07f35d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930824"
---
# <a name="handlers-for-message-map-ranges"></a>範囲内のメッセージのハンドラー
この記事では、メッセージの範囲を (1 つのメッセージを 1 つだけの関数にマッピング) ではなく 1 つのメッセージ ハンドラー関数にマップする方法について説明します。  
  
 まったく同じ方法で 1 つ以上のメッセージまたはコントロールの通知を処理する必要がある場合もあります。 このような時間は、すべてのメッセージを 1 つのハンドラー関数にマップしておくこともできます。 メッセージ マップの範囲を使用すると、これを行うメッセージの連続した範囲にします。  
  
-   コマンド Id の範囲を割り当てることができます。  
  
    -   コマンド ハンドラー関数。  
  
    -   コマンド更新ハンドラー関数。  
  
-   コントロール Id の範囲に対するコントロール通知メッセージは、メッセージ ハンドラー関数にマップできます。  
  
 この記事で説明されているトピックは次のとおりです。  
  
-   [メッセージ マップ エントリを書き込む](#_core_writing_the_message.2d.map_entry)  
  
-   [ハンドラー関数の宣言](#_core_declaring_the_handler_function)  
  
-   [コマンド Id の範囲の例](#_core_example_for_a_range_of_command_ids)  
  
-   [コントロール Id の範囲の例](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a> メッセージ マップ エントリを書き込む  
 の。CPP ファイルに次の例で示すように、メッセージ マップ エントリを追加します。  
  
 [!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]  
  
 メッセージ マップ エントリは、次の項目で構成されます。  
  
-   メッセージ マップの範囲マクロ:  
  
    -   [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)  
  
    -   [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)  
  
    -   [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)  
  
-   マクロ パラメーター:  
  
     最初の 2 つのマクロは、次の 3 つのパラメーターをとります。  
  
    -   範囲の開始コマンド ID  
  
    -   範囲の最後のコマンド ID  
  
    -   メッセージ ハンドラー関数の名前  
  
     コマンド Id の範囲は連続している必要があります。  
  
     3 番目のマクロでは、 `ON_CONTROL_RANGE`、追加の最初のパラメーターを受け取る: コントロールの通知メッセージなど、 **EN_CHANGE**です。  
  
##  <a name="_core_declaring_the_handler_function"></a> ハンドラー関数の宣言  
 ハンドラー関数の宣言を追加します。H ファイルです。 次のコードは、次に示すようにこれが検索する方法を示しています。  
  
 [!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]  
  
 1 つのコマンド ハンドラー関数には、パラメーターを通常使用するものはありません。 更新ハンドラー関数を除くメッセージ マップの範囲をハンドラー関数は、余分なパラメーターを必要と*nID*、型の**UINT**です。 このパラメーターは、最初のパラメーターです。 このパラメーターには、ユーザーが実際に選択したコマンドを指定するために必要なコマンド ID が対応しています。  
  
 更新ハンドラー関数のパラメーターの要件の詳細については、次を参照してください。[例の Id の範囲コマンド](#_core_example_for_a_range_of_command_ids)です。  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a> 範囲のコマンド Id の例  
 使用すると範囲が 1 つの例では、MFC のサンプルのズーム コマンドと同様のコマンドの処理、 [HIERSVR](../visual-cpp-samples.md)です。 このコマンドは、表示、25% と通常のサイズの 300% の間でスケールを拡大します。 HIERSVR のビュー クラスでは、次のようなメッセージ マップ エントリにズーム コマンドを処理するのに範囲を使用します。  
  
 [!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]  
  
 メッセージ マップ エントリを記述するときに指定します。  
  
-   2 つのコマンド Id、開始と、連続した範囲を終了します。  
  
     ここでは**ID_VIEW_ZOOM25**と**ID_VIEW_ZOOM300**です。  
  
-   コマンドのハンドラー関数の名前。  
  
     ここでは`OnZoom`します。  
  
 関数の宣言には、これは似ています。  
  
 [!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]  
  
 更新ハンドラー関数の場合と同様より広範に使用できる可能性があります。 よく書き込む`ON_UPDATE_COMMAND_UI`コマンドの数のハンドラーを書き込み、またはコピーを同じコードを繰り返し、自分で検索します。 ソリューションは、さまざまなコマンド ハンドラー関数を使用して Id を 1 つの更新をマップする、`ON_UPDATE_COMMAND_UI_RANGE`マクロです。 コマンド Id は、連続する範囲を形成する必要があります。 例については、次を参照してください。、`OnUpdateZoom`ハンドラーとその`ON_UPDATE_COMMAND_UI_RANGE`hiersvr のビュー クラスのメッセージ マップ エントリです。  
  
 通常実行する 1 つのコマンドは、単一のパラメーターのハンドラー関数を更新する*対応付けられた*、型の`CCmdUI*`します。 ハンドラー関数とは異なりメッセージ マップの範囲の更新プログラム ハンドラー関数が不要で追加のパラメーター *nID*、型の**UINT**です。 ユーザーが実際に選択したコマンドを指定するため、コマンド ID がで見つかった、`CCmdUI`オブジェクト。  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a> 範囲のコントロール Id の例  
 もう 1 つの興味深い例では、コントロール Id の範囲に対するコントロール通知メッセージを 1 つのハンドラーにマップします。 たとえば、ユーザーが 10 個のボタンをクリックします。 10 のすべてのボタンを 1 つのハンドラーにマップするには、メッセージ マップ エントリは次のようになります。  
  
 [!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]  
  
 記述するとき、`ON_CONTROL_RANGE`メッセージ マップにマクロを指定します。  
  
-   特定のコントロール通知メッセージです。  
  
     ここでは**BN_CLICKED**です。  
  
-   コントロールの範囲に関連付けられているコントロールの ID 値です。  
  
     ここではこれら**IDC_BUTTON1**と**IDC_BUTTON10**です。  
  
-   メッセージ ハンドラー関数の名前。  
  
     ここでは`OnButtonClicked`します。  
  
 ハンドラー関数を記述するときに指定の余分な**UINT**では、次に示すように、パラメーター。  
  
 [!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]  
  
 `OnButtonClicked`は 1 つのハンドラー **BN_CLICKED**メッセージにはパラメーターがありません。 いずれかになります各種のボタンの同じハンドラー **UINT**です。 余分なパラメーターを使用して、特定のコントロールを生成する役割を識別するため、 **BN_CLICKED**メッセージ。  
  
 例に示すコードは標準的な: に渡された値に変換する、`int`内でメッセージの範囲とこれは大文字と小文字であることをアサートするとします。 ボタンのクリックしてによっていくつかの異なるアクションを利用すること。  
  
## <a name="see-also"></a>関連項目  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
