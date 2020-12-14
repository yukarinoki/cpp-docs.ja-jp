---
description: 詳細については、「Message-Map 範囲のハンドラー」を参照してください。
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
ms.openlocfilehash: 1b0f829a4c75aa8ee6148bdf3e96f6886ab07aba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248919"
---
# <a name="handlers-for-message-map-ranges"></a>範囲内のメッセージのハンドラー

この記事では、メッセージの範囲を1つのメッセージハンドラー関数にマップする方法について説明します (1 つのメッセージを1つの関数にマップするのではなく)。

複数のメッセージまたはコントロール通知をまったく同じ方法で処理する必要がある場合もあります。 このような場合は、すべてのメッセージを1つのハンドラー関数にマップする必要があります。 メッセージマップの範囲を使用すると、メッセージの連続した範囲に対してこれを行うことができます。

- コマンド Id の範囲を次のようにマップできます。

  - コマンドハンドラー関数。

  - コマンド更新ハンドラー関数。

- コントロール Id の範囲のコントロール通知メッセージは、メッセージハンドラー関数にマップできます。

この記事では、次のトピックについて説明します。

- [メッセージマップエントリを書き込んでいます](#_core_writing_the_message.2d.map_entry)

- [ハンドラー関数の宣言](#_core_declaring_the_handler_function)

- [コマンド Id の範囲の例](#_core_example_for_a_range_of_command_ids)

- [コントロール Id の範囲の例](#_core_example_for_a_range_of_control_ids)

## <a name="writing-the-message-map-entry"></a><a name="_core_writing_the_message.2d.map_entry"></a> Message-Map エントリの書き込み

の。CPP ファイルを追加し、次の例に示すように、メッセージマップエントリを追加します。

[!code-cpp[NVC_MFCMessageHandling#6](codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

メッセージマップエントリは、次の項目で構成されています。

- メッセージマップの範囲マクロ:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- マクロのパラメーター:

  最初の2つのマクロは、次の3つのパラメーターを受け取ります。

  - 範囲を開始するコマンド ID

  - 範囲を終了するコマンド ID

  - メッセージハンドラー関数の名前

  コマンド Id の範囲は連続している必要があります。

  3番目のマクロは、追加の最初のパラメーター (EN_CHANGE などの `ON_CONTROL_RANGE` コントロール通知メッセージ) を受け取ります。

## <a name="declaring-the-handler-function"></a><a name="_core_declaring_the_handler_function"></a> ハンドラー関数の宣言

にハンドラー関数の宣言を追加します。H ファイル。 次に示すように、これがどのように見えるかを次のコードに示します。

[!code-cpp[NVC_MFCMessageHandling#7](codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

1つのコマンドのハンドラー関数は、通常、パラメーターを受け取りません。 更新ハンドラー関数を除き、メッセージマップの範囲のハンドラー関数には、 **UINT** 型の追加のパラメーター *nID* が必要です。 このパラメーターは、最初のパラメーターです。 追加のパラメーターは、ユーザーが実際に選択したコマンドを指定するために必要な追加のコマンド ID に対応します。

ハンドラー関数を更新するためのパラメーター要件の詳細については、「 [コマンド id の範囲の例](#_core_example_for_a_range_of_command_ids)」を参照してください。

## <a name="example-for-a-range-of-command-ids"></a><a name="_core_example_for_a_range_of_command_ids"></a> コマンド Id の範囲の例

範囲を使用する場合、1つの例は、MFC サンプル [HIERSVR](../overview/visual-cpp-samples.md)の Zoom コマンドのようなコマンドを処理することです。 このコマンドは、ビューをズームし、標準サイズの25% から300% の間にスケーリングします。 HIERSVR のビュークラスは、範囲を使用して、次のようなメッセージマップエントリでズームコマンドを処理します。

[!code-cpp[NVC_MFCMessageHandling#8](codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

メッセージマップエントリを記述するときは、次の項目を指定します。

- 2つのコマンド Id。連続した範囲を開始および終了します。

   ここでは、 **ID_VIEW_ZOOM25** と **ID_VIEW_ZOOM300** しています。

- コマンドのハンドラー関数の名前。

   次のように `OnZoom` なります。

関数宣言は次のようになります。

[!code-cpp[NVC_MFCMessageHandling#9](codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

更新ハンドラー関数の大文字と小文字の区別は似ており、より広く使用されている可能性があります。 `ON_UPDATE_COMMAND_UI`多くのコマンドに対してハンドラーを記述し、同じコードを何度も記述 (コピー) することは非常に一般的です。 この問題を解決するには、マクロを使用して、コマンド Id の範囲を1つの更新ハンドラー関数にマップし `ON_UPDATE_COMMAND_UI_RANGE` ます。 コマンド Id は、連続した範囲を形成する必要があります。 例については、 `OnUpdateZoom` `ON_UPDATE_COMMAND_UI_RANGE` HIERSVR サンプルのビュークラスのハンドラーとそのメッセージマップエントリを参照してください。

1つのコマンドの更新ハンドラー関数は、通常、型の1つのパラメーター *pCmdUI* を受け取り `CCmdUI*` ます。 ハンドラー関数とは異なり、メッセージマップ範囲の更新ハンドラー関数では、 **UINT** 型の追加のパラメーター *nID* を必要としません。 ユーザーが実際に選択したコマンドを指定するために必要なコマンド ID は、オブジェクトにあり `CCmdUI` ます。

## <a name="example-for-a-range-of-control-ids"></a><a name="_core_example_for_a_range_of_control_ids"></a> コントロール Id の範囲の例

もう1つの興味深いケースは、コントロール Id の範囲の制御通知メッセージを1つのハンドラーにマップすることです。 ユーザーが10個のボタンをクリックできるとします。 すべての10個のボタンを1つのハンドラーにマップするために、メッセージマップエントリは次のようになります。

[!code-cpp[NVC_MFCMessageHandling#10](codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

メッセージマップにマクロを記述する場合は `ON_CONTROL_RANGE` 、次のように指定します。

- 特定のコントロール通知メッセージ。

   ここで **BN_CLICKED** です。

- コントロールの連続する範囲に関連付けられているコントロール ID の値。

   ここでは、 **IDC_BUTTON1** と **IDC_BUTTON10** について説明します。

- メッセージハンドラー関数の名前。

   次のように `OnButtonClicked` なります。

ハンドラー関数を記述するときは、次に示すように、余分な **UINT** パラメーターを指定します。

[!code-cpp[NVC_MFCMessageHandling#11](codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

`OnButtonClicked`1 つの **BN_CLICKED** メッセージのハンドラーはパラメーターを受け取りません。 ボタンの範囲に対する同じハンドラーは、1つの **UINT** を受け取ります。 余分なパラメーターを使用すると、 **BN_CLICKED** メッセージの生成を担当する特定のコントロールを識別できます。

この例に示すコードは、一般的な例です。メッセージ範囲内のに渡された値を変換し、その **`int`** ような場合にアサートします。 次に、どのボタンがクリックされたかに応じて、別のアクションを実行することができます。

## <a name="see-also"></a>関連項目

[メッセージハンドラー関数の宣言](declaring-message-handler-functions.md)
