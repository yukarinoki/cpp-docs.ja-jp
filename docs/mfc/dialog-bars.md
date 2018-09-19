---
title: ダイアログ バー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed0e773dda8a1a31a028a0b6c5e349b2e3655982
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401499"
---
# <a name="dialog-bars"></a>ダイアログ バー

ダイアログ バーは、ツールバー、一種の[コントロール バー](../mfc/control-bars.md)あらゆる種類のコントロールを含めることができます。 モードレス ダイアログ ボックスでは、特性があるため、 [CDialogBar](../mfc/reference/cdialogbar-class.md)オブジェクトはより強力なツールバーを提供します。

ツールバーのいくつかの主な違いがあると`CDialogBar`オブジェクト。 A `CDialogBar` Visual C ダイアログ エディターを使用して作成およびあらゆる種類の Windows コントロールを含めることができる、ダイアログ テンプレート リソースからオブジェクトを作成します。 ユーザーはコントロールからコントロールのタブにします。 親フレーム ウィンドウの任意の部分を持つダイアログ バーを配置するか、親のサイズが変更された場合の場所に残すにも、配置スタイルを指定できます。 次の図には、さまざまなコントロールをダイアログ バーが表示されます。

![VC ダイアログ バー](../mfc/media/vc378t1.gif "vc378t1")ダイアログ バー

その他の点では、使用、`CDialogBar`オブジェクトはモードレス ダイアログ ボックスでの作業に似ています。 設計およびダイアログ リソースを作成するには、ダイアログ エディターを使用します。

ダイアログ バーの長所の 1 つはボタン以外のコントロールを含めることができます。

独自のダイアログ クラスを派生させるのには通常は`CDialog`、ダイアログ バーの独自のクラスを通常は派生されません。 ダイアログ バーのメイン ウィンドウとダイアログ バー コントロールの通知メッセージ、拡張機能として**BN_CLICKED**または**EN_CHANGE**、横棒グラフ、メイン ウィンドウ、ダイアログ ボックスの親に送信されます。

## <a name="see-also"></a>関連項目

[ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)<br/>
[サンプル](../visual-cpp-samples.md)

