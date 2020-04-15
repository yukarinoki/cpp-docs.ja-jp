---
title: 'ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング'
ms.date: 09/12/2018
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
ms.openlocfilehash: 9620f4d47197147db4972c9f2024f6018a705902
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371188"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング

この資料では、埋め込まれた ActiveX コントロールの公開された[メソッド](../mfc/mfc-activex-controls-methods.md)と[プロパティ](../mfc/mfc-activex-controls-properties.md)にアクセスするプロセスについて説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

基本的に、次の手順に従います。

1. [ギャラリーを使用して ActiveX コンテナ プロジェクトに ActiveX コントロールを挿入](../mfc/inserting-a-control-into-a-control-container-application.md)します。

1. ActiveX コントロール ラッパー クラスと同じ型の[メンバー変数](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)(または他の形式のアクセス) を定義します。

1. ラッパー クラスの定義済みメンバー関数を使用して[ActiveX コントロールをプログラミング](#_core_programming_the_activex_control)します。

ここでは、ActiveX コントロールのサポートを使用してダイアログ ベースのプロジェクト (Container という名前) を作成したとします。 Circ サンプル コントロール Circ が、結果のプロジェクトに追加されます。

Circ コントロールがプロジェクトに挿入されたら (手順 1)、Circ コントロールのインスタンスをアプリケーションのメイン ダイアログ ボックスに挿入します。

## <a name="procedures"></a>手順

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>ダイアログ テンプレートに Circ コントロールを追加するには

1. ActiveX コントロール コンテナー プロジェクトを読み込みます。 この例では、プロジェクトを`Container`使用します。

1. [リソース ビュー] タブをクリックします。

1. **ダイアログ**フォルダーを開きます。

1. メイン ダイアログ ボックス テンプレートをダブルクリックします。 この例では、 **IDD_CONTAINER_DIALOG**を使用します。

1. ツールボックスの Circ コントロール アイコンをクリックします。

1. ダイアログ ボックス内のスポットをクリックして、Circ コントロールを挿入します。

1. [**ファイル]** メニューの [**すべて保存]** を選択して、ダイアログ ボックス テンプレートに対するすべての変更を保存します。

## <a name="modifications-to-the-project"></a>プロジェクトへの変更

コンテナー アプリケーションが Circ コントロールにアクセスできるようにするために、Visual C++ はラッパー`CCirc`クラス ( ) 実装ファイル () を自動的に追加します。CPP) をコンテナー プロジェクトとラッパー クラス ヘッダー (.H) ファイルをダイアログ ボックスのヘッダー ファイルに移動します。

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a>ラッパー クラス ヘッダー (.H) ファイル

Circ コントロールのプロパティを取得して設定し、メソッドを呼び出`CCirc`すために、ラッパー クラスは、公開されているすべてのメソッドとプロパティの宣言を提供します。 この例では、これらの宣言は CIRC にあります。H。 次の例は、ActiveX`CCirc`コントロールの公開インターフェイスを定義するクラスの一部です。

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

これらの関数は、通常の C++ 構文を使用して、アプリケーションの他のプロシージャから呼び出すことができます。 このメンバ関数セットを使用してコントロールのメソッドとプロパティにアクセスする方法の詳細については[、「ActiveX コントロールのプログラミング](#_core_programming_the_activex_control)」を参照してください。

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a>プロジェクトへのメンバー変数の変更

ActiveX コントロールをプロジェクトに追加し、ダイアログ ボックス コンテナに埋め込むと、プロジェクトの他の部分からアクセスできます。 コントロールにアクセスする最も簡単な方法は、Visual `CContainerDlg` C++ によってプロジェクトに追加されたラッパー クラスと同じ型のダイアログ クラス (手順 2) の[メンバー変数を作成](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)することです。 その後、メンバー変数を使用して、いつでも埋め込みコントロールにアクセスできます。

[**メンバー変数の追加**] ダイアログ ボックスで*m_circctl*メンバー変数をプロジェクトに追加すると、ヘッダー ファイルに次の行も追加されます (.H) クラス`CContainerDlg`の:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

また **、DDX_Control**の呼び出しは、 の`CContainerDlg`実装に自動的に`DoDataExchange`追加されます。

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a>ActiveX コントロールのプログラミング

この時点で、ダイアログ テンプレートに ActiveX コントロールを挿入し、そのメンバ変数を作成しました。 これで、一般的な C++ 構文を使用して、埋め込みコントロールのプロパティとメソッドにアクセスできるようになりました。

前述のとおり ([ラッパー クラスヘッダー (.H) ファイル](#_core_the_wrapper_class_header_28h29_file))、ヘッダーファイル(.H)`CCirc`ラッパー クラス (この場合は CIRC) に対して。H は、公開されたプロパティ値を取得および設定するために使用できるメンバー関数の一覧を格納します。 公開メソッドのメンバー関数も使用できます。

コントロールのプロパティを変更する一般的な場所は、メイン`OnInitDialog`ダイアログ クラスのメンバー関数にあります。 この関数は、ダイアログ ボックスが表示される直前に呼び出され、その内容 (コントロールを含む) を初期化するために使用されます。

次のコード例では *、m_circctl*メンバー変数を使用して、埋め込まれた Circ コントロールの Caption プロパティと CircleShape プロパティを変更します。

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>関連項目

[ActiveX コントロール コンテナ](../mfc/activex-control-containers.md)
