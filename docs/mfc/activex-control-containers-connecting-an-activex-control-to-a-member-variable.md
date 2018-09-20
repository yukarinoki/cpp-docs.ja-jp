---
title: 'ActiveX コントロール コンテナー: ActiveX コントロールをメンバー変数に接続する |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae0cefa518ce44913f5c316a096d221fa9bd41aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433856"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け

コンテナーのアプリケーションをコントロール内での ActiveX コントロールにアクセスする最も簡単な方法では、ActiveX コントロールにコントロールを含むダイアログ クラスのメンバー変数を関連付けます。

> [!NOTE]
>  これは、コンテナー クラス内から埋め込まれたコントロールにアクセスする唯一の方法ではありませんが、この記事の目的で十分です。

### <a name="adding-a-member-variable-to-the-dialog-class"></a>ダイアログ クラスにメンバー変数の追加

1. クラス ビューでは、ショートカット メニューを開き、メイン ダイアログ クラスを右クリックします。 たとえば、`CContainerDlg` のようにします。

1. ショートカット メニューでは、次のようにクリックします。**追加**し**変数の追加**します。

1. メンバー変数の追加ウィザードで次のようにクリックします。**コントロール変数**します。

1. **コントロール ID**ボックスの一覧で、埋め込みの ActiveX コントロールのコントロール ID を選択します。 たとえば、`IDC_CIRCCTRL1` のようにします。

1. **変数名**ボックスに、名前を入力します。

     たとえば、*で*します。

1. クリックして**完了**選択内容を確定し、メンバー変数の追加ウィザードを終了します。

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

