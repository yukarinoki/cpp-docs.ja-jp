---
title: 'Active ドキュメント コンテインメントの例: Office バインダー |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 757fb13ac93fdf26aec67d570ab097b353975604
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408545"
---
# <a name="example-of-active-document-containment-office-binder"></a>Active ドキュメント コンテインメントの例 : Office バインダー

Microsoft Office のバインダーでは、active ドキュメント コンテナーの例を示します。 Office バインダーには、コンテナーと同様の 2 つの主要なペインが含まれています。 左側のウィンドウには、バインダー内のアクティブなドキュメントに対応するアイコンが含まれています。 各ドキュメントと呼ばれる、*セクション*バインダー内。 たとえば、バインダーは、Word 文書、PowerPoint ファイル、Excel スプレッドシート、および具合に含めることができます。

左側のウィンドウでアイコンをクリックすると、対応するアクティブなドキュメントがアクティブにします。 バインダーの右側のウィンドウには、現在選択されているアクティブなドキュメントの内容が表示されます。

開きバインダーに Word 文書のアクティブ化すると、ビュー、フレームの上部にある、Word のメニュー バーとツールバーが表示され、Word コマンドまたはツールを使用して、ドキュメントの内容を編集することができます。 ただし、メニュー バー、バインダーと Word の両方のメニュー バーの組み合わせです。 バインダーと Word の両方であるため**ヘルプ**メニュー、それぞれのメニューの内容がマージされます。 Office バインダーなどの active ドキュメント コンテナーが自動的に提供**ヘルプ** メニューのマージ。 詳細については、を参照してください[ヘルプ メニューのマージ](../mfc/help-menu-merging.md)します。

別のアプリケーションの種類、アクティブなドキュメントのアプリケーションの種類の対応するために、バインダーのインターフェイスの変更のアクティブ ドキュメントを選択するとします。 たとえば、バインダーは、Excel スプレッドシートが含まれる場合 Excel スプレッドシートのセクションを選択すると、バインダーのメニューを変更することを確認はします。

もちろん、バインダーの横にあるコンテナーの可能なその他の種類があります。 ファイル エクスプ ローラーでは、左側のウィンドウが右側のウィンドウが現在選択されているディレクトリに含まれているファイルを表示中に、ドライブまたはネットワーク ディレクトリの階層リストを表示するツリーのコントロールを使用する代表的なデュアル ウィンドウ インターフェイスを使用します。 デュアル ウィンドウ インターフェイスを使用するのではなく、コンテナー (Microsoft Internet Explorer) などのインターネット ブラウザーの種類は通常は 1 つのフレームとハイパーリンクを使用してナビゲーションを提供します。

## <a name="see-also"></a>関連項目

[Active ドキュメント コンテインメント](../mfc/active-document-containment.md)

