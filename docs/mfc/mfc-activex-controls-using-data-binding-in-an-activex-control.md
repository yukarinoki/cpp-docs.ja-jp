---
description: '詳細については、「MFC ActiveX コントロール: ActiveX コントロールでのデータバインディングの使用」を参照してください。'
title: 'MFC ActiveX コントロール : ActiveX コントロールにおけるデータ バインディングの使用'
ms.date: 11/19/2018
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
ms.openlocfilehash: eb6a6ea52dee7aaf1fcb4c9f15db89cfa5f25deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206085"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールにおけるデータ バインディングの使用

ActiveX コントロールのより強力な使用方法の1つとして、データバインディングがあります。これにより、コントロールのプロパティをデータベース内の特定のフィールドにバインドできます。 ユーザーがこのバインドされたプロパティのデータを変更すると、コントロールはデータベースに通知し、レコードフィールドを更新するように要求します。 次に、データベースは、要求が成功したか失敗したかを制御します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

この記事では、タスクの制御側について説明します。 データバインディングとデータベースの対話を実装することは、コントロールコンテナーの役割です。 コンテナー内のデータベースの相互作用を管理する方法については、このドキュメントでは扱いません。 データバインディング用にコントロールを準備する方法については、この記事の残りの部分で説明します。

![データ&#45;バインドされたコントロールの概念図](../mfc/media/vc374v1.gif "データ&#45;バインドされたコントロールの概念図") <br/>
Data-Bound コントロールの概念図

`COleControl`クラスには、データバインディングを実装する簡単なプロセスを作成する2つのメンバー関数が用意されています。 最初の関数である [Boundpropertyrequestedit](reference/colecontrol-class.md#boundpropertyrequestedit)は、プロパティ値を変更する権限を要求するために使用されます。 2番目の関数である[BoundPropertyChanged](reference/colecontrol-class.md#boundpropertychanged)は、プロパティ値が正常に変更された後に呼び出されます。

この記事では、次のトピックについて説明します。

- [バインド可能なストックプロパティの作成](#vchowcreatingbindablestockproperty)

- [バインド可能な Get/Set メソッドの作成](#vchowcreatingbindablegetsetmethod)

## <a name="creating-a-bindable-stock-property"></a><a name="vchowcreatingbindablestockproperty"></a> バインド可能なストックプロパティの作成

データバインドされたストックプロパティを作成することもできますが、バインド可能な [get/set メソッド](#vchowcreatingbindablegetsetmethod)が必要になる可能性が高くなります。

> [!NOTE]
> ストックプロパティには `bindable` 、 `requestedit` 既定で属性と属性があります。

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してバインド可能なストックプロパティを追加するには

1. [MFC ActiveX コントロールウィザード](reference/mfc-activex-control-wizard.md)を使用してプロジェクトを開始します。

1. コントロールの [インターフェイス] ノードを右クリックします。

   ショートカットメニューが開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **プロパティの追加**] をクリックします。

1. [ **プロパティ名** ] ドロップダウンリストからいずれかのエントリを選択します。 たとえば、 **テキスト** を選択できます。

   **Text** はストックプロパティであるため、**バインド** 可能な属性と **requestedit** 属性は既にチェックされています。

1. [ **IDL 属性** ] タブで次のチェックボックスをオンにします。 **displaybind** と **defaultbind** を選択して、プロジェクトののプロパティ定義に属性を追加します。IDL ファイル。 これらの属性により、コントロールがユーザーに表示され、stock プロパティが既定のバインド可能なプロパティになります。

この時点で、コントロールはデータソースのデータを表示できますが、ユーザーはデータフィールドを更新できません。 コントロールでもデータを更新できるようにするには、 `OnOcmCommand` [onocmcommand](mfc-activex-controls-subclassing-a-windows-control.md) 関数を次のように変更します。

[!code-cpp[NVC_MFC_AxData#1](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

これで、プロジェクトをビルドできるようになりました。これにより、コントロールが登録されます。 ダイアログボックスにコントロールを挿入すると、 **データフィールド** と **データソース** のプロパティが追加され、コントロールに表示するデータソースとフィールドを選択できるようになります。

## <a name="creating-a-bindable-getset-method"></a><a name="vchowcreatingbindablegetsetmethod"></a> バインド可能な Get/Set メソッドの作成

データバインドされた get/set メソッドに加えて、バインド可能な [ストックプロパティ](#vchowcreatingbindablestockproperty)を作成することもできます。

> [!NOTE]
> この手順では、Windows コントロールをサブクラス化する ActiveX コントロールプロジェクトがあることを前提としています。

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用して、バインド可能な get/set メソッドを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [ **コントロールの設定** ] ページで、サブクラス化するコントロールのウィンドウクラスを選択します。 たとえば、編集コントロールをサブクラス化することができます。

1. コントロールのプロジェクトを読み込みます。

1. コントロールの [インターフェイス] ノードを右クリックします。

   ショートカットメニューが開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **プロパティの追加**] をクリックします。

1. [ **プロパティ名** ] ボックスにプロパティ名を入力します。 `MyProp`この例では、を使用します。

1. [ **プロパティの種類** ] ボックスの一覧からデータ型を選択します。 **`short`** この例では、を使用します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [IDL 属性] タブ ([ **バインド** 可能]、[ **requestedit**]、[ **displaybind**]、[ **defaultbind** ]) で、次のチェックボックスをオンにして、プロジェクトののプロパティ定義に属性を追加します。IDL ファイル。 これらの属性により、コントロールがユーザーに表示され、stock プロパティが既定のバインド可能なプロパティになります。

1. **[完了]** をクリックします。

1. 関数の本体を変更して、 `SetMyProp` 次のコードが含まれるようにします。

   [!code-cpp[NVC_MFC_AxData#2](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. および関数に渡される `BoundPropertyChanged` パラメーター `BoundPropertyRequestEdit` は、プロパティの dispid です。このプロパティは、のプロパティの id () 属性に渡されるパラメーターです。IDL ファイル。

1. 次のコードが含まれるように [Onocmcommand](mfc-activex-controls-subclassing-a-windows-control.md) 関数を変更します。

   [!code-cpp[NVC_MFC_AxData#1](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. `OnDraw`次のコードが含まれるように関数を変更します。

   [!code-cpp[NVC_MFC_AxData#3](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. ヘッダーファイルのパブリックセクションにコントロールクラスのヘッダーファイルを追加し、次の定義 (コンストラクター) をメンバー変数に追加します。

   [!code-cpp[NVC_MFC_AxData#4](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. 関数の最後の行に、次の行を作成し `DoPropExchange` ます。

   [!code-cpp[NVC_MFC_AxData#5](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. `OnResetState`次のコードが含まれるように関数を変更します。

   [!code-cpp[NVC_MFC_AxData#6](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. `GetMyProp`次のコードが含まれるように関数を変更します。

   [!code-cpp[NVC_MFC_AxData#7](codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

これで、プロジェクトをビルドできるようになりました。これにより、コントロールが登録されます。 ダイアログボックスにコントロールを挿入すると、 **データフィールド** と **データソース** のプロパティが追加され、コントロールに表示するデータソースとフィールドを選択できるようになります。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
