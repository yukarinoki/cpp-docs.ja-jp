---
title: 'MFC ActiveX コントロール : 高度なプロパティの実装'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: 017959c5809d324af6ab13247fd093a6df280dab
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502210"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX コントロール : 高度なプロパティの実装

この記事では、ActiveX コントロールでの高度なプロパティの実装に関連するトピックについて説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

- [読み取り専用プロパティと書き込み専用プロパティ](#_core_read2donly_and_write2donly_properties)

- [プロパティからエラーコードを返す](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a> 読み取り専用プロパティと書き込み専用プロパティ

プロパティの追加ウィザードを使用すると、コントロールの読み取り専用または書き込み専用のプロパティをすばやく簡単に実装できます。

#### <a name="to-implement-a-read-only-or-write-only-property"></a>読み取り専用または書き込み専用のプロパティを実装するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカットメニューの [ **追加** ] をクリックし、[ **プロパティの追加**] をクリックします。

   これにより、 [プロパティの追加ウィザード](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)が開きます。

1. [ **プロパティ名** ] ボックスに、プロパティの名前を入力します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [ **プロパティの種類** ] ボックスで、プロパティに適切な型を選択します。

1. 読み取り専用プロパティが必要な場合は、[関数名の設定] をオフにします。 書き込み専用プロパティが必要な場合は、Get 関数名をクリアします。

1. **[完了]** をクリックします。

この操作を行うと、 `SetNotSupported` `GetNotSupported` 通常の Set 関数または Get 関数の代わりに、プロパティの追加ウィザードによって関数またはディスパッチマップエントリが挿入されます。

既存のプロパティを読み取り専用または書き込み専用に変更する場合は、ディスパッチマップを手動で編集し、不要な Set または Get 関数を control クラスから削除します。

プロパティを条件付きで読み取り専用または書き込み専用にする場合 (たとえば、コントロールが特定のモードで動作している場合にのみ) は、Set 関数または Get 関数を通常のように指定し、 `SetNotSupported` 適切な場所で関数または関数を呼び出すことができ `GetNotSupported` ます。 次に例を示します。

[!code-cpp[NVC_MFC_AxUI#29](codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

このコードサンプル `SetNotSupported` では、 `m_bReadOnlyMode` データメンバーが **TRUE**の場合、が呼び出されます。 **FALSE**の場合、プロパティは新しい値に設定されます。

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a> プロパティからエラーコードを返す

プロパティを取得または設定しようとしているときにエラーが発生したことを示すには、 `COleControl::ThrowError` 関数を使用します。この関数は、SCODE (状態コード) をパラメーターとして受け取ります。 定義済みの SCODE を使用することも、独自の SCODE を定義することもできます。 定義済みの SCODEs の一覧およびカスタム SCODEs を定義する手順については、「ActiveX コントロール: 高度なトピック」の「 [Activex コントロールでのエラーの処理](mfc-activex-controls-advanced-topics.md) 」を参照してください。

このヘルパー関数は、最も一般的な定義済みの SCODEs (例: [colecontrol:: SetNotSupported](reference/colecontrol-class.md#setnotsupported)、 [Colecontrol:: GetNotSupported](reference/colecontrol-class.md#getnotsupported)、および [colecontrol:: setnotpermitted](reference/colecontrol-class.md#setnotpermitted)) に対して存在します。

> [!NOTE]
> `ThrowError` は、プロパティの Get または Set 関数またはオートメーションメソッド内からエラーを返す手段としてのみ使用されることを意図しています。 これらは、適切な例外ハンドラーがスタックに存在する唯一の時間です。

コードの他の領域の例外を報告する方法の詳細については、「ActiveX コントロール: 高度なトピック」の「 [COleControl:: 焼討 error](reference/colecontrol-class.md#fireerror) 」および「 [Activex コントロールのエラー処理](mfc-activex-controls-advanced-topics.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール: プロパティ](mfc-activex-controls-properties.md)<br/>
[MFC ActiveX コントロール: メソッド](mfc-activex-controls-methods.md)<br/>
[COleControl クラス](reference/colecontrol-class.md)
