---
title: アニメーション コントロールの使い方 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3da9684d0218c631cbd745475d48f1cf23addde5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404567"
---
# <a name="using-an-animation-control"></a>アニメーション コントロールの使い方

アニメーション コントロールの一般的な使用方法では、次のパターンに従います。

- コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、ダイアログ ボックスが作成されると作成は自動です。 (必要、 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)アニメーション コントロールに対応するダイアログ クラスのメンバーです)。また、使用することができます、[作成](../mfc/reference/canimatectrl-class.md#create)メンバー関数は、すべてのウィンドウの子ウィンドウとして、コントロールを作成します。

- アニメーション コントロールを呼び出すことによって、AVI クリップを読み込む、[オープン](../mfc/reference/canimatectrl-class.md#open)メンバー関数。 アニメーション コントロールがダイアログ ボックスで、これを行うことをお勧めはダイアログ クラスの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数。

- 呼び出すことによってクリップの再生、[再生](../mfc/reference/canimatectrl-class.md#play)メンバー関数。 アニメーション コントロールがダイアログ ボックスで、これを行うことをお勧めはダイアログ クラスの`OnInitDialog`関数。 呼び出す`Play`アニメーション コントロールが ACS_AUTOPLAY スタイルの設定は必要はありません。

- クリップの一部を表示またはフレームごとの使用を再生する場合、`Seek`メンバー関数。 再生しているクリップを停止する、`Stop`メンバー関数。

- コントロールをすぐに破棄しない場合、メモリからクリップを削除する、呼び出すことによって、`Close`メンバー関数。

- アニメーション コントロールがダイアログ ボックスでは、場合、および`CAnimateCtrl`オブジェクトが自動的に破棄されます。 かどうか、する必要があることに、両方のコントロールを確認し、`CAnimateCtrl`オブジェクトが破棄されました。 コントロールを自動的に破棄するには、AVI クリップが閉じられます。

## <a name="see-also"></a>関連項目

[CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

