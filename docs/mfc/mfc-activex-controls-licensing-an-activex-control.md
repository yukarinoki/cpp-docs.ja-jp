---
title: 'MFC ActiveX コントロール : ActiveX コントロールのライセンス'
ms.date: 11/19/2018
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: 4fe2fcf63cce02ed6c1c9943e6d0fe6ffab00a92
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622364"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX コントロール : ActiveX コントロールのライセンス

ActiveX コントロールのオプション機能であるライセンスサポートを使用すると、コントロールを使用または配布できるユーザーを制御できます。 (ライセンスに関する問題の詳細については、「[既存の ActiveX コントロールのアップグレード](upgrading-an-existing-activex-control.md)に関する問題」を参照してください)。

> [!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

この記事では、次のトピックについて説明します。

- [ActiveX コントロールのライセンスの概要](#_core_overview_of_activex_control_licensing)

- [ライセンスされたコントロールの作成](#_core_creating_a_licensed_control)

- [ライセンスサポート](#_core_licensing_support)

- [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)

ライセンスを実装する ActiveX コントロールでは、コントロール開発者は、他のユーザーが ActiveX コントロールを使用する方法を決定できます。 コントロールの購入者には、コントロールとを指定します。契約書を使用する LIC ファイル。購入者がコントロールを配布することはできますが、は含まれません。LIC ファイル。コントロールを使用するアプリケーションが含まれています。 これにより、そのアプリケーションのユーザーは、最初にコントロールをライセンス認証することなく、コントロールを使用する新しいアプリケーションを作成できなくなります。

## <a name="overview-of-activex-control-licensing"></a><a name="_core_overview_of_activex_control_licensing"></a>ActiveX コントロールのライセンスの概要

ActiveX コントロールのライセンスサポートを提供するために、 [COleObjectFactory](reference/coleobjectfactory-class.md)クラスは `IClassFactory2` `IClassFactory2::RequestLicKey` 、、、およびのインターフェイス内のいくつかの関数の実装を提供し `IClassFactory2::GetLicInfo` `IClassFactory2::CreateInstanceLic` ます。 コンテナーアプリケーションの開発者がコントロールのインスタンスを作成する要求を行うと、 `GetLicInfo` そのコントロールを確認するための呼び出しが行われます。LIC ファイルが存在します。 コントロールがライセンスされている場合は、コントロールのインスタンスを作成し、コンテナーに配置できます。 開発者がコンテナーアプリケーションの構築を完了すると、もう1つの関数呼び出し `RequestLicKey` が行われます。 この関数は、ライセンスキー (単純な文字列) をコンテナーアプリケーションに返します。 返されたキーは、アプリケーションに埋め込まれます。

次の図は、コンテナーアプリケーションの開発中に使用される ActiveX コントロールのライセンス検証を示しています。 既に説明したように、コンテナーアプリケーションの開発者には適切なが必要です。コントロールのインスタンスを作成するために開発用コンピューターにインストールされた LIC ファイル。

![開発時で検証された、ライセンスされた ActiveX コントロール](../mfc/media/vc374d1.gif "開発時で検証された、ライセンスされた ActiveX コントロール") <br/>
開発時の ActiveX コントロールのライセンス検査

次の図に示すように、エンドユーザーがコンテナーアプリケーションを実行すると、次のプロセスが発生します。

アプリケーションが開始されると、通常、コントロールのインスタンスを作成する必要があります。 コンテナーは、を呼び出して `CreateInstanceLic` 、埋め込みライセンスキーをパラメーターとして渡すことによってこれを実現します。 次に、埋め込みライセンスキーと、ライセンスキーのコントロール独自のコピーとの間で文字列比較が行われます。 一致が成功した場合、コントロールのインスタンスが作成され、アプリケーションは正常に実行され続けます。 であることに注意してください。LIC ファイルがコントロールユーザーのコンピューターに存在していない必要があります。

![実行時に検証された、ライセンスされた ActiveX コントロール](../mfc/media/vc374d2.gif "実行時に検証された、ライセンスされた ActiveX コントロール") <br/>
実行時の ActiveX コントロールのライセンス検査

コントロールのライセンスは、コントロール実装 DLL 内の特定のコードとライセンスファイルの2つの基本的なコンポーネントで構成されています。 このコードは、2つ (または 3) の関数呼び出しと、著作権に関する通知を含む "ライセンス文字列" と呼ばれる文字列で構成されます。 これらの呼び出しとライセンス文字列は、コントロールの実装にあります (「」を参照してください。CPP) ファイル。 ActiveX コントロールウィザードによって生成されるライセンスファイルは、著作権に関する声明を含むテキストファイルです。 これには、プロジェクト名とを使用して名前が付けられます。LIC extension (例)。LIC. デザイン時の使用が必要な場合は、ライセンスされたコントロールにライセンスファイルを添付する必要があります。

## <a name="creating-a-licensed-control"></a><a name="_core_creating_a_licensed_control"></a>ライセンスされたコントロールの作成

ActiveX コントロールウィザードを使用してコントロールフレームワークを作成する場合、ライセンスサポートを簡単に含めることができます。 コントロールにランタイムライセンスが必要であることを指定すると、ActiveX コントロールウィザードによって、ライセンスをサポートするためのコードがコントロールクラスに追加されます。 このコードは、ライセンス認証のためにキーとライセンスファイルを使用する関数で構成されています。 これらの関数を変更して、コントロールのライセンスをカスタマイズすることもできます。 ライセンスのカスタマイズの詳細については、この記事で後述する「 [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)」を参照してください。

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>ActiveX コントロールウィザードを使用して、コントロールプロジェクトを作成するときにライセンスのサポートを追加するには

1. 「 [MFC ActiveX コントロールの作成](reference/creating-an-mfc-activex-control.md)」の手順を使用します。 ActiveX コントロールウィザードの [**アプリケーションの設定**] ページには、ランタイムライセンスを持つコントロールを作成するオプションがあります。

ActiveX コントロールウィザードで、基本的なライセンスサポートを含む ActiveX コントロールフレームワークが生成されるようになりました。 ライセンスコードの詳細については、次のトピックを参照してください。

## <a name="licensing-support"></a><a name="_core_licensing_support"></a>ライセンスサポート

Activex コントロールウィザードを使用して ActiveX コントロールにライセンスサポートを追加すると、ActiveX コントロールウィザードによって、ライセンス機能を宣言して実装するコードが追加され、コントロールのヘッダーおよび実装ファイルに追加されます。 このコードは、 `VerifyUserLicense` メンバー関数とメンバー関数で構成され `GetLicenseKey` 、 [COleObjectFactory](reference/coleobjectfactory-class.md)で見つかった既定の実装をオーバーライドします。 これらの関数は、コントロールのライセンスを取得して確認します。

> [!NOTE]
> 3番目のメンバー関数 `VerifyLicenseKey` は、ActiveX コントロールウィザードでは生成されませんが、オーバーライドしてライセンスキーの検証動作をカスタマイズできます。

これらのメンバー関数は次のとおりです。

- [VerifyUserLicense](reference/coleobjectfactory-class.md#verifyuserlicense)

   コントロールで、コントロールのライセンスファイルが存在するかどうかを確認することによって、デザイン時の使用を許可するかどうかを確認します。 この関数は、およびの処理の一部としてフレームワークによって呼び出され `IClassFactory2::GetLicInfo` `IClassFactory::CreateInstanceLic` ます。

- [GetLicenseKey](reference/coleobjectfactory-class.md#getlicensekey)

   コントロール DLL から一意のキーを要求します。 このキーはコンテナーアプリケーションに埋め込まれ、後でと組み合わせて使用して `VerifyLicenseKey` 、コントロールのインスタンスを作成します。 この関数は、処理の一部としてフレームワークによって呼び出され `IClassFactory2::RequestLicKey` ます。

- [VerifyLicenseKey](reference/coleobjectfactory-class.md#verifylicensekey)

   埋め込まれたキーとコントロールの一意のキーが同じであることを確認します。 これにより、コンテナーは使用するコントロールのインスタンスを作成できます。 この関数は、処理の一部としてフレームワークによって呼び出され、 `IClassFactory2::CreateInstanceLic` ライセンスキーのカスタマイズされた検証を行うためにオーバーライドできます。 既定の実装では、文字列比較が実行されます。 詳細については、この記事で後述する「 [ActiveX コントロールのライセンスのカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)」を参照してください。

### <a name="header-file-modifications"></a><a name="_core_header_file_modifications"></a>ヘッダーファイルの変更

ActiveX コントロールウィザードでは、次のコードがコントロールヘッダーファイルに配置されます。 この例では、のオブジェクトの2つのメンバー関数 `CSampleCtrl` `factory` が宣言されています。1つはコントロールの存在を検証する関数です。LIC ファイルと、コントロールを含むアプリケーションで使用されるライセンスキーを取得する別のファイル。

[!code-cpp[NVC_MFC_AxUI#39](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

### <a name="implementation-file-modifications"></a><a name="_core_implementation_file_modifications"></a>実装ファイルの変更

ActiveX コントロールウィザードでは、ライセンスファイル名とライセンス文字列を宣言するために、コントロール実装ファイルに次の2つのステートメントが配置されます。

[!code-cpp[NVC_MFC_AxUI#40](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
> `szLicString`何らかの方法で変更する場合は、コントロールの最初の行も変更する必要があります。LIC ファイルまたはライセンスは正常に機能しません。

ActiveX コントロールウィザードでは、コントロールクラスと関数を定義するために、コントロールの実装ファイルに次のコードを配置し `VerifyUserLicense` `GetLicenseKey` ます。

[!code-cpp[NVC_MFC_AxUI#41](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

最後に、 **ActiveX コントロールウィザード**によって、コントロールプロジェクトが変更されます。IDL ファイル。 **ライセンス**されたキーワードは、次の例のように、コントロールのコクラス宣言に追加されます。

[!code-cpp[NVC_MFC_AxUI#42](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

## <a name="customizing-the-licensing-of-an-activex-control"></a><a name="_core_customizing_the_licensing_of_an_activex_control"></a>ActiveX コントロールのライセンスのカスタマイズ

`VerifyUserLicense`、 `GetLicenseKey` 、および `VerifyLicenseKey` は、コントロールファクトリクラスの仮想メンバー関数として宣言されているため、コントロールのライセンスの動作をカスタマイズできます。

たとえば、またはのメンバー関数をオーバーライドすることにより、コントロールに複数のレベルのライセンスを提供でき `VerifyUserLicense` `VerifyLicenseKey` ます。 この関数内では、検出されたライセンスレベルに従って、ユーザーに公開されるプロパティまたはメソッドを調整できます。

また、 `VerifyLicenseKey` コントロールの作成が失敗したことをユーザーに通知するためのカスタマイズされたメソッドを提供するコードを関数に追加することもできます。 たとえば、メンバー関数では、 `VerifyLicenseKey` コントロールが初期化に失敗したこととその理由を示すメッセージボックスを表示できます。

> [!NOTE]
> ActiveX コントロールライセンスの検証をカスタマイズするもう1つの方法は、を呼び出す代わりに、登録データベースで特定のレジストリキーを確認することです `AfxVerifyLicFile` 。 既定の実装の例については、この記事の「[実装ファイルの変更](#_core_implementation_file_modifications)」セクションを参照してください。

ライセンスに関する問題の詳細については、「[既存の ActiveX コントロールのアップグレード](upgrading-an-existing-activex-control.md)に関する問題」を参照してください。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)<br/>
[MFC ActiveX コントロールウィザード](reference/mfc-activex-control-wizard.md)
