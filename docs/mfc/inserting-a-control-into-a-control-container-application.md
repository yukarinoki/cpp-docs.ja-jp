---
title: 'ActiveX コントロール コンテナー : コントロール コンテナー アプリケーションへのコントロールの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 1d2fc82628b3bcf842a6efb1d36ab9e8389fc0ba
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618490"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX コントロール コンテナー : コントロール コンテナー アプリケーションへのコントロールの追加

Activex コントロールコンテナーアプリケーションから ActiveX コントロールにアクセスするには、[ [Activex コントロールの挿入](../windows/insert-activex-control-dialog-box.md)] ダイアログボックスを使用して、activex コントロールをコンテナーアプリケーションに追加する必要があります。

Activex コントロールコンテナープロジェクトに activex コントロールを追加するには、「[ダイアログボックスへの activex コントロールの表示と追加](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)」を参照してください。

コントロールを追加したら、ダイアログボックスクラスにメンバー変数 (ActiveX コントロール型) を追加する必要があります。 この手順の詳細については、「[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)」を参照してください。

メンバー変数を追加すると、ラッパークラスと呼ばれるクラスが自動的に生成され、プロジェクトに追加されます。 このクラスは、コントロールコンテナーと埋め込みコントロールの間のインターフェイスとして使用されます。

## <a name="see-also"></a>関連項目

[ActiveX コントロールコンテナー](activex-control-containers.md)
