---
description: 詳細については、「ActiveX コントロールコンテナー」を参照してください。
title: ActiveX コントロール コンテナー
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC]
- OLE controls [MFC], containers
ms.assetid: 0eb1a713-e607-4c79-a0c7-67c5f1fd5fab
ms.openlocfilehash: 6de379cc152ff35e16366c1b5e920bf3548f4cd4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339105"
---
# <a name="activex-control-containers"></a>ActiveX コントロール コンテナー

ActiveX コントロールコンテナーは、ActiveX コントロールを完全にサポートし、独自のウィンドウやダイアログに組み込むことができるコンテナーです。 ActiveX コントロールは再利用可能なソフトウェア要素で、多くの開発プロジェクトで使用できます。 コントロールを使用すると、アプリケーションのユーザーがデータベースにアクセスし、データを監視し、アプリケーション内でさまざまな選択を行うことができます。 ActiveX コントロールの詳細については、「 [MFC Activex コントロール](mfc-activex-controls.md)」を参照してください。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

コントロールコンテナーは、通常、プロジェクト内で2つの形式を取ります。

- フォームビューなどのダイアログとダイアログに似たウィンドウ。ここでは、ActiveX コントロールをダイアログボックスの任意の場所で使用します。

- アプリケーション内のウィンドウ。 ActiveX コントロールは、ツールバー、またはユーザーウィンドウ内の他の場所で使用されます。

ActiveX コントロールコンテナーは、公開されている [メソッド](mfc-activex-controls-methods.md) と [プロパティ](mfc-activex-controls-properties.md)を使用してコントロールと対話します。 これらのメソッドとプロパティは、コントロールコンテナーによってアクセスおよび変更でき、ActiveX コントロールコンテナープロジェクトのラッパークラスを介してアクセスされます。 埋め込み ActiveX コントロールは、 [イベント](mfc-activex-controls-events.md) を発生させることによってコンテナーと対話することもできます。これにより、アクションが発生したことがコンテナーに通知されます。 コントロールコンテナーは、これらの通知を操作するかどうかを選択できます。

追加の記事では、ActiveX コントロールコンテナープロジェクトの作成から、Visual C++ でビルドされた ActiveX コントロールコンテナーに関連する基本的な実装の問題まで、いくつかのトピックについて説明します。

- [MFC ActiveX コントロールコンテナーの作成](reference/creating-an-mfc-activex-control-container.md)

- [ActiveX コントロールのコンテナー](containers-for-activex-controls.md)

- [ActiveX コントロールコンテナー: ActiveX コントロールのコンテインメントを手動で有効にする](activex-control-containers-manually-enabling-activex-control-containment.md)

- [ActiveX コントロールコンテナー: コントロールコンテナーアプリケーションへのコントロールの挿入](inserting-a-control-into-a-control-container-application.md)

- [ActiveX コントロールコンテナー: ActiveX コントロールをメンバー変数に接続する](activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)

- [ActiveX コントロールコンテナー: ActiveX コントロールからのイベントの処理](activex-control-containers-handling-events-from-an-activex-control.md)

- [ActiveX コントロールコンテナー: コントロールのプロパティの表示と変更](activex-control-containers-viewing-and-modifying-control-properties.md)

- [ActiveX コントロールコンテナー: activex コントロールコンテナーでの ActiveX コントロールのプログラミング](programming-activex-controls-in-a-activex-control-container.md)

- [ActiveX コントロールコンテナー: ダイアログ以外のコンテナーでのコントロールの使用](activex-control-containers-using-controls-in-a-non-dialog-container.md)

ダイアログボックスで ActiveX コントロールを使用する方法の詳細については、「 [ダイアログエディター](../windows/dialog-editor.md) のトピック」を参照してください。

Visual C++ と MFC ActiveX コントロールクラスを使用した ActiveX コントロールの開発の詳細について説明している記事の一覧については、「 [Mfc activex コントロール](mfc-activex-controls.md)」を参照してください。 記事は、機能カテゴリ別にグループ化されています。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
