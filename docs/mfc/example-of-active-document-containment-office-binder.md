---
description: '詳細情報: Active ドキュメントコンテインメントの例: Office バインダー'
title: 'Active ドキュメント コンテインメントの例 : Office バインダー'
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
ms.openlocfilehash: 075922f3a50df77f83aab90dc380e33f703737fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290831"
---
# <a name="example-of-active-document-containment-office-binder"></a>Active ドキュメント コンテインメントの例 : Office バインダー

Microsoft Office バインダーは、アクティブなドキュメントコンテナーの一例です。 Office バインダーには、通常、コンテナーとして2つの主要なペインがあります。 左側のウィンドウには、バインダー内のアクティブなドキュメントに対応するアイコンが表示されます。 各ドキュメントは、バインダー内の *セクション* と呼ばれます。 たとえば、バインダーには Word 文書、PowerPoint ファイル、Excel スプレッドシートなどを含めることができます。

左側のウィンドウにあるアイコンをクリックすると、対応するアクティブなドキュメントがアクティブ化されます。 バインダーの右側のウィンドウに、現在選択されているアクティブなドキュメントの内容が表示されます。

バインダーで Word 文書を開いてアクティブにすると、Word のメニューバーとツールバーがビューフレームの上部に表示され、Word のコマンドまたはツールを使用してドキュメントの内容を編集できます。 ただし、メニューバーはバインダーと Word のメニューバーの両方を組み合わせたものです。 バインダーと Word には両方とも **ヘルプ** メニューがあるため、それぞれのメニューの内容がマージされます。 Office バインダーなどの Active ドキュメントコンテナーは、自動的に **ヘルプ** メニューを結合します。詳細については、「 [[ヘルプ] メニューのマージ](help-menu-merging.md)」を参照してください。

別のアプリケーションの種類の作業中のドキュメントを選択すると、バインダーのインターフェイスは、アクティブなドキュメントのアプリケーションの種類に合わせて変更されます。 たとえば、バインダーに Excel ワークシートが含まれている場合、[Excel スプレッドシート] セクションを選択すると、バインダーのメニューが変更されます。

もちろん、バインダーの横にあるその他の種類のコンテナーもあります。 エクスプローラーでは、通常の2つのウィンドウインターフェイスが使用されます。左側のウィンドウでは、ツリーコントロールを使用してドライブまたはネットワーク内のディレクトリの階層リストが表示され、右側のウィンドウには現在選択されているディレクトリに含まれるファイルが表示されます。 インターネットブラウザーの種類のコンテナー (Microsoft Internet Explorer など) は、通常、1つのフレームを持ち、ハイパーリンクを使用したナビゲーションを提供します。

## <a name="see-also"></a>関連項目

[Active ドキュメントコンテインメント](active-document-containment.md)
