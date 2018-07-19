---
title: 'ActiveX コントロール コンテナー: ActiveX コントロール コンテナーで ActiveX コントロールのプログラミング |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1bd8a99faa4cf0444782f402e69da761a8c25e2
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929956"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング
ここで、公開された状態にアクセスする手順について説明[メソッド](../mfc/mfc-activex-controls-methods.md)と[プロパティ](../mfc/mfc-activex-controls-properties.md)埋め込みの ActiveX コントロールのです。 基本的には、これらの手順に従うされます。  
  
1.  [ActiveX コントロールを ActiveX コンテナー プロジェクトに挿入](../mfc/inserting-a-control-into-a-control-container-application.md)ギャラリーを使用します。  
  
2.  [メンバー変数を定義する](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)(またはその他の形式のアクセス) ActiveX と同じ型のラッパー クラスを制御します。  
  
3.  [ActiveX コントロールをプログラム](#_core_programming_the_activex_control)ラッパー クラスのメンバー関数を使用して事前に定義されています。  
  
 詳細については、この ActiveX コントロール サポート (名前付きコンテナー) ダイアログ ベースのプロジェクトを作成したと仮定しています。 というコントロール、Circ は、このプロジェクトに追加されます。  
  
 プロジェクト (ステップ 1) に Circ コントロールを挿入すると、Circ コントロールのインスタンスをアプリケーションのメイン ダイアログ ボックスに挿入します。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Circ コントロール ダイアログ テンプレートを追加するには  
  
1.  ActiveX コントロール コンテナー プロジェクトを読み込みます。 この例では、使用、`Container`プロジェクト。  
  
2.  リソース ビュー タブをクリックします。  
  
3.  開く、**ダイアログ**フォルダーです。  
  
4.  メイン ダイアログ ボックスのテンプレートをダブルクリックします。 この例では、使用**で**です。  
  
5.  ツールボックスに Circ コントロールのアイコンをクリックします。  
  
6.  Circ コントロールを挿入するダイアログ ボックス内で特定の場所をクリックします。  
  
7.  **ファイル** メニューの 選択**すべてを保存** ダイアログ ボックス テンプレートに対するすべての変更を保存します。  
  
## <a name="modifications-to-the-project"></a>プロジェクトへの変更  
 コンテナー アプリケーション Circ コントロールにアクセスするには、Visual C 自動的に追加ラッパー クラス (`CCirc`) 実装ファイル (です。CPP) には、コンテナーのプロジェクトにラッパー クラスのヘッダー (です。H) ダイアログ ボックスのヘッダー ファイルにファイル:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a> ラッパー クラスのヘッダー (です。H) ファイル  
 取得し、プロパティを設定する (メソッドの呼び出し) Circ コントロールに対して、`CCirc`ラッパー クラスが公開されているすべてのメソッドとプロパティの宣言を提供します。 例では、これらの宣言内にある可変範囲H. 次の例は、クラスの部分`CCirc`ActiveX コントロールの公開されているインターフェイスを定義します。  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 これらの関数は、通常の C++ 構文を使用して、アプリケーションのプロシージャの他の呼び出すことができます。 このメンバー関数へのアクセス制御のメソッドとプロパティ セットを使用する方法については、セクションを参照して[ActiveX コントロールをプログラミング](#_core_programming_the_activex_control)です。  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a> プロジェクトにメンバー変数の変更  
 ActiveX コントロールは、プロジェクトに追加され、ダイアログ ボックスのコンテナーに埋め込まれているとは、プロジェクトの他の部分でアクセスできます。 コントロールにアクセスする最も簡単には[メンバー変数を作成](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)ダイアログ クラスの`CContainerDlg`(ステップ 2)、つまり Visual C によってプロジェクトに追加するラッパー クラスと同じ型です。 メンバー変数を使用して、いつでも埋め込まれたコントロールにアクセスすることができますし、します。  
  
 ときに、**メンバー変数の追加** ダイアログ ボックスを追加、*で*メンバー変数をプロジェクトも追加、次の行をヘッダー ファイル (です。H) の`CContainerDlg`クラス。  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 さらへの呼び出し**DDX_Control**に自動的に追加されて、`CContainerDlg`の実装の`DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a> ActiveX コントロールのプログラミング  
 この時点では、ダイアログ テンプレートに、ActiveX コントロールを挿入して、メンバー変数を作成します。 プロパティおよび埋め込みのコントロールのメソッドにアクセスするのに一般的な C++ 構文を使用できます。  
  
 前述の (で[ラッパー クラスのヘッダー (です。H) ファイルに](#_core_the_wrapper_class_header_28h29_file))、ヘッダー ファイル (です。H) の`CCirc`この case 可変範囲内のラッパー クラスH には、取得し、公開されたプロパティ値を設定に使用できるメンバー関数の一覧が含まれています。 公開されたメソッドのメンバー関数も使用できます。  
  
 コントロールのプロパティを変更する一般的な場所は、`OnInitDialog`メイン ダイアログ クラスのメンバー関数。 この関数は、ダイアログ ボックスが表示され、そのコントロールのいずれかを含む、その内容を初期化するために使用される直前に呼び出されます。  
  
 次のコード例では、*で*メンバー変数に埋め込まれた Circ コントロールのキャプションと CircleShape プロパティを変更します。  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)

