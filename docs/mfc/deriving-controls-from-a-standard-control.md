---
description: 詳細については、「標準コントロールからのコントロールの派生」を参照してください。
title: 標準コントロールからのコントロールの派生
ms.date: 11/04/2016
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
ms.openlocfilehash: 80e63464a7ad6d869582c66d5047a255e303a6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327871"
---
# <a name="deriving-controls-from-a-standard-control"></a>標準コントロールからのコントロールの派生

[CWnd](reference/cwnd-class.md)の派生クラスと同様に、既存のコントロールクラスから新しいクラスを派生させることによって、コントロールの動作を変更できます。

### <a name="to-create-a-derived-control-class"></a>派生コントロールクラスを作成するには

1. 既存のコントロールクラスからクラスを派生させ、必要に応じて、 `Create` 基底クラスの関数に必要な引数を提供するようにメンバー関数をオーバーライドし `Create` ます。

1. 特定の Windows メッセージに応答してコントロールの動作を変更するために、メッセージハンドラーのメンバー関数とメッセージマップエントリを提供します。 「 [関数へのメッセージのマッピング」を](reference/mapping-messages-to-functions.md)参照してください。

1. 新しいメンバー関数を指定して、コントロールの機能を拡張します (省略可能)。

ダイアログボックスで派生コントロールを使用するには、追加の作業が必要です。 ダイアログボックス内のコントロールの種類と位置は、通常、ダイアログテンプレートリソースで指定されます。 派生したコントロールクラスを作成する場合、ダイアログテンプレートでは指定できません。これは、リソースコンパイラが派生クラスについて何も認識しないためです。

#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>派生したコントロールをダイアログボックスに配置するには

1. 派生したダイアログクラスの宣言に、派生したコントロールクラスのオブジェクトを埋め込みます。

1. `OnInitDialog`ダイアログクラスのメンバー関数をオーバーライドして、 `SubclassDlgItem` 派生したコントロールのメンバー関数を呼び出します。

`SubclassDlgItem` ダイアログテンプレートから作成されたコントロールを "動的にサブクラス化" します。 コントロールを動的にサブクラス化する場合は、Windows にフックし、独自のアプリケーション内の一部のメッセージを処理した後、残りのメッセージを Windows に渡します。 詳細については、 [](reference/cwnd-class.md#subclassdlgitem) `CWnd` *MFC リファレンス* のクラスの SubclassDlgItem メンバー関数を参照してください。 次の例は、のオーバーライドを記述してを呼び出す方法を示してい `OnInitDialog` `SubclassDlgItem` ます。

[!code-cpp[NVC_MFCControlLadenDialog#3](codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]

派生コントロールはダイアログクラスに埋め込まれているため、ダイアログボックスが構築されるときに作成され、ダイアログボックスが破棄されると破棄されます。 このコードを手動でコントロールを [追加](adding-controls-by-hand.md)する例と比較します。

## <a name="see-also"></a>関連項目

[コントロールの作成と使用](making-and-using-controls.md)<br/>
[コントロール](controls-mfc.md)
