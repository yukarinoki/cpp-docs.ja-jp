---
description: 詳細については、「アニメーションコントロールの使用」を参照してください。
title: アニメーション コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: 7ef4a7b5eb005569ac2a3e3cb66cc0ed785e9299
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202718"
---
# <a name="using-an-animation-control"></a>アニメーション コントロールの使い方

アニメーションコントロールの一般的な使用方法は、次のパターンに従います。

- コントロールが作成されます。 ダイアログボックステンプレートでコントロールが指定されている場合、ダイアログボックスが作成されると、作成が自動的に作成されます。 (アニメーションコントロールに対応する [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) メンバーが dialog クラスに存在している必要があります)。または、 [create](../mfc/reference/canimatectrl-class.md#create) member 関数を使用して、ウィンドウの子ウィンドウとしてコントロールを作成することもできます。

- [Open](../mfc/reference/canimatectrl-class.md#open)メンバー関数を呼び出して、アニメーションコントロールに AVI クリップを読み込みます。 アニメーションコントロールがダイアログボックス内にある場合は、ダイアログクラスの [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 関数内に配置することをお勧めします。

- [Play](../mfc/reference/canimatectrl-class.md#play)メンバー関数を呼び出して、クリップを再生します。 アニメーションコントロールがダイアログボックス内にある場合は、ダイアログクラスの関数内に配置することをお勧めし `OnInitDialog` ます。 `Play`アニメーションコントロールに ACS_AUTOPLAY スタイルが設定されている場合、を呼び出す必要はありません。

- クリップの一部を表示する場合、またはフレームごとに再生する場合は、 `Seek` メンバー関数を使用します。 再生中のクリップを停止するには、 `Stop` メンバー関数を使用します。

- コントロールをすぐに破棄しない場合は、メンバー関数を呼び出してメモリからクリップを削除し `Close` ます。

- アニメーションコントロールがダイアログボックス内にある場合、そのコントロールは `CAnimateCtrl` 自動的に破棄されます。 それ以外の場合は、コントロールとオブジェクトの両方が正しく破棄されていることを確認する必要があり `CAnimateCtrl` ます。 コントロールを破棄すると、AVI クリップが自動的に閉じられます。

## <a name="see-also"></a>関連項目

[CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
