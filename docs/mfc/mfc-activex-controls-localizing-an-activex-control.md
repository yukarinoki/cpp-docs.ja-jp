---
title: 'MFC ActiveX コントロール: ActiveX コントロールのローカライズ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LocaleID
- AfxOleRegisterTypeLib
dev_langs:
- C++
helpviewer_keywords:
- localization, ActiveX controls
- MFC ActiveX controls [MFC], localizing
- LocaleID ambient property [MFC]
- LOCALIZE sample [MFC]
ms.assetid: a44b839a-c652-4ec5-b824-04392708a5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9a6495c23695f8cdedf45fbdd7cbc915b96873e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929609"
---
# <a name="mfc-activex-controls-localizing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのローカライズ
この記事では、ActiveX コントロールのインターフェイスをローカライズするための手順について説明します。  
  
 国際市場に ActiveX コントロールを調整する場合は、コントロールをローカライズすることがあります。 Windows では、既定の英語、ドイツ語、フランス語、スウェーデン語を含むだけでなく多くの言語をサポートします。 これは、問題が生じる場合、コントロールの場合は、インターフェイスは英語版のみです。  
  
 一般に、ActiveX コントロール常に基、ロケールに LocaleID アンビエント プロパティです。 これには、次の 3 つの方法があります。  
  
-   LocaleID アンビエント プロパティの現在の値に基づいて、要求時に常に、リソースを読み込みます。 MFC ActiveX コントロールをサンプル[LOCALIZE](../visual-cpp-samples.md)はこの方法を使用します。  
  
-   LocaleID アンビエント プロパティに基づいて、最初のコントロールがインスタンス化時にリソースを読み込むし、その他のすべてのインスタンスに対してこれらのリソースを使用します。 この記事では、この方法について説明します。  
  
    > [!NOTE]
    >  これは正しく動きません場合によっては、将来のインスタンスが別のロケールがある場合。  
  
-   使用して、`OnAmbientChanged`通知関数をコンテナーのロケールの適切なリソースを動的に読み込みます。  
  
    > [!NOTE]
    >  これは、コントロールの機能しますが、ランタイム DLL が動的に更新されない、独自のリソース LocaleID アンビエント プロパティが変更されたときにします。 さらに、ActiveX コントロール ランタイム Dll は、そのリソースのロケールを決定するのにスレッドのロケールを使用します。  
  
 この記事の残りの部分では、次の 2 つのローカライズ方法について説明します。 第 1 の戦略[コントロールのプログラミング インターフェイスをローカライズ](#_core_localizing_your_control.92.s_programmability_interface)(プロパティ、メソッド、およびイベントの名前)。 第 2 の戦略[コントロールのユーザー インターフェイスをローカライズ](#_core_localizing_the_control.92.s_user_interface)コンテナーの LocaleID アンビエント プロパティを使用します。 コントロールのローカリゼーションのデモについては、MFC ActiveX コントロールのサンプルを参照してください。 [LOCALIZE](../visual-cpp-samples.md)です。  
  
##  <a name="_core_localizing_your_control.92.s_programmability_interface"></a> コントロールのプログラミング インターフェイスのローカライズ  
 コントロールのプログラミング インターフェイス (コントロールを使用するアプリケーションを記述するプログラマによって使用されるインターフェイス) をローカライズするときに、コントロールの変更済みバージョンを作成する必要があります。IDL をサポートする言語ごとに (コントロール タイプ ライブラリを構築するためのスクリプト) をファイルです。 これは、コントロールのプロパティ名をローカライズする必要がある唯一の場所です。  
  
 ローカライズされたコントロールを開発する場合は、タイプ ライブラリのレベルにある属性としてロケール ID を含めます。 たとえば、フランス語のローカライズされたプロパティ名を持つタイプ ライブラリを提供する場合は、サンプルのコピーを作成します。IDL ファイル、および SAMPLEFR を呼び出します。IDL です。 ロケール ID 属性 (フランス語のロケール ID は 0x040c)、ファイルを追加するのには、次のような。  
  
 [!code-cpp[NVC_MFC_AxLoc#1](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_1.idl)]  
  
 SAMPLEFR のプロパティ名を変更します。対応するフランス語としを使用して MKTYPLIB IDL です。EXE、フランス語を生成するためには、ライブラリ、SAMPLEFR を入力します。TLB です。  
  
 複数のローカライズされたタイプ ライブラリを作成するには、ローカライズしたを追加することができます。IDL ファイルをプロジェクトと、自動的に構築されます。  
  
#### <a name="to-add-an-idl-file-to-your-activex-control-project"></a>追加する、します。ActiveX コントロール プロジェクトへの IDL ファイル  
  
1.  コントロール プロジェクトを開き、[、**プロジェクト**] メニューのをクリックして**既存項目の追加**です。  
  
     **既存項目の追加** ダイアログ ボックスが表示されます。  
  
2.  必要に応じて、ドライブとを表示するディレクトリを選択します。  
  
3.  **ファイルの種類**ボックスで、**すべてのファイル (\*.\*)**.  
  
4.  ファイルの一覧ボックスをダブルクリックします。IDL ファイルがプロジェクトに挿入します。  
  
5.  をクリックして**開く**追加したら、必要なすべてです。IDL ファイル。  
  
 ファイルをプロジェクトに追加されて、ため、残りのプロジェクトのビルド時にビルドされます。 ローカライズされたタイプ ライブラリは、現在の ActiveX コントロール プロジェクト ディレクトリにあります。  
  
 コード内では、(英語) では通常内部プロパティの名前は、常に使用し、ローカライズされていることはありません。 これには、コントロールのディスパッチ マップ、プロパティの exchange 関数、およびプロパティ ページのデータ交換コードが含まれます。  
  
 1 つだけのタイプ ライブラリ (です。TLB) ファイルは、コントロールの実装のリソースにバインドする可能性があります (です。OCX) ファイルです。 これは、標準化されたバージョンでは通常 (通常は、英語) の名前。 出荷する必要があるコントロールのローカライズされたバージョンを出荷します。OCX (これは既定値に既にバインドされています。TLB バージョン) とします。適切なロケールの TLB です。 これだけであることを意味します.Ocx ファイルは、正しい以降英語版のバージョンが必要です。TLB に既にバインドされています。 その他のロケールでは、ローカライズされたタイプ ライブラリも配布するには、します。OCX です。  
  
 コントロールのクライアントが検出できるように、ローカライズされたタイプ ライブラリ、するには、ロケール固有を登録します。Windows システム レジストリの TypeLib の項 TLB ファイル。 3 番目のパラメーター (通常は省略可能)、 [AfxOleRegisterTypeLib](../mfc/reference/registering-ole-controls.md#afxoleregistertypelib)関数はこの目的で用意されています。 次の例は、ActiveX コントロールのフランス語のタイプ ライブラリを登録します。  
  
 [!code-cpp[NVC_MFC_AxLoc#2](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_2.cpp)]  
  
 コントロールを登録すると、`AfxOleRegisterTypeLib`関数は、指定されたを自動的に検索します。コントロールと同じディレクトリに TLB ファイル、Windows レジストリ データベースに登録します。 場合、します。TLB ファイルが見つからない場合は、関数が影響を与えません。  
  
##  <a name="_core_localizing_the_control.92.s_user_interface"></a> コントロールのユーザー インターフェイスのローカライズ  
 コントロールのユーザー インターフェイスをローカライズするには、言語固有のリソース Dll にすべてのプロパティ ページおよびエラー メッセージ) などのコントロールのユーザーに表示されるリソースを配置します。 コンテナーの LocaleID アンビエント プロパティを使用して、ユーザーのロケールに該当する DLL を選択することができますし、します。  
  
 次のコード例では、検索して特定のロケールのリソース DLL を読み込む方法の 1 つを示します。 このメンバー関数を呼び出す`GetLocalizedResourceHandle`この例では、ActiveX コントロール クラスのメンバー関数を指定できます。  
  
 [!code-cpp[NVC_MFC_AxLoc#3](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_3.cpp)]  
  
 専門的なローカライズを提供する、switch ステートメントの各 case でサブ言語 ID を確認することに注意してください。 この関数のデモについては、次を参照してください。、`GetResourceHandle`関数 MFC activex コントロール サンプル[LOCALIZE](../visual-cpp-samples.md)です。  
  
 コントロールが初めて読み込まれる自体をコンテナーに、ときに呼び出すことができます[COleControl::AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)ロケール ID を取得するには コントロールは、返されるロケール ID の値を渡すことができますし、`GetLocalizedResourceHandle`関数は、適切なリソース ライブラリが読み込まれます。 コントロールが存在する場合、結果として得られるハンドルを渡す必要がありますに[AfxSetResourceHandle](../mfc/reference/application-information-and-management.md#afxsetresourcehandle):  
  
 [!code-cpp[NVC_MFC_AxLoc#4](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_4.cpp)]  
  
 上記のコード サンプルに、メンバー関数のオーバーライドなど、コントロールの配置[COleControl::OnSetClientSite](../mfc/reference/colecontrol-class.md#onsetclientsite)です。 さらに、 *m_hResDLL*コントロール クラスのメンバー変数にする必要があります。  
  
 コントロールのプロパティ ページをローカライズするのと同様のロジックを使用できます。 プロパティ ページをローカライズするには、プロパティ ページの実装ファイルに次の例のようなコードを追加 (のオーバーライドで[COlePropertyPage::OnSetPageSite](../mfc/reference/colepropertypage-class.md#onsetpagesite))。  
  
 [!code-cpp[NVC_MFC_AxLoc#5](../mfc/codesnippet/cpp/mfc-activex-controls-localizing-an-activex-control_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

