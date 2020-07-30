---
title: 'MFC ActiveX コントロール : カスタム プロパティの追加'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: 805fffcc6cafe92df91af6b01bb53240a0d70f51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230494"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX コントロール : カスタム プロパティの追加

カスタムプロパティは、クラスによって実装されていないカスタムプロパティであるという点で、ストックプロパティとは異なり `COleControl` ます。 カスタムプロパティは、ActiveX コントロールの特定の状態または外観を、コントロールを使用してプログラマに公開するために使用されます。

この記事では、プロパティの追加ウィザードを使用して ActiveX コントロールにカスタムプロパティを追加する方法と、結果として生成されるコード変更について説明します。 取り上げるトピックは次のとおりです。

- [プロパティの追加ウィザードを使用したカスタムプロパティの追加](#_core_using_classwizard_to_add_a_custom_property)

- [カスタムプロパティのプロパティの追加ウィザードの変更](#_core_classwizard_changes_for_custom_properties)

カスタムプロパティには、メンバー変数、通知を含むメンバー変数、Get/Set メソッド、およびパラメーター化の4種類の実装があります。

- メンバー変数の実装

   この実装は、プロパティの状態をコントロールクラスのメンバー変数として表します。 プロパティ値がいつ変更されるかを把握することが重要でない場合は、メンバー変数の実装を使用します。 3種類のうち、この実装では、プロパティのサポートコードの量が最小限に抑えています。 メンバー変数の実装のディスパッチマップエントリマクロは[DISP_PROPERTY](reference/dispatch-maps.md#disp_property)です。

- 通知実装のメンバー変数

   この実装は、メンバー変数と、プロパティの追加ウィザードによって作成される通知関数で構成されます。 通知関数は、プロパティ値が変更された後、フレームワークによって自動的に呼び出されます。 プロパティ値が変更された後に通知を受け取る必要がある場合は、通知の実装でメンバー変数を使用します。 この実装では、関数呼び出しが必要になるため、より多くの時間が必要になります。 この実装のディスパッチマップエントリマクロは[DISP_PROPERTY_NOTIFY](reference/dispatch-maps.md#disp_property_notify)です。

- Get/Set メソッドの実装

   この実装は、コントロールクラスのメンバー関数のペアで構成されます。 Get/Set メソッドの実装では、コントロールのユーザーがプロパティの現在の値を要求したときに Get メンバー関数が自動的に呼び出され、プロパティの変更をコントロールのユーザーが要求したときにメンバーの設定関数が呼び出されます。 この実装は、実行時にプロパティの値を計算する必要がある場合、実際のプロパティを変更する前にコントロールのユーザーによって渡された値を検証する場合、または読み取り専用または書き込み専用のプロパティ型を実装する場合に使用します。 この実装のディスパッチマップエントリマクロは[DISP_PROPERTY_EX](reference/dispatch-maps.md#disp_property_ex)です。 次のセクションでは、[プロパティの追加ウィザードを使用してカスタムプロパティを追加](#_core_using_classwizard_to_add_a_custom_property)し、CircleOffset カスタムプロパティを使用して、この実装を示します。

- パラメーター化された実装

   パラメーター化された実装は、プロパティの追加ウィザードでサポートされています。 パラメーター化されたプロパティ (プロパティ配列と呼ばれることもあります) を使用して、コントロールの1つのプロパティを使用して一連の値にアクセスできます。 この実装のディスパッチマップエントリマクロは DISP_PROPERTY_PARAM です。 この型の実装の詳細については、「ActiveX コントロール: 高度なトピック」の「[パラメーター化されたプロパティの実装](mfc-activex-controls-advanced-topics.md)」を参照してください。

## <a name="using-the-add-property-wizard-to-add-a-custom-property"></a><a name="_core_using_classwizard_to_add_a_custom_property"></a>プロパティの追加ウィザードを使用したカスタムプロパティの追加

次の手順では、Get/Set メソッドの実装を使用するカスタムプロパティ CircleOffset を追加する方法を示します。 CircleOffset カスタムプロパティを使用すると、コントロールのユーザーは、コントロールの外接する四角形の中心から円をオフセットできます。 Get/Set メソッド以外の実装でカスタムプロパティを追加する手順はよく似ています。

この同じ手順を使用して、必要な他のカスタムプロパティを追加することもできます。 カスタムプロパティ名を CircleOffset プロパティ名とパラメーターに置き換えます。

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用して CircleOffset カスタムプロパティを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)が開きます。

1. [**プロパティ名**] ボックスに「 *CircleOffset*」と入力します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [**プロパティの種類**] ボックスで、を選択し **`short`** ます。

1. Get 関数と Set 関数に一意の名前を入力するか、既定の名前をそのまま使用します。

1. **[完了]** をクリックします。

## <a name="add-property-wizard-changes-for-custom-properties"></a><a name="_core_classwizard_changes_for_custom_properties"></a>カスタムプロパティのプロパティの追加ウィザードの変更

CircleOffset カスタムプロパティを追加すると、プロパティの追加ウィザードによってヘッダー () が変更されます。H) と実装 (.CPP) コントロールクラスのファイル。

に次の行が追加されます。とという2つの関数を宣言する H ファイル `GetCircleOffset` `SetCircleOffset` 。

[!code-cpp[NVC_MFC_AxUI#25](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

次の行がコントロールのに追加されます。IDL ファイル:

[!code-cpp[NVC_MFC_AxUI#26](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

この行は、プロパティの追加ウィザードのメソッドとプロパティの一覧で、メソッドの位置から取得された特定の ID 番号を CircleOffset プロパティに割り当てます。

さらに、次の行がディスパッチマップに追加されます (の)。コントロールクラスの CPP ファイル) を、CircleOffset プロパティをコントロールの2つのハンドラー関数にマップします。

[!code-cpp[NVC_MFC_AxUI#27](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

最後に、および関数の実装をコントロールのの `GetCircleOffset` `SetCircleOffset` 末尾に追加します。CPP ファイル。 ほとんどの場合、プロパティの値を返すように Get 関数を変更します。 Set 関数には、通常、プロパティが変更される前または後に実行する必要があるコードが含まれています。

[!code-cpp[NVC_MFC_AxUI#28](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

プロパティの追加ウィザードでは、Set 関数の本体に[SetModifiedFlag](reference/colecontrol-class.md#setmodifiedflag)への呼び出しが自動的に追加されることに注意してください。 この関数を呼び出すと、コントロールが変更済みとしてマークされます。 コントロールが変更されている場合、コンテナーの保存時に新しい状態が保存されます。 コントロールの永続的な状態の一部として保存されたプロパティが値を変更するたびに、この関数を呼び出す必要があります。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: プロパティ](mfc-activex-controls-properties.md)<br/>
[MFC ActiveX コントロール: メソッド](mfc-activex-controls-methods.md)<br/>
[COleControl クラス](reference/colecontrol-class.md)
