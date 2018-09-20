---
title: '方法: ステータス バーにコマンド情報を表示 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 089e0fd8f1853a4e219309c0df7659f90e4f4b3d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405750"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>ステータス バーにコマンド情報を表示する方法

アプリケーションのスケルトンを作成するアプリケーション ウィザードを実行するときに、ツールバーとステータス バーをサポートできます。 アプリケーション ウィザード内の 1 つのオプションは、両方をサポートします。 ステータス バーが存在する場合は、アプリケーションでユーザーが、メニュー項目にポインターを移動すると、操作に役立つ情報が自動的に提供します。 アプリケーションは、メニュー項目が強調表示すると自動的にプロンプト文字列とステータス バーに表示します。 に、ユーザーがポインターを移動したときになど、**切り取り**コマンドを**編集**メニュー、ステータス バー、ステータス バーのメッセージ領域で"選択範囲を切り取ってクリップボードに保存します。"と表示可能性があります。 プロンプトでは、ユーザーがメニュー項目の目的を理解するのに役立ちます。 これは、ユーザーがツール バー ボタンをクリックしたときにも機能します。

プログラムを追加するメニュー項目の表示文字列を定義することで、このステータス バーのヘルプを追加できます。 これを行うには、メニュー エディターのメニュー項目のプロパティを編集するときに、プロンプト文字列を提供します。 定義する文字列、アプリケーションのリソース ファイルに格納されます。説明するコマンドと同じ Id があります。

既定では、アプリケーション ウィザードによって追加されます**AFX_IDS_IDLEMESSAGE**プログラムが新しいメッセージを待機しているときに表示される標準的な"Ready"メッセージの ID。 アプリケーション ウィザードで状況依存のヘルプ オプションを指定する場合、メッセージは「については、F1 キーを押します」に変更します。

## <a name="see-also"></a>関連項目

[メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

