---
title: 'MFC ActiveX コントロール: カスタム プロパティの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc3aa3f7aa8b6f4abf28c12a11f75540f59238e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352426"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX コントロール : カスタム プロパティの追加
カスタム プロパティとは異なり、ストック プロパティのカスタム プロパティがによって既に実装されていない、`COleControl`クラスです。 カスタム プロパティを使用して、特定の状態やコントロールを使用してプログラマに ActiveX コントロールの外観を公開できます。  
  
 この記事では、プロパティの追加ウィザードを使用して ActiveX コントロールをカスタム プロパティを追加する方法について説明し、結果として得られるコードの変更について説明します。 ここでは、次の内容について説明します。  
  
-   [プロパティの追加ウィザードを使用して、カスタム プロパティを追加するには](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [カスタム プロパティのプロパティ ウィザードによる変更を追加します。](#_core_classwizard_changes_for_custom_properties)  
  
 カスタム プロパティには、実装の 4 つの種類: メンバー変数のメンバー変数の通知、Get と Set メソッド、およびパラメーター化されたとします。  
  
-   メンバー変数の実装  
  
     この実装では、コントロール クラスのメンバー変数とプロパティの状態を表します。 プロパティの値が変更されたときを知る必要があるいない場合は、メンバー変数の実装を使用します。 3 つの種類のこの実装は、最小限のプロパティのサポート コードを作成します。 メンバー変数の実装のディスパッチ マップ エントリ マクロは[DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property)です。  
  
-   通知の実装とメンバー変数  
  
     この実装は、メンバー変数とプロパティの追加ウィザードによって作成された関数の通知で構成されます。 通知関数は、プロパティ値が変更された後に、フレームワークによって自動的に呼び出されます。 変数を使用してメンバー通知の実装とプロパティの値が変更された後に通知する必要がある場合。 この実装では、関数呼び出しが必要とするためより多くの時間が必要です。 この実装のディスパッチ マップ エントリ マクロは[DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify)です。  
  
-   メソッドの実装を取得/設定  
  
     この実装は、コントロール クラスのメンバー関数のペアで構成されます。 Get/set メソッド実装では、自動的にメンバーを呼び出します Get 関数、コントロールのユーザー プロパティの現在の値を要求して、セット メンバー関数、コントロールのユーザーが、プロパティを変更することを要求するとき。 必要があります、実行時のプロパティの値を計算する実際のプロパティを変更する前に、コントロールのユーザーによって渡される値を検証するか、読み取りまたは書き込みの専用のプロパティの型を実装する場合は、この実装を使用します。 この実装のディスパッチ マップ エントリ マクロは[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex)です。 次のセクションでは、[カスタム プロパティを追加するプロパティの追加ウィザードを使用して](#_core_using_classwizard_to_add_a_custom_property)、CircleOffset カスタム プロパティを使用して、この実装を示します。  
  
-   パラメーター化の実装  
  
     パラメーター化されたプロパティの追加ウィザードによってサポートされています。 使用にアクセスする一連の値、コントロールの 1 つのプロパティ (プロパティ配列とも呼ばれます)、パラメーター化されたプロパティを使用できます。 この実装のディスパッチ マップ エントリ マクロは`DISP_PROPERTY_PARAM`します。 この型の実装の詳細については、次を参照してください。[パラメーター化されたプロパティを実装する](../mfc/mfc-activex-controls-advanced-topics.md)記事 ActiveX コントロール: 高度なトピックです。  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> 使用して、プロパティの追加ウィザードのカスタム プロパティを追加するには  
 次の手順では、CircleOffset で、Get と Set メソッドの実装を使用して、カスタム プロパティを追加することを示します。 CircleOffset のカスタム プロパティは、コントロールの外接する四角形の中心から円をオフセットするコントロールのユーザーを使用できます。 カスタム プロパティを Get/set メソッド以外の実装を追加する手順は、よく似ています。  
  
 これと同じ手順は、必要なその他のカスタム プロパティを追加するも使用できます。 CircleOffset プロパティの名前およびパラメーターについて、カスタム プロパティの名前に置き換えます。  
  
#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用して CircleOffset カスタム プロパティを追加するには  
  
1.  コントロールのプロジェクトを読み込みます。  
  
2.  [クラス ビュー] で、コントロールのライブラリ ノードを展開します。  
  
3.  コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。  
  
4.  ショートカット メニューから **[追加]** をクリックし、**プロパティの追加**です。  
  
     開き、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)です。  
  
5.  **プロパティ名**ボックスに、入力`CircleOffset`です。  
  
6.  **[実装型]** として、 **[Get/Set メソッド]** をクリックします。  
  
7.  **プロパティの型**ボックスで、**短い**です。  
  
8.  Get および Set 関数に一意の名前を入力するか、既定の名前を受け入れます。  
  
9. **[完了]** をクリックします。  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> カスタム プロパティのプロパティ ウィザードによる変更を追加します。  
 プロパティの追加ウィザードがヘッダーに変更をによって CircleOffset のカスタム プロパティを追加する場合 (です。H) と実装 (です。コントロールのクラス CPP) ファイル。  
  
 次の行に追加します。H ファイルと呼ばれる 2 つの関数の宣言を`GetCircleOffset`と`SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 コントロールの次の行が追加されます。IDL ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 この行は、プロパティの追加ウィザードのメソッドとプロパティの一覧で、メソッドの位置から取得する、特定の ID 番号を CircleOffset プロパティに割り当てます。  
  
 ディスパッチ マップに次の行を追加するさらに、(にします。コントロールのクラス CPP ファイル)、コントロールの 2 つのハンドラー関数にマップします。  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 実装では、最後に、`GetCircleOffset`と`SetCircleOffset`関数は、コントロールの末尾に追加します。CPP ファイルです。 ほとんどの場合では、プロパティの値を返す Get 関数を変更します。 Set 関数には、通常の前に、またはプロパティの変更後に実行されるコードが含まれます。  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 プロパティの追加ウィザードに自動的にによって追加される、通話にメモ[SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag)、集合関数の本体にします。 この関数を呼び出すことでは、変更済みとしてにコントロールをマークします。 コントロールが変更された場合は、コンテナーを保存すると、新しい状態が保存されます。 コントロールの永続的な状態の一部として保存し、プロパティ値が変更されるたびに、この関数を呼び出す必要があります。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: プロパティ](../mfc/mfc-activex-controls-properties.md)   
 [MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)
