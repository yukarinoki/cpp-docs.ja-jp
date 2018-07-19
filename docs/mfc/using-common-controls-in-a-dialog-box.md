---
title: ダイアログ ボックスで一般的なコントロールの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c848cfa74363d871720f9ca269b114687aad9ecf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382692"
---
# <a name="using-common-controls-in-a-dialog-box"></a>ダイアログ ボックスでのコモン コントロールの使い方
Windows コモン コントロールで使用できます[ ダイアログ ボックス](../mfc/dialog-boxes.md)ビュー、レコード ビュー、およびダイアログ テンプレートに基づくその他のウィンドウを形成します。 軽微な変更を次の手順は形式も機能します。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-use-a-common-control-in-a-dialog-box"></a>ダイアログ ボックスで、一般的なコントロールを使用するには  
  
1.  ダイアログ テンプレートにコントロールを配置[ダイアログ エディターを使用して](../mfc/using-the-dialog-editor-to-add-controls.md)です。  
  
2.  ダイアログ クラスには、コントロールを表すメンバー変数を追加します。 **メンバー変数の追加**ダイアログ ボックスで、**制御変数**ことを確認して**コントロール**が選択されて、**カテゴリ**です。  
  
3.  この一般的なコントロールは、プログラムへの入力を提供して場合、は、その他のメンバーを宣言 variable(s) を処理できるダイアログ クラスでは、値を入力します。  
  
    > [!NOTE]
    >  クラス ビュー コンテキスト メニューを使用してこれらのメンバー変数を追加することができます (を参照してください[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md))。  
  
4.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)ダイアログ クラスの一般的なコントロールの初期の条件を設定します。 前の手順で作成されたメンバー変数を使用して、関数を使用してメンバーの初期値とその他の設定を設定します。 設定には、次の詳細については、コントロールの説明を参照してください。  
  
     使用することも[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange-and-validation.md)チェンジ (DDX) ダイアログ ボックスのコントロールを初期化します。  
  
5.  ダイアログ ボックスのコントロールに、ハンドラーでは、コントロールを操作するのにメンバー変数を使用します。 メソッドでは、次の詳細については、コントロールの説明を参照してください。  
  
    > [!NOTE]
    >  のみ、ダイアログ ボックス自体が存在する限りは、メンバー変数が存在します。 ダイアログ ボックスが閉じられた後に値の入力コントロールのクエリを実行できなきます。 コモン コントロールからの入力値を使用するオーバーライド`OnOK`ダイアログ クラスにします。 オーバーライドの中でクエリ入力値を制御し、それらの値をダイアログ クラスのメンバー変数に格納します。  
  
    > [!NOTE]
    >  また、ダイアログ ボックスのコントロールから値を取得または設定するダイアログ データ エクス チェンジを使用することができます。  
  
## <a name="remarks"></a>コメント  
 ダイアログ ボックスにいくつかの一般的なコントロールの追加は、ダイアログ ボックスが機能しなくなります。 参照してください[コントロール ダイアログ ボックスを追加する、ダイアログはありません機能](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md)の詳細についてはこのような状況を処理する方法です。  
  
## <a name="what-do-you-want-to-do"></a>どうしたいんですか  
  
-   [コントロールを追加 ダイアログ ボックスを手動での代わりにダイアログ エディター](../mfc/adding-controls-by-hand.md)  
  
-   [標準の Windows コモン コントロールのいずれかのコントロールを派生します。](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [子ウィンドウとしてのコモン コントロールを使用します。](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [コントロールから通知メッセージを受信します。](../mfc/receiving-notification-from-common-controls.md)  
  
-   [ダイアログ データ エクス (チェンジ DDX) の使用します。](../mfc/dialog-data-exchange-and-validation.md)  
  
## <a name="see-also"></a>関連項目  
 [作成方法とコントロールの使用](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)

