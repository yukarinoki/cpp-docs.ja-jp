---
title: 外観、ATL コントロール ウィザード
ms.date: 08/31/2018
f1_keywords:
- vc.codewiz.class.atl.control.misc
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
ms.openlocfilehash: 3484fb5d0f919af0dfd18b584e96d4675e2baea8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319402"
---
# <a name="appearance-atl-control-wizard"></a>外観、ATL コントロール ウィザード

ウィザードのこのページを使用して、コントロールの追加のユーザー要素オプションを指定します。 このページは[、[ATL コントロール ウィザードのオプション]](../../atl/reference/options-atl-control-wizard.md)ページの **[コントロールの種類**] の下の **[標準**コントロール] に指定されているコントロールで使用できます。

## <a name="uielement-list"></a>UI 要素の一覧

- **状態の表示**

   コンテナー内のコントロールの外観を設定します。

  - **不透明**: [viewSTATUS](/windows/win32/api/ocidl/ne-ocidl-viewstatus)列挙体にVIEWSTATUS_OPAQUEビットを設定し[、CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw)メソッドに渡されるコントロール四角形全体を描画します。 コントロールは完全に不透明に表示され、コントロール境界の背後にはコンテナーが表示されません。

      この設定は、コンテナーがコントロールをより迅速に描画するのに役立ちます。 このオプションを選択しない場合、コントロールに透明な部分を含めることができます。

      不透明なコントロールだけが、背景を塗りつぶすことができます。

  - **ソリッド背景**: VIEWSTATUS 列挙体にVIEWSTATUS_SOLIDBKGNDビットを設定します。 コントロールの背景は、パターンのない単色で表示されます。

      このオプションは、[**不透明]** オプションも選択されている場合にのみ使用できます。

- **に基づいてコントロールを追加**

   コントロールを実装するクラスに[CContainedWindow](ccontainedwindowt-class.md)データ メンバーを追加することで、Windows コントロール型に基づくコントロールを設定します。 また、コントロールの Windows メッセージを処理するメッセージ マップとメッセージ ハンドラー関数も追加します。 作成する Windows コントロールの種類を一覧から選択します (存在する場合)。

  - **ボタン**

  - **ListBox**

  - **SysAnimate32**

  - **SysListView32**

  - **ComboBox**

  - **RichEdit**

  - **SysDateTimePick32**

  - **SysMonthCal32**

  - **ComboBoxEx32**

  - **ScrollBar**

  - **SysHeader32**

  - **SysTabControl32**

  - **編集**

  - **静的**

  - **SysIPAddress32**

  - **SysTreeView32**

- **その他のステータス**

   コントロールの外観と動作に関する追加のオプションを設定します。

  - **実行時に非表示**: 実行時にコントロールが非表示に設定されます。 非表示のコントロールを使用すると、時間間隔でイベントを発生するなどの操作をバックグラウンドで実行できます。

  - **ボタンのように動作**する : コントロールがボタンのように動作するように[、OLEMISC](/windows/win32/api/oleidl/ne-oleidl-olemisc)列挙のOLEMISC_ACTSLIKEBUTTONビットを設定します。 コンテナーがコントロールのクライアント サイトを既定のボタンとしてマークしている場合、このオプションを選択すると、ボタン コントロールを既定のボタンとして表示できます。 詳細については[、CCom コントロールベースを](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault)参照してください。

  - **ラベルのように動作**する : OLEMISC 列挙体のOLEMISC_ACTSLIKELABELビットを設定して、コントロールがコンテナのネイティブ ラベルを置き換えるようにします。 コンテナは、このフラグを使用する操作を決定します。

- **その他**

   コントロールのその他の動作オプションを設定します。

  - **正規化された DC**: 描画する場合に、コントロールが呼び出されたときに、正規化されたデバイス コンテキストを作成するように設定します。 この操作によって、コントロールの外観が標準化されますが、描画の効率は低下します。

  - **ウィンドウのみ**: コントロールをウィンドウなしにできないことを指定します。 このオプションを選択しない場合、ウィンドウなしのオブジェクトをサポートするコンテナーではコントロールは自動的にウィンドウなしになり、ウィンドウなしのオブジェクトをサポートしないコンテナーで自動的にウィンドウが表示されます。 このオプションを選択すると、ウィンドウなしのオブジェクトをサポートするコンテナーでも、コントロールが強制的にウィンドウに表示されます。

  - **挿入可能**: Word や Excel などのアプリケーションの **[オブジェクトの挿入**] ダイアログ ボックスにコントロールを表示するには、このオプションを選択します。 このダイアログ ボックスを使用して、埋め込みオブジェクトをサポートする任意のアプリケーションによってコントロールを挿入できます。

## <a name="see-also"></a>関連項目

[ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)<br/>
[SUBEDIT サンプル: 標準 Windows コントロールのスーパークラス](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit)
