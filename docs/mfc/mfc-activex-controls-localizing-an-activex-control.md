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
ms.openlocfilehash: a85ec5cbed797b756afd93cd8423c58d138a0625
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615420"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのローカライズ

この記事では、ActiveX コントロールインターフェイスをローカライズする手順について説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

ActiveX コントロールを国際市場に合わせて調整する場合は、コントロールをローカライズすることをお勧めします。 Windows では、ドイツ語、フランス語、スウェーデン語など、既定の英語に加えて多くの言語がサポートされています。 インターフェイスが英語のみの場合は、コントロールの問題が発生する可能性があります。

一般に、ActiveX コントロールは、常に、アンビエント LocaleID プロパティのロケールに基づいている必要があります。 これには 3 つの方法があります。

- アンビエント LocaleID プロパティの現在の値に基づいて、リソースを常にオンデマンドで読み込みます。 MFC ActiveX コントロールのサンプル[ローカライズ](../overview/visual-cpp-samples.md)では、この方法を使用します。

- アンビエント LocaleID プロパティに基づいて、最初のコントロールがインスタンス化されたときにリソースを読み込み、他のすべてのインスタンスに対してこれらのリソースを使用します。 この記事では、この方法について説明します。

    > [!NOTE]
    >  これは、将来のインスタンスのロケールが異なると、場合によっては正しく機能しません。

- 通知関数を使用して、 `OnAmbientChanged` コンテナーのロケールに適切なリソースを動的に読み込みます。

    > [!NOTE]
    >  これはコントロールに対しては機能しますが、アンビエント LocaleID プロパティが変更された場合、ランタイム DLL は独自のリソースを動的に更新しません。 また、ActiveX コントロールのランタイム Dll では、スレッドロケールを使用してリソースのロケールを決定します。

この記事の残りの部分では、2つのローカライズ戦略について説明します。 最初の方法では、[コントロールのプログラミングインターフェイス](#_core_localizing_your_control.92.s_programmability_interface)(プロパティ、メソッド、およびイベントの名前) をローカライズします。 2番目の方法では、コンテナーのアンビエント LocaleID プロパティを使用して、[コントロールのユーザーインターフェイスをローカライズ](#_core_localizing_the_control.92.s_user_interface)します。 コントロールのローカライズのデモンストレーションについては、「MFC ActiveX コントロールのサンプル[ローカライズ](../overview/visual-cpp-samples.md)」を参照してください。

## <a name="localizing-the-controls-programmability-interface"></a><a name="_core_localizing_your_control.92.s_programmability_interface"></a>コントロールのプログラミングインターフェイスのローカライズ

コントロールのプログラミングインターフェイス (プログラマがコントロールを使用するアプリケーションを作成するために使用するインターフェイス) をローカライズする場合は、コントロールの変更されたバージョンを作成する必要があります。IDL ファイル (コントロールタイプライブラリを構築するためのスクリプト) は、サポートする各言語に対応しています。 これは、コントロールのプロパティ名をローカライズするために必要な唯一の場所です。

ローカライズされたコントロールを開発する場合は、タイプライブラリレベルの属性としてロケール ID を含めます。 たとえば、フランス語のローカライズされたプロパティ名を持つタイプライブラリを提供する場合は、サンプルのコピーを作成します。IDL ファイルを呼び出して、SAMPLEFR を呼び出します。IDL. ロケール ID 属性をファイルに追加します (フランス語のロケール ID は 0x040c)。次に例を示します。

[!code-cpp[NVC_MFC_AxLoc#1](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]

SAMPLEFR のプロパティ名を変更します。IDL をフランス語に相当するものにし、MKTYPLIB を使用します。EXE を実行して、フランス語タイプライブラリ (SAMPLEFR) を生成します。TLB.

複数のローカライズされたタイプライブラリを作成するには、ローカライズ版を追加します。IDL ファイルはプロジェクトに自動的に作成されます。

#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>を追加する場合は。IDL ファイルを ActiveX コントロールプロジェクトに

1. コントロールプロジェクトを開いた状態で、[**プロジェクト**] メニューの [**既存項目の追加**] をクリックします。

   **[既存項目の追加]** ダイアログ ボックスが表示されます。

1. 必要に応じて、表示するドライブとディレクトリを選択します。

1. [**ファイルの種類**] ボックスで、[**すべてのファイル ( \* . \* )**] を選択します。

1. [ファイル] ボックスの一覧で、をダブルクリックします。プロジェクトに挿入する IDL ファイル。

1. 必要なものをすべて追加したら、[**開く**] をクリックします。IDL ファイル。

ファイルはプロジェクトに追加されているため、プロジェクトの残りの部分がビルドされるときにビルドされます。 ローカライズされたタイプライブラリは、現在の ActiveX コントロールプロジェクトディレクトリにあります。

コード内では、内部プロパティ名 (通常は英語) が常に使用され、ローカライズされることはありません。 これには、コントロールディスパッチマップ、プロパティエクスチェンジ関数、およびプロパティページデータ交換コードが含まれます。

1つのタイプライブラリ (.TLB) ファイルは、コントロールの実装 () のリソースにバインドされている場合があります。OCX) ファイル。 通常、これは標準化された (通常は英語の) 名前を持つバージョンです。 ローカライズされたバージョンのコントロールを出荷するには、を出荷する必要があります。OCX (既定値に既にバインドされている)。TLB バージョン) と。適切なロケールの TLB。 これは、のみを意味します。バージョンが正しくないため、英語版の場合は OCX が必要です。TLB は既にバインドされています。 その他のロケールでは、ローカライズされたタイプライブラリもに付属している必要があります。脆弱性.

コントロールのクライアントがローカライズされたタイプライブラリを見つけることができるようにするには、ロケール固有のを登録します。Windows システムレジストリの TypeLib セクションにある TLB ファイル。 [AfxOleRegisterTypeLib](reference/registering-ole-controls.md#afxoleregistertypelib)関数の3番目のパラメーター (通常はオプション) がこの目的で提供されています。 次の例では、ActiveX コントロールのフランス語タイプライブラリを登録します。

[!code-cpp[NVC_MFC_AxLoc#2](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]

コントロールが登録されると、関数は、指定されたを `AfxOleRegisterTypeLib` 自動的に検索します。TLB ファイルは、コントロールと同じディレクトリにあり、Windows 登録データベースに登録されます。 の場合は。TLB ファイルが見つかりません。関数は無効です。

## <a name="localizing-the-controls-user-interface"></a><a name="_core_localizing_the_control.92.s_user_interface"></a>コントロールのユーザーインターフェイスのローカライズ

コントロールのユーザーインターフェイスをローカライズするには、コントロールのすべてのユーザーに表示されるリソース (プロパティページやエラーメッセージなど) を言語固有のリソース Dll に配置します。 その後、コンテナーのアンビエント LocaleID プロパティを使用して、ユーザーのロケールに適した DLL を選択できます。

次のコード例は、特定のロケールのリソース DLL を検索して読み込む方法の1つを示しています。 この例で呼び出されるこのメンバー関数は、 `GetLocalizedResourceHandle` ActiveX コントロールクラスのメンバー関数にすることができます。

[!code-cpp[NVC_MFC_AxLoc#3](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]

Switch ステートメントの各ケースでサブ言語 ID をチェックし、より専門的なローカライズを行うことができることに注意してください。 この関数のデモンストレーションについては、「 `GetResourceHandle` MFC ActiveX コントロールのサンプル[ローカライズ](../overview/visual-cpp-samples.md)」の関数を参照してください。

コントロールが最初にコンテナーに読み込まれるときに、 [COleControl:: AmbientLocaleID](reference/colecontrol-class.md#ambientlocaleid)を呼び出してロケール ID を取得できます。 次に、返されたロケール ID 値を、適切なリソースライブラリを読み込む関数に渡すことができ `GetLocalizedResourceHandle` ます。 コントロールは、結果として得られるハンドルを[AfxSetResourceHandle](reference/application-information-and-management.md#afxsetresourcehandle)に渡す必要があります。

[!code-cpp[NVC_MFC_AxLoc#4](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]

上記のコードサンプルを、たとえば、 [COleControl:: OnSetClientSite](reference/colecontrol-class.md#onsetclientsite)のオーバーライドなど、コントロールのメンバー関数に配置します。 さらに、 *m_hResDLL*は、コントロールクラスのメンバー変数である必要があります。

同様のロジックを使用して、コントロールのプロパティページをローカライズできます。 プロパティページをローカライズするには、次の例のようなコードをプロパティページの実装ファイルに追加します ( [COlePropertyPage:: OnSetPageSite](reference/colepropertypage-class.md#onsetpagesite)のオーバーライド内)。

[!code-cpp[NVC_MFC_AxLoc#5](codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
