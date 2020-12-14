---
description: '詳細については、「方法: Message-Map 相互参照を使用する」を参照してください。'
title: メッセージ マップ クロス リファレンスの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
ms.openlocfilehash: 4bbc140db59a7df4abd42fdcf68b47273ec3e846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219656"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>メッセージ マップ クロス リファレンスの使い方

[ラベルの付い \<memberFxn> たエントリ] に、派生した [CWnd](../../mfc/reference/cwnd-class.md) クラスの独自のメンバー関数を記述します。 関数に任意の名前を付けます。 などの他の関数 `OnActivate` は、クラスのメンバー関数です `CWnd` 。 呼び出された場合は、メッセージを Windows の関数に渡し `DefWindowProc` ます。 Windows 通知メッセージを処理するには、 `CWnd` 派生クラスの対応する関数をオーバーライドします。 関数は、基底クラスでオーバーライドされた関数を呼び出して、基底クラスと Windows がメッセージに応答できるようにする必要があります。

どのような場合でも、関数プロトタイプを `CWnd` から派生したクラスヘッダーに配置し、表示されているようにメッセージマップエントリをコーディングします。

使用される用語は次のとおりです。

|項目|定義|
|----------|----------------|
|id|任意のユーザー定義のメニュー項目 ID (WM_COMMAND メッセージ) またはコントロール ID (子ウィンドウ通知メッセージ)。|
|"message" と "wNotifyCode"|WINDOWS .H で定義されている windows メッセージ Id。|
|nMessageVariable|Windows 関数からの戻り値を格納する変数の名前 `RegisterWindowMessage` 。|

## <a name="see-also"></a>関連項目

[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)
