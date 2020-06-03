---
title: 'MFC ActiveX コントロール : カスタム プロパティの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: 00f7a879582bca562ce626fe224206094fd19bc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364699"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX コントロール : カスタム プロパティの追加

カスタム プロパティは、クラスによって`COleControl`実装されていないという点で、ストック プロパティとは異なります。 カスタム プロパティは、コントロールを使用して、特定の状態または ActiveX コントロールの外観をプログラマに公開するために使用されます。

この資料では、プロパティの追加ウィザードを使用して ActiveX コントロールにカスタム プロパティを追加する方法と、結果として生じるコードの変更について説明します。 取り上げるトピックは次のとおりです。

- [プロパティの追加ウィザードを使用してカスタム プロパティを追加する](#_core_using_classwizard_to_add_a_custom_property)

- [カスタム プロパティのプロパティ ウィザードの変更](#_core_classwizard_changes_for_custom_properties)

カスタム プロパティには、メンバー変数、通知付きメンバー変数、Get/Set メソッド、およびパラメータ化の 4 種類があります。

- メンバー変数の実装

   この実装は、コントロール クラスのメンバー変数としてのプロパティの状態を表します。 プロパティ値がいつ変更されるのか知ることが重要でない場合は、メンバー変数の実装を使用します。 この実装では、3 種類の中で、プロパティのサポート コードの量が最も少ないです。 メンバー変数実装のディスパッチ マップ エントリ マクロは[、DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property)されます。

- 通知の実装を伴うメンバー変数

   この実装は、メンバー変数と、プロパティの追加ウィザードによって作成された通知関数で構成されます。 通知関数は、プロパティ値が変更された後にフレームワークによって自動的に呼び出されます。 プロパティ値が変更された後に通知を受け取る必要がある場合は、メンバー変数と通知の実装を使用します。 この実装では、関数呼び出しが必要なため、より多くの時間が必要です。 この実装のディスパッチ マップ エントリ マクロは[DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify)です。

- メソッドの取得/設定の実装

   この実装は、コントロール クラス内のメンバー関数のペアで構成されます。 Get/Set Methods 実装は、コントロールのユーザーがプロパティの現在の値を要求すると Get メンバー関数を自動的に呼び出し、コントロールのユーザーがプロパティの変更を要求したときに Set メンバー関数を呼び出します。 実行時にプロパティの値を計算する必要がある場合、実際のプロパティを変更する前にコントロールのユーザーによって渡された値を検証する場合、または読み取りまたは書き込み専用のプロパティ型を実装する必要がある場合は、この実装を使用します。 この実装のディスパッチ マップ エントリ マクロは[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex)です。 次のセクションでは、[プロパティの追加ウィザードを使用してカスタム プロパティを追加する](#_core_using_classwizard_to_add_a_custom_property)を使用して、CircleOffset カスタム プロパティを使用して、この実装を示します。

- パラメータ化された実装

   パラメーター化された実装は、プロパティの追加ウィザードでサポートされています。 パラメーター化されたプロパティ (プロパティ配列とも呼ばれます) を使用すると、コントロールの 1 つのプロパティを使用して値のセットにアクセスできます。 この実装のディスパッチ マップ エントリ マクロはDISP_PROPERTY_PARAM。 この型の実装の詳細については、「ActiveX コントロール: 詳細トピック」の[「パラメーター化されたプロパティの実装](../mfc/mfc-activex-controls-advanced-topics.md)」を参照してください。

## <a name="using-the-add-property-wizard-to-add-a-custom-property"></a><a name="_core_using_classwizard_to_add_a_custom_property"></a>プロパティ追加ウィザードを使用したカスタム プロパティの追加

次の手順では、Get メソッド/Set メソッド実装を使用するカスタム プロパティ CircleOffset を追加する方法を示します。 CircleOffset カスタム プロパティを使用すると、コントロールのユーザーは、コントロールの外接する四角形の中心から円をオフセットできます。 Get/Set Methods 以外の実装でカスタム プロパティを追加する手順は、非常に似ています。

この同じ手順を使用して、必要な他のカスタム プロパティを追加することもできます。 CircleOffset プロパティ名とパラメータを、カスタム プロパティ名に置き換えます。

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>プロパティ追加ウィザードを使用して CircleOffset カスタム プロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、[プロパティの追加ウィザードが](../ide/names-add-property-wizard.md)開きます。

1. [**プロパティ名**] ボックスに *「CircleOffset」* と入力します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [**プロパティの種類]** ボックスで、[**短い**] を選択します。

1. Get 関数と Set 関数に一意の名前を入力するか、既定の名前をそのまま使用します。

1. **[完了]** をクリックします。

## <a name="add-property-wizard-changes-for-custom-properties"></a><a name="_core_classwizard_changes_for_custom_properties"></a>カスタム プロパティのプロパティ ウィザードの変更を追加する

CircleOffset カスタム プロパティを追加すると、プロパティの追加ウィザードによってヘッダー (.H) および実装 (.コントロール クラスの CPP) ファイル。

次の行が に追加されます。と呼ばれる`GetCircleOffset`2つの関数を宣言`SetCircleOffset`するHファイル:

[!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

次の行がコントロールの に追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

この行は、CircleOffset プロパティに、プロパティの追加ウィザードのメソッドとプロパティのリストでメソッドの位置から取得された特定の ID 番号を割り当てます。

さらに、次の行がディスパッチ マップに追加されます (.コントロール クラスの CPP ファイル) を使用して、CircleOffset プロパティをコントロールの 2 つのハンドラー関数にマップします。

[!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

最後に、`GetCircleOffset`および`SetCircleOffset`関数の実装が、コントロールの末尾に追加されます。CPP ファイル。 ほとんどの場合、Get 関数を変更してプロパティの値を返します。 Set 関数には、通常、プロパティの変更前または変更後に実行する必要のあるコードが含まれます。

[!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

プロパティの追加ウィザードは[、SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag)関数の本体に呼び出しを自動的に追加します。 この関数を呼び出すと、コントロールは変更済みとしてマークされます。 コントロールが変更されている場合、コンテナーを保存すると、その新しい状態が保存されます。 この関数は、コントロールの永続状態の一部として保存されたプロパティが値を変更するたびに呼び出されます。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール : プロパティ](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl クラス](../mfc/reference/colecontrol-class.md)
