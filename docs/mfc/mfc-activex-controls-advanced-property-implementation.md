---
title: 'MFC ActiveX コントロール : 高度なプロパティの実装'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- properties [MFC], ActiveX controls
- MFC ActiveX controls [MFC], properties
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
ms.openlocfilehash: d4f1265e6540e9f84bdb680e7948a4e308d31bb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364650"
---
# <a name="mfc-activex-controls-advanced-property-implementation"></a>MFC ActiveX コントロール : 高度なプロパティの実装

この資料では、ActiveX コントロールでの詳細プロパティの実装に関連するトピックについて説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

- [読み取り専用および書き込み専用プロパティ](#_core_read2donly_and_write2donly_properties)

- [プロパティからエラー コードを返す](#_core_returning_error_codes_from_a_property)

## <a name="read-only-and-write-only-properties"></a><a name="_core_read2donly_and_write2donly_properties"></a>読み取り専用および書き込み専用プロパティ

プロパティの追加ウィザードには、コントロールの読み取り専用プロパティまたは書き込み専用プロパティを簡単に実装する方法が用意されています。

#### <a name="to-implement-a-read-only-or-write-only-property"></a>読み取り専用または書き込み専用のプロパティを実装するには

1. コントロールのプロジェクトを読み込みます。

1. [クラス ビュー] で、コントロールのライブラリ ノードを展開します。

1. コントロールのインターフェイス ノード (ライブラリ ノードの 2 番目のノード) を右クリックし、ショートカット メニューを開きます。

1. ショートカット メニューの [**追加**] をクリックし、[**プロパティの追加**] をクリックします。

   これにより、[プロパティの追加ウィザードが](../ide/names-add-property-wizard.md)開きます。

1. [**プロパティ名]** ボックスに、プロパティの名前を入力します。

1. **[実装型]** として、 **[Get/Set メソッド]** をクリックします。

1. [**プロパティの種類]** ボックスで、プロパティに適切な型を選択します。

1. 読み取り専用プロパティを使用する場合は、Set 関数名をクリアします。 書き込み専用プロパティが必要な場合は、Get 関数名をクリアします。

1. **[完了]** をクリックします。

これを行うと、プロパティの追加ウィザードは、通常の`SetNotSupported`Set`GetNotSupported`関数または Get 関数の代わりに、関数またはディスパッチ マップ エントリに関数を挿入します。

既存のプロパティを読み取り専用または書き込み専用に変更する場合は、ディスパッチ マップを手動で編集し、不要な Set 関数または Get 関数をコントロール クラスから削除できます。

プロパティを条件付きで読み取り専用または書き込み専用にする場合 (たとえば、コントロールが特定のモードで動作している場合)、Set 関数または Get 関数を通常どおりに提供し`SetNotSupported`、`GetNotSupported`必要に応じて Or 関数を呼び出すことができます。 次に例を示します。

[!code-cpp[NVC_MFC_AxUI#29](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-property-implementation_1.cpp)]

このコード サンプル`SetNotSupported`は、`m_bReadOnlyMode`データ メンバーが**TRUE の**場合に呼び出します。 **FALSE**の場合、プロパティは新しい値に設定されます。

## <a name="returning-error-codes-from-a-property"></a><a name="_core_returning_error_codes_from_a_property"></a>プロパティからエラー コードを返す

プロパティの取得または設定を試みている間にエラーが発生したことを示すには、SCODE `COleControl::ThrowError` (ステータス コード) をパラメータとして受け取る関数を使用します。 事前定義された SCODE を使用することも、独自の SCODE を定義することもできます。 定義済みの SCOD の一覧とカスタム SCOD を定義する手順については、「ActiveX コントロール: 詳細トピック」の[「ActiveX コントロールのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)」を参照してください。

ヘルパー関数は[、COleControl::SetNotSupported、COleControl::GetNotSupported、](../mfc/reference/colecontrol-class.md#setnotsupported)[および COleControl::SetNot許可](../mfc/reference/colecontrol-class.md#setnotpermitted)されたなどの最も一般的な定義済みの SCODEs に対して存在します。 [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported)

> [!NOTE]
> `ThrowError`プロパティの Get 関数または Set 関数またはオートメーション メソッドからエラーを返す手段としてのみ使用されます。 これらは、スタック上に適切な例外ハンドラーが存在する唯一の時間です。

コードの他の領域での例外の報告の詳細については、「ActiveX コントロール: 詳細トピック」の[「COleControl::FireError」](../mfc/reference/colecontrol-class.md#fireerror)と[「ActiveX コントロールのエラーの処理](../mfc/mfc-activex-controls-advanced-topics.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX コントロール : プロパティ](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX コントロール: メソッド](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl クラス](../mfc/reference/colecontrol-class.md)
