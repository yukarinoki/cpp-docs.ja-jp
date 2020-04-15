---
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
ms.openlocfilehash: 620a9ec58b3a5a8fcdac63626b81fbc4620de399
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371620"
---
# <a name="activex-control-containers-connecting-an-activex-control-to-a-member-variable"></a>ActiveX コントロール コンテナー : ActiveX コントロールとメンバー変数の関連付け

コントロール コンテナー アプリケーション内から ActiveX コントロールにアクセスする最も簡単な方法は、ActiveX コントロールを、そのコントロールを含むダイアログ クラスのメンバ変数に関連付ける方法です。

> [!NOTE]
> コンテナー クラス内から埋め込みコントロールにアクセスする方法は、この方法だけではありませんが、この記事の目的で十分です。

### <a name="adding-a-member-variable-to-the-dialog-class"></a>ダイアログ クラスへのメンバー変数の追加

1. クラス ビューで、メイン ダイアログ クラスを右クリックしてショートカット メニューを開きます。 たとえば、「 `CContainerDlg` 」のように入力します。

1. ショートカット メニューの [**追加**] をクリックし、[**変数の追加**] をクリックします。

1. メンバー変数の追加ウィザードで、**コントロール変数**をクリックします。

1. [**コントロール ID] ボックス**の一覧で、埋め込まれた ActiveX コントロールのコントロール ID を選択します。 たとえば、「 `IDC_CIRCCTRL1` 」のように入力します。

1. [**変数名**] ボックスに名前を入力します。

   たとえば *、m_circctl。*

1. [**完了] を**クリックして選択内容を受け入れ、メンバー変数の追加ウィザードを終了します。

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナ](../mfc/activex-control-containers.md)
