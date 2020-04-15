---
title: 'MFC ActiveX コントロール : ActiveX コントロールのローカライズ'
ms.date: 09/12/2018
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
ms.openlocfilehash: 987cde2117307cdb5940a31e6f01efb15c527b84
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364598"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのローカライズ

この資料では、ActiveX コントロール インターフェイスをローカライズする手順について説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX に取って代わる最新テクノロジの詳細については、「 [ActiveX コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールを国際市場に適応させる場合は、コントロールをローカライズする必要があります。 Windows では、ドイツ語、フランス語、スウェーデン語など、既定の英語に加えて多くの言語がサポートされています。 この場合、コントロールのインターフェイスが英語のみである場合に、コントロールに問題が発生する可能性があります。

一般に、ActiveX コントロールは常にロケールの基にする必要があります、 ロケールのプロパティをアンビエント。 これには 3 つの方法があります。

- アンビエント LocaleID プロパティの現在の値に基づいて、常にオンデマンドでリソースを読み込みます。 MFC ActiveX コントロールのサンプル[LOCALIZE](../overview/visual-cpp-samples.md)では、この方法を使用します。

- 最初のコントロールがインスタンス化されたときにリソースを読み込み、周囲の LocaleID プロパティに基づいて、その他のすべてのインスタンスにこれらのリソースを使用します。 この記事では、この戦略を示します。

    > [!NOTE]
    >  将来のインスタンスのロケールが異なる場合、これは正しく動作しない場合があります。

- 通知関数`OnAmbientChanged`を使用して、コンテナーのロケールに適したリソースを動的に読み込みます。

    > [!NOTE]
    >  この方法はコントロールで機能しますが、実行時 DLL は、アンビエント LocaleID プロパティが変更されたときに、自身のリソースを動的に更新しません。 さらに、ActiveX コントロールのランタイム DLL は、スレッド ロケールを使用してリソースのロケールを決定します。

この記事の残りの部分では、2 つのローカライズ戦略について説明します。 最初の戦略では[、コントロールのプログラミング インターフェイス](#_core_localizing_your_control.92.s_programmability_interface)(プロパティ、メソッド、およびイベントの名前) をローカライズします。 2 番目の方法では、コンテナーのアンビエント LocaleID プロパティを使用して[、コントロールのユーザー インターフェイスをローカライズ](#_core_localizing_the_control.92.s_user_interface)します。 コントロールのローカライズのデモンストレーションについては、MFC ActiveX コントロールのサンプル[「LOCALIZE」](../overview/visual-cpp-samples.md)を参照してください。

## <a name="localizing-the-controls-programmability-interface"></a><a name="_core_localizing_your_control.92.s_programmability_interface"></a>コントロールのプログラマビリティ インタフェースのローカライズ

コントロールのプログラミング インターフェイス (コントロールを使用するアプリケーションを作成するプログラマが使用するインターフェイス) をローカライズする場合は、コントロールの修正バージョンを作成する必要があります。サポートする言語ごとに IDL ファイル (コントロール タイプ ライブラリを構築するためのスクリプト) を指定します。 これは、コントロールのプロパティ名をローカライズする必要がある唯一の場所です。

ローカライズされたコントロールを開発する場合は、タイプ ライブラリ レベルで属性としてロケール ID を含めます。 たとえば、フランス語のローカライズされたプロパティ名を持つタイプ ライブラリを提供する場合は、SAMPLE のコピーを作成します。IDL ファイルを呼び出し、それを SAMPLEFR と呼びます。Idl。 次のように、ファイルにロケール ID 属性 (フランス語のロケール ID は 0x040c) を追加します。

[!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

SAMPLEFR でプロパティ名を変更します。IDL はフランス語に相当するものにし、MKTYPLIB を使用します。EXE は、フランス語タイプ ライブラリ SAMPLEFR を生成します。Tlb。

複数のローカライズされたタイプ ライブラリを作成するには、任意のローカライズされた を追加できます。IDL ファイルはプロジェクトに追加され、自動的にビルドされます。

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>を追加するには、ActiveX コントロール プロジェクトへの IDL ファイル

1. コントロール プロジェクトを開いた後、[**プロジェクト**] メニューの [**既存項目の追加**] をクリックします。

   [**既存項目の追加]** ダイアログ ボックスが表示されます。

1. 必要に応じて、表示するドライブとディレクトリを選択します。

1. [**ファイルの種類]** ボックスで、[**すべてのファイル\*\*] ( . ) を**選択します。

1. ファイルリストボックスで、 をダブルクリックします。プロジェクトに挿入する IDL ファイル。

1. 必要な値をすべて追加したら、[**開く**] をクリックします。IDL ファイル。

ファイルはプロジェクトに追加されているため、プロジェクトの残りの部分がビルドされるときにビルドされます。 ローカライズされたタイプ ライブラリは、現在の ActiveX コントロール プロジェクト ディレクトリにあります。

コード内では、内部プロパティ名 (通常は英語) が常に使用され、ローカライズされることはありません。 これには、コントロールディスパッチ マップ、プロパティ 交換関数、およびプロパティ ページデータエクスチェンジ コードが含まれます。

タイプ ライブラリ (.TLB) ファイルは、コントロール実装のリソースにバインドすることができます (.OCX) ファイル。 通常、これは標準化された (通常は英語) の名前を持つバージョンです。 コントロールのローカライズ版を出荷するには、 を出荷する必要があります。OCX (これは既にデフォルトにバインドされています。TLB バージョン) と .適切なロケールの TLB。 これは、.正しいので、OCXは、英語版のために必要とされます.TLB は既にバインドされています。 その他のロケールでは、ローカライズされたタイプ ライブラリも .Ocx。

コントロールのクライアントがローカライズされたタイプ ライブラリを見つけられるようにするには、ロケール固有の .Windows システム レジストリの TypeLib セクションの下にある TLB ファイル。 この目的のために[、AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib)関数の 3 番目のパラメーター (通常は省略可能) が用意されています。 次の例では、ActiveX コントロールのフランス語タイプ ライブラリを登録します。

[!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

コントロールが登録されると、`AfxOleRegisterTypeLib`指定された .TLB ファイルは、コントロールと同じディレクトリに格納され、Windows 登録データベースに登録されます。 の場合は、TLB ファイルが見つからない場合、関数は無効です。

## <a name="localizing-the-controls-user-interface"></a><a name="_core_localizing_the_control.92.s_user_interface"></a>コントロールのユーザー インターフェイスのローカライズ

コントロールのユーザー インターフェイスをローカライズするには、コントロールのユーザーに表示されるすべてのリソース (プロパティ ページやエラー メッセージなど) を言語固有のリソース DLL に配置します。 その後、コンテナのアンビエント LocaleID プロパティを使用して、ユーザーのロケールに適した DLL を選択できます。

特定のロケールのリソース DLL を検索して読み込む方法を次のコード例に示します。 この例`GetLocalizedResourceHandle`では、このメンバー関数は、ActiveX コントロール クラスのメンバー関数にすることができます。

[!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

サブ言語 ID は、より特化したローカライズを提供するために、switch ステートメントの各ケースでチェックできることに注意してください。 この関数のデモンストレーションについては、MFC ActiveX コントロールの`GetResourceHandle`サンプル[「LOCALIZE」](../overview/visual-cpp-samples.md)の関数を参照してください。

コントロールが最初にコンテナーに読み込まれるときに[、COleControl::AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)を呼び出してロケール ID を取得できます。 その後、コントロールは返されたロケール ID 値`GetLocalizedResourceHandle`を関数に渡し、適切なリソース ライブラリを読み込みます。 コントロールは、結果として得られるハンドルを[AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle)に渡す必要があります。

[!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

上のコード サンプルをコントロールのメンバー関数[(COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite)のオーバーライドなど) に配置します。 さらに *、m_hResDLL*コントロール クラスのメンバー変数である必要があります。

同様のロジックを使用して、コントロールのプロパティ ページをローカライズできます。 プロパティ ページをローカライズするには、次のサンプルのようなコードをプロパティ ページの実装ファイルに追加します[(COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite)のオーバーライド)。

[!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
