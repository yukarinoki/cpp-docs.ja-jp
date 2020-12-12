---
description: '詳細については、「ActiveX コントロールコンテナー: ActiveX コントロールをメンバー変数に接続する」を参照してください。'
title: 'ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- ActiveX controls [MFC], member variables of project
- connecting ActiveX controls to container member variables
- ActiveX controls [MFC], accessing
- member variables [MFC], ActiveX controls in project
- ActiveX control containers [MFC], ActiveX controls as member variables
ms.assetid: 7898a336-440d-4a60-be43-cb062b807aee
ms.openlocfilehash: c3b890b5705624a18ec42583b143fbd33e4f0608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271903"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け

コントロールコンテナーアプリケーション内から ActiveX コントロールにアクセスする最も簡単な方法は、ActiveX コントロールを、コントロールを格納するダイアログクラスのメンバー変数に関連付けることです。

> [!NOTE]
> これは、コンテナークラス内から埋め込まれたコントロールにアクセスする唯一の方法ではありませんが、この記事の目的上、十分です。

### <a name="adding-a-member-variable-to-the-dialog-class"></a>ダイアログクラスへのメンバー変数の追加

1. クラスビューから、メインダイアログクラスを右クリックしてショートカットメニューを開きます。 たとえば、「 `CContainerDlg` 」のように入力します。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **変数の追加**] をクリックします。

1. メンバー変数の追加ウィザードで、[ **制御変数**] をクリックします。

1. [ **コントロール id** ] ボックスの一覧で、埋め込み ActiveX コントロールのコントロール id を選択します。 たとえば、「 `IDC_CIRCCTRL1` 」のように入力します。

1. [ **変数名** ] ボックスに名前を入力します。

   たとえば、 *m_circctl* のようにします。

1. [ **完了** ] をクリックして選択内容を確定し、メンバー変数の追加ウィザードを終了します。

## <a name="see-also"></a>関連項目

[ActiveX コントロールコンテナー](activex-control-containers.md)
