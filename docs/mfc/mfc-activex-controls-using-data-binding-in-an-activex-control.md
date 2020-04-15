---
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
ms.openlocfilehash: 41ac0180242aea3143a1df2c32dc81fb18cd7dca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370790"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールにおけるデータ バインディングの使用

ActiveX コントロールの強力な用途の 1 つは、データベース内の特定のフィールドに連結するコントロールのプロパティを使用できるデータ バインディングです。 ユーザーがこのバインドされたプロパティのデータを変更すると、コントロールはデータベースに通知し、レコード フィールドの更新を要求します。 その後、データベースは要求の成功または失敗を制御に通知します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

この記事では、タスクの制御面について説明します。 データベースとのデータ バインディングの対話を実装するは、コントロール コンテナーの役割です。 コンテナー内のデータベース対話の管理方法については、このドキュメントでは説明しません。 データ バインディング用のコントロールの準備方法については、この記事の残りの部分で説明します。

![連結コントロールのデータ&#45;の概念図](../mfc/media/vc374v1.gif "連結コントロールのデータ&#45;の概念図") <br/>
データ バインド コントロールの概念図

この`COleControl`クラスには、データ バインディングを簡単に実装できる 2 つのメンバー関数が用意されています。 最初の関数である[BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit)は、プロパティ値を変更するアクセス許可を要求するために使用されます。 2 番目の関数である[BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged)は、プロパティ値が正常に変更された後に呼び出されます。

この記事では、次のトピックについて説明します。

- [バインド可能なストック プロパティの作成](#vchowcreatingbindablestockproperty)

- [バインド可能な Get/Set メソッドの作成](#vchowcreatingbindablegetsetmethod)

## <a name="creating-a-bindable-stock-property"></a><a name="vchowcreatingbindablestockproperty"></a>バインド可能なストック プロパティの作成

データ バインドストック プロパティを作成することは可能ですが、[バインド可能な get/set メソッド](#vchowcreatingbindablegetsetmethod)が必要になる可能性が高くなります。

> [!NOTE]
> ストック プロパティには`bindable`、`requestedit`属性と 属性が既定で設定されています。

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してバインド可能なストック プロパティを追加するには

1. [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)を使用してプロジェクトを開始します。

1. コントロールのインターフェイス ノードを右クリックします。

   ショートカット メニューが開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

1. **[プロパティ名]** ドロップダウン リストからエントリのいずれかを選択します。 たとえば、**テキスト**を選択できます。

   **Text**はストック プロパティであるため、**バインド可能**な属性と**要求された属性**は既にチェックされています。

1. **[IDL 属性]** タブで、次のチェック ボックスを**オンに****します。** IDL ファイル。 これらの属性は、ユーザーがコントロールを表示し、ストック プロパティを既定のバインド可能なプロパティにします。

この時点で、コントロールはデータ ソースのデータを表示できますが、ユーザーはデータ フィールドを更新できません。 コントロールでデータを更新できるようにする場合は`OnOcmCommand`[、OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)関数を次のように変更します。

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

これで、コントロールを登録するプロジェクトをビルドできます。 ダイアログ ボックスにコントロールを挿入すると、データ**フィールドとデータ****ソース**のプロパティが追加され、コントロールに表示するデータ ソースとフィールドを選択できるようになります。

## <a name="creating-a-bindable-getset-method"></a><a name="vchowcreatingbindablegetsetmethod"></a>バインド可能な Get/Set メソッドの作成

データバインドされた get/set メソッドに加えて、[バインド可能なストック プロパティ](#vchowcreatingbindablestockproperty)を作成することもできます。

> [!NOTE]
> この手順では、Windows コントロールのサブクラスを設定する ActiveX コントロール プロジェクトがあることを前提としています。

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>プロパティの追加ウィザードを使用してバインド可能な get/set メソッドを追加するには

1. コントロールのプロジェクトを読み込みます。

1. [**コントロールの設定]** ページで、サブクラス化するコントロールのウィンドウ クラスを選択します。 たとえば、EDIT コントロールをサブクラス化する場合があります。

1. コントロールのプロジェクトを読み込みます。

1. コントロールのインターフェイス ノードを右クリックします。

   ショートカット メニューが開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

1. [プロパティ名] ボックスに**プロパティ名を**入力します。 この`MyProp`例に使用します。

1. [プロパティタイプ]ドロップダウン リスト ボックスからデータ**タイプを**選択します。 この例では**short**を使用します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [IDL 属性] タブで、**バインド可能**、**要求済**み 、**表示バインド**、**および defaultbind**の各チェック ボックスをオンにして、プロジェクトの プロパティ定義に属性を追加します。IDL ファイル。 これらの属性は、ユーザーがコントロールを表示し、ストック プロパティを既定のバインド可能なプロパティにします。

1. **[完了]** をクリックします。

1. 次のコードが`SetMyProp`含まれるように関数の本体を変更します。

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

1. `BoundPropertyChanged`に渡されるパラメータと`BoundPropertyRequestEdit`関数はプロパティのディピッドで、これは プロパティの id() 属性に渡されるパラメータです。IDL ファイル。

1. 次のコードが含まれるように[OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)関数を変更します。

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

1. 次の`OnDraw`コードが含まれるように関数を変更します。

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

1. ヘッダー ファイルの public セクションに、コントロール クラスのヘッダー ファイルに、メンバー変数の次の定義 (コンストラクター) を追加します。

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

1. 次の行を関数の最後の行`DoPropExchange`にします。

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

1. 次の`OnResetState`コードが含まれるように関数を変更します。

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

1. 次の`GetMyProp`コードが含まれるように関数を変更します。

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

これで、コントロールを登録するプロジェクトをビルドできます。 ダイアログ ボックスにコントロールを挿入すると、データ**フィールドとデータ****ソース**のプロパティが追加され、コントロールに表示するデータ ソースとフィールドを選択できるようになります。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
