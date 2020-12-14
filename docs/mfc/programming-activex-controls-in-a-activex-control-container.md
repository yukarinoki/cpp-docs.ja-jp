---
description: '詳細情報: ActiveX コントロールコンテナー: activex コントロールコンテナーでの ActiveX コントロールのプログラミング'
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
ms.openlocfilehash: 34a5a2aaa1d7ec940ea31ae2fbe8c89ba3d84818
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251012"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX コントロール コンテナー : ActiveX コントロール コンテナーでの ActiveX コントロールのプログラミング

この記事では、埋め込み ActiveX コントロールの公開された [メソッド](../mfc/mfc-activex-controls-methods.md) と [プロパティ](../mfc/mfc-activex-controls-properties.md) にアクセスするためのプロセスについて説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

基本的には、次の手順に従います。

1. ギャラリーを使用して activex[コントロールを activex コンテナープロジェクトに挿入](../mfc/inserting-a-control-into-a-control-container-application.md)します。

1. ActiveX コントロールラッパークラスと同じ型のメンバー変数 (またはその他の形式のアクセス)[を定義](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md)します。

1. ラッパークラスの定義済みメンバー関数を使用して[ActiveX コントロールをプログラミングし](#_core_programming_the_activex_control)ます。

ここでは、ActiveX コントロールをサポートするダイアログベースのプロジェクト (名前付きコンテナー) を作成したとします。 Circ サンプルコントロール Circ が、結果のプロジェクトに追加されます。

Circ コントロールがプロジェクトに挿入されたら (手順 1)、アプリケーションのメインダイアログボックスに Circ コントロールのインスタンスを挿入します。

## <a name="procedures"></a>手順

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>ダイアログテンプレートに Circ コントロールを追加するには

1. ActiveX コントロールコンテナープロジェクトを読み込みます。 この例では、プロジェクトを使用し `Container` ます。

1. [リソースビュー] タブをクリックします。

1. **ダイアログ** フォルダーを開きます。

1. メインダイアログボックステンプレートをダブルクリックします。 この例では、 **IDD_CONTAINER_DIALOG** を使用します。

1. ツールボックスの [Circ コントロール] アイコンをクリックします。

1. ダイアログボックス内の位置をクリックして、Circ コントロールを挿入します。

1. [ **ファイル** ] メニューの [ **すべてを保存** ] をクリックして、すべての変更をダイアログボックステンプレートに保存します。

## <a name="modifications-to-the-project"></a>プロジェクトに対する変更

コンテナーアプリケーションが Circ コントロールにアクセスできるようにするために、Visual C++ によってラッパークラス ( `CCirc` ) の実装ファイル () が自動的に追加されます。CPP) をコンテナープロジェクトとラッパークラスヘッダー () に格納します。H) ファイルをダイアログボックスのヘッダーファイルに対して実行します。

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

## <a name="the-wrapper-class-header-h-file"></a><a name="_core_the_wrapper_class_header_28h29_file"></a> ラッパークラスヘッダー (.H) ファイル

Circ コントロールのプロパティの取得と設定 (およびメソッドの呼び出し) を行うために、ラッパークラスは、公開されている `CCirc` すべてのメソッドとプロパティの宣言を提供します。 この例では、これらの宣言は CIRC にあります。 次のサンプルは、 `CCirc` ActiveX コントロールの公開されたインターフェイスを定義するクラスの部分です。

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

これらの関数は、通常の C++ 構文を使用して、アプリケーションの他のプロシージャから呼び出すことができます。 このメンバー関数セットを使用してコントロールのメソッドとプロパティにアクセスする方法の詳細については、「 [ActiveX コントロールのプログラミング](#_core_programming_the_activex_control)」を参照してください。

## <a name="member-variable-modifications-to-the-project"></a><a name="_core_member_variable_modifications_to_the_project"></a> プロジェクトに対するメンバー変数の変更

ActiveX コントロールがプロジェクトに追加され、ダイアログボックスコンテナーに埋め込まれると、プロジェクトの他の部分からアクセスできるようになります。 コントロールにアクセスする最も簡単な方法は[](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) 、 `CContainerDlg` Visual C++ によってプロジェクトに追加されたラッパークラスと同じ型のダイアログクラス (手順 2) のメンバー変数を作成することです。 その後、メンバー変数を使用して、埋め込みコントロールにいつでもアクセスできます。

[ **メンバー変数の追加** ] ダイアログボックスによって *m_circctl* メンバー変数がプロジェクトに追加されると、ヘッダーファイル () に次の行が追加されます。H) を `CContainerDlg` 実行します。

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

さらに、の実装に **DDX_Control** の呼び出しが自動的に追加され `CContainerDlg` `DoDataExchange` ます。

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

## <a name="programming-the-activex-control"></a><a name="_core_programming_the_activex_control"></a> ActiveX コントロールのプログラミング

この時点で、ActiveX コントロールがダイアログテンプレートに挿入され、そのコントロールのメンバー変数が作成されました。 共通の C++ 構文を使用して、埋め込みコントロールのプロパティおよびメソッドにアクセスできるようになりました。

(ラッパークラスヘッダー () に記載されているとおり [です。H) ファイル](#_core_the_wrapper_class_header_28h29_file)、ヘッダーファイル ()。H)、 `CCirc` ラッパークラスの場合 (この場合は CIRC)。H には、公開されているプロパティ値を取得および設定するために使用できるメンバー関数の一覧が含まれています。 公開されたメソッドのメンバー関数も使用できます。

コントロールのプロパティを変更する一般的な場所は、 `OnInitDialog` メインダイアログクラスのメンバー関数です。 この関数は、ダイアログボックスが表示される直前に呼び出され、そのコントロールのいずれかを含む内容を初期化するために使用されます。

次のコード例では、 *m_circctl* メンバー変数を使用して、埋め込まれた Circ コントロールの Caption プロパティと CircleShape プロパティを変更します。

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>関連項目

[ActiveX コントロールコンテナー](../mfc/activex-control-containers.md)
